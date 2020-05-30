---
title: Deploying PyCharm-Created Django Project on Heroku
date: 2020-02-28 17:00:00
lang: en
categories:
- 996.ICU
tags:
- Python
- Heroku
---

I previously hosted two of my [Django](https://docs.djangoproject.com/) projects, [NoteShare](https://github.com/maobowen/noteshare_django) and [Anime](https://github.com/maobowen/anime_django), on [IBM Cloud](https://www.ibm.com/cloud). Now, I have decided to switch to [Heroku](https://www.heroku.com), but the migration is not that straightforward. This article introduces how to deploy a Django project, created by [PyCharm](https://www.jetbrains.com/pycharm/), on Heroku.

<!-- more -->

## Why I Made This Switch

IBM Cloud, previously called IBM Bluemix, is a Platform-as-a-Service (PaaS) based on [Cloud Foundry](https://www.cloudfoundry.org/). It provides free Lite accounts, but [the limitations of those free accounts](https://cloud.ibm.com/docs/account?topic=account-accounts#lite-account-features) are super inconvenient:

- After 10 days of no development activity, your apps go to sleep.
- After 30 days of no development activity, your service instances with Lite plans are deleted.

Having these rules means that I have to frequently update my projects even if I don't need to. More interestingly, once an app goes to sleep, I must either push new code or log into the console to re-activate it. Therefore, I decided to switch to [Heroku's free plan](https://www.heroku.com/pricing). The free plan on Heroku also has [the following limitation](https://devcenter.heroku.com/articles/free-dyno-hours#dyno-sleeping):

- If an app has a free web dyno, and that dyno receives no web traffic in a 30-minute period, it will sleep.

However, I can simply re-activate the app by visiting the URL of it. If you really want your app being online during most of the time in a day, you always have [other options](https://medium.com/better-programming/keeping-my-heroku-app-alive-b19f3a8c3a82) available. (By the way, it is [not possible](https://devcenter.heroku.com/articles/free-dyno-hours#usage) to make the free dynos always online.)

## Differences Between IBM Cloud and Heroku

To me, there are two major differences.

- Cloud Foundry uses `.cfignore` to determine which files should be excluded from upload. This file can be different from `.gitignore` which determines which files should be excluded from the Git repository. This gives me more freedom of maintaining files in a project. For example, I don't want to ruin my repository by adding super large SQLite database file or numerous subtitle files of anime episodes. I don't want to push the credentials of the project to GitHub, too, but I want them available in the cloud. To deal with these cases, I could simply include those files in `.gitignore` but not in `.cfignore` in the past. However, on Heroku I don't have that level of control.
- Heroku's [ephemeral filesystem](https://devcenter.heroku.com/articles/dynos#ephemeral-filesystem) makes it [impossible to use file-based SQLite database](https://devcenter.heroku.com/articles/sqlite3), as I just explained that SQLite database will not and should not be added to the repository. Therefore, I must switch to some database systems such as Postgres or MySQL, and actually Heroku provides bunch of [database add-ons](https://elements.heroku.com/addons#data-stores). In addition, I cannot have any dynamically-generated files in the projects.

Therefore, I cannot directly push the projects to Heroku directly. Many changes must be made before doing that.

## Setting Up a New Django Project Using PyCharm

Since there are lots of changes to my out-dated projects (which haven't been maintained for a long time since my app on IBM Cloud was deleted) and I forgot the process of setting up Django projects, I decided to deploy a new one using PyCharm. The following tutorial assumes that:

- A Python environment for Django has been set up;
- Heroku CLI has been installed and configured;
- Postgres has been installed locally and a clean database has been created;
- A clean Django project has been created in PyCharm and the Git repository has been initialized;
- A Heroku app has been created.

### Preparing the Project

We need at least three files in the top-level project folder.

`runtime.txt` specifies the Python runtime the Heroku app uses. See a list of supported runtimes [here](https://devcenter.heroku.com/articles/python-support#specifying-a-python-version).

`Procfile` [declares what command to execute to start the app](https://devcenter.heroku.com/articles/getting-started-with-python#define-a-procfile). Since I uses [Gunicorn](https://gunicorn.org) as the server, here I just have one line:

```
web: gunicorn django_site.wsgi --log-file -
```

where `django_site` is Django project's name and `--log-file -` means log to `stderr`.

`requirements.txt` [defines app dependencies](https://devcenter.heroku.com/articles/getting-started-with-python#declare-app-dependencies). It is recommended to run `pip freeze > requirements.txt` to create it but at least those are necessary:

```txt
Django>=3.0.0
django-heroku>=0.3.0
gunicorn>=20.0.0
requests>=2.22.0
whitenoise>=4.1.0
```

Then run `pip install -r requirements.txt` to install all the dependencies locally. I would maintain packages using `conda` though.

In addition to those files, a `.gitignore` is also necessary. It can be easily created on [gitignore.io](https://gitignore.io). You can also use [mine](https://www.gitignore.io/api/django,linux,macos,pycharm+all,python,virtualenv,visualstudiocode,windows).

### Modifying Project's `settings.py`

`settings.py` is located inside `django_site` folder. It is generated by PyCharm to [configure the project](https://docs.djangoproject.com/en/3.0/ref/settings/). Here are the modifications:

Set `SECRET_KEY` because it should not be exposed to the public. This is critical if the repository will be pushed to some public code bases such as GitHub. So first, mark down the secret key. Then run `heroku config:set SECRET_KEY=<secret_key>` to set the environment variable `SECRET_KEY` on Heroku. Also, add this environment variable to any PyCharm configurations. Finally, change the code to `SECRET_KEY = os.environ.get('SECRET_KEY')` so that the app will read the key from the environment variable.

Set `DEBUG = False` and `DEBUG_PROPAGATE_EXCEPTIONS = True`.

Set `ALLOWED_HOSTS` where `django-site` is the name of the Heroku app:

```python
ALLOWED_HOSTS = [
    '0.0.0.0',
    '127.0.0.1',
    '[::1]',
    '.localhost',
    'django-site.herokuapp.com',
]
```

Add middleware [WhiteNoise](http://whitenoise.evans.io/en/stable/) by

- Adding `'whitenoise.runserver_nostatic'` to `INSTALLED_APPS`;
- Adding `'whitenoise.middleware.WhiteNoiseMiddleware'` to `MIDDLEWARE` [directly after the Django `SecurityMiddleware` and before all other middleware](http://whitenoise.evans.io/en/stable/django.html#enable-whitenoise);
- Setting `STATICFILES_STORAGE = 'whitenoise.storage.CompressedManifestStaticFilesStorage'`

```python
INSTALLED_APPS = [
    'whitenoise.runserver_nostatic',
    'django.contrib.staticfiles',
    # ...
]

MIDDLEWARE = [
    'django.middleware.security.SecurityMiddleware',
    'whitenoise.middleware.WhiteNoiseMiddleware',
    # ...
]

STATICFILES_STORAGE = 'whitenoise.storage.CompressedManifestStaticFilesStorage'
```

Set database connection. In order not to expose database URLs in the code, first add `import dj_database_url` to the very beginning of the file, then after `DATABASES = { ... }`, add the following code:

```python
if 'DATABASE_URL' in os.environ:
    # Configure Django for DATABASE_URL environment variable.
    DATABASES['default'] = dj_database_url.config(conn_max_age=600)
```

And don't forget to add `DATABASE_URL` environment variable to any PyCharm configurations with value `postgresql://localhost:5432/django_site` if `django_site` is the name of the local Postgres database.

Set [static asset](https://devcenter.heroku.com/articles/django-assets) variables. For example:

```python
STATIC_URL = '/static/'
STATIC_ROOT = os.path.join(BASE_DIR, 'staticfiles')
STATICFILES_DIRS = [
    os.path.join(BASE_DIR, 'static'),
]
```

Make sure that `staticfiles` and `static` folders exist in the top-level folder and `static` folder is not empty (i.e., containing at least one file). Also run `heroku config:set DEBUG_COLLECTSTATIC=1` to simplify debugging collectstatic on Heroku.

Set [media file](https://docs.djangoproject.com/en/3.0/topics/files/) variables:

```python
MEDIA_URL = '/media/'
MEDIA_ROOT = os.path.join(BASE_DIR, 'media')
```

Run `python manage.py migrate` to apply migrations.

## Setting Up a New Django Application

A Django project can have multiple Django applications. When PyCharm creates the project, an application can be created at the same time. The key things here are coding `app/urls.py`, `app/models,py` and `app/views.py`, designing templates and adding static files to `app/static/app` folder. Don't forget to add the application to `django_site/settings.py` and `django_site/urls.py`.

When done, run the following commands to migrate schema changes and [load initial data into the local database](https://docs.djangoproject.com/en/3.0/howto/initial-data/) if the fixture is located at `app/fixtures/app.json`:

```bash
python manage.py makemigrations
python manage.py migrate
python manage.py loaddata app
python manage.py collectstatic
```

## Pushing the Project to Heroku

We need to push both the local database and the local code repository to Heroku. I use [Heroku Postgres add-on](https://www.heroku.com/postgres) and have attached it to the Heroku app, so I just need to do:

```bash
heroku git:remote -a django-site
heroku pg:push postgresql://localhost:5432/django_site <postgresql_addon>
git push heroku master
```

## References

1. Harman Deep Singh, "Deploying Django App on Heroku with Postgres as Backend," *Medium*. [Online]. Available: <https://medium.com/%40hdsingh13/b2f3194e8a43>.
