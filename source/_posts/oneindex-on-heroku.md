---
title: Deploying OneIndex on Heroku
date: 2018-07-18 11:00:00
lang: en
categories:
- 996.ICU
tags:
- OneDrive
- Heroku
---

Students from those schools which offer [Office 365 Education](https://products.office.com/en-us/student/office-in-education) are eligible to enjoy up to 5TB of OneDrive for Business storage. With the huge space provided, we can turn it into a file hosting platform, which is similar to [Amazon S3](https://aws.amazon.com/s3/), to store and share static files like documents, images, videos, etc. OneDrive for Business supports [sharing files](https://support.office.com/en-us/article/share-onedrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business) with external users, but your school has to opt to enable external sharing, and the links generated are encoded. We can use a program called [OneIndex](https://github.com/donwa/oneindex) which helps generate **direct download links** without enabling external sharing. We can link to our files directly later.

<!-- more -->

## Introduction

OneIndex is a PHP program developed by [&#64;donwa](https://github.com/donwa) which indices directories and files in OneDrive or OneDrive for Business. We can deploy it on a PHP server. If you have your own server, you can simply install it on a LAMP (Linux, Apache, MySQL, PHP) stack. In this tutorial, I will demonstrate how to install it on [Heroku](https://www.heroku.com/), where we can deploy cloud applications for free. However, due to Heroku's [ephemeral file system](https://devcenter.heroku.com/articles/dynos#ephemeral-filesystem), we still need a temporary server, and we have to install and configure the program twice.

## Installing OneIndex on a Server

You may check [my previous post](../shadowsocksr/#Prepare-a-server) to prepare a server if you do not have one. I will deploy a [Vultr](https://www.vultr.com/promo25b?ref=7436070) Cloud Compute (VC2) server with Ubuntu 18.04 in this tutorial.

### Installing Apache2 Web Server and PHP

First, follow [this tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-ubuntu-18-04) to set up a LAMP stack. Here are some points that you should take care of:

- Setting up firewall rules is important to keep your server secure. However, you can skip enabling the UFW firewall in Step 1 if your server supports setting up firewall from graphical interface or your server is for temporary use. 
- You can skip Step 2 since we do not need a database. Similarly, you do not to install `php-mysql` in Step 3.

In addition, we need to enable PHP's cULR module. Run the following commands to install the module and to restart Apache web server:

```bash
sudo apt install php-curl
sudo systemctl restart apache2
```

We also need to allow `.htaccess` overrides. Suppose we will use`/var/www/oneindex` as the root directory of our OneIndex program. Use your favorite editor to create an Apache configuration file for OneIndex:

```bash
sudo vim /etc/apache2/sites-available/oneindex.conf
```

Add the following text to the file:

```txt
<VirtualHost *:80>
	DocumentRoot /var/www/oneindex
	ErrorLog ${APACHE_LOG_DIR}/error.log
	CustomLog ${APACHE_LOG_DIR}/access.log combined
	<Directory /var/www/oneindex/>
		AllowOverride All
	</Directory>
</VirtualHost>
```

Then run the following commands to enable our site:

```bash
sudo a2ensite oneindex.conf
sudo a2dissite 000-default.conf
```

Run the following commands to enable Apache mod_rewrite:

```bash
sudo a2enmod rewrite
sudo systemctl restart apache2
```

### Installing OneIndex

Now, let's start to deploy OneIndex on our server. Download the GitHub repository, move it to the root directory and change the ownership:

```bash
sudo apt install git
git clone https://github.com/donwa/oneindex.git
sudo mv oneindex/ /var/www/
sudo chown -R www-data:www-data /var/www/oneindex
```

Now, open the browser and visit your site. Follow [this animation](https://github.com/donwa/oneindex#安装) to install and configure OneIndex. Some additional configurations can be found [in this tutorial](https://github.com/donwa/oneindex/blob/5ce51982c4903107c44a9e7e7e525869360c034c/README.md#可配置项). Make sure that your settings are final, since it is not trivial to change them after we move it onto Heroku.

## Installing OneIndex on Heroku

On the local machine, follow the first two steps of [this tutorial](https://devcenter.heroku.com/articles/getting-started-with-php) to set up the development environment.

Then prepare the template of the PHP cloud application:

```bash
git clone https://github.com/heroku/php-getting-started.git
mv php-getting-started/ onedrive
cd onedrive
```

Pick your favorite editor, edit `composer.json` in the root directory to adjust dependencies:

```json
{
  "require" : {
    "php": "^7.2.0"
  },
  "require-dev": {
    "heroku/heroku-buildpack-php": "*"
  }
}
```

Run the following command to update the dependencies:

```bash
composer update
```

In the root directory, replace the `web` directory by OneIndex program:

```bash
rm -rf web/
git clone https://github.com/donwa/oneindex.git
mv oneindex/ web
```

> In case you want to put OneIndex in a subfolder, make sure to set up `.htaccess` correctly under the `web` directory:
> 
> ```txt
RewriteEngine On
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^.*$ /index.php [L,QSA]
```

Now, we need to "borrow" the configuration files of OneIndex on the server.

> As stated before, Heroku has an ephemeral file system, which means that any files written will be discarded eventually. Generated by the program when we install OneIndex, caches and configuration are not parts of the Heroku application. Therefore, they will go away as well. It does not matter whether caches are persistent, but we have to make sure that configuration is persistent. Therefore, we have to use a temporary server to generate the configuration first and put the files into the Heroku application's repository before publishing it.

Pick your favorite SFTP or SCP client, for example, graphical interface tools such as [FileZilla](https://filezilla-project.org) and [WinSCP](https://winscp.net) (for Windows only) or command-line tools such as `sftp` or `scp`. Download `base.php` and `token.php` from the server (inside `/var/www/onedrive/config/`) to your local repository (`web/config`).

Last, create an application on Heroku, and use Heroku CLI to push the local repository to the cloud (supposing your application is `oneindex`):

```bash
heroku login
heroku create oneindex
git push heroku master
```

Open the browser and verify whether OneIndex is working on https://oneindex.herokuapp.com/.

## Reference

1. M. Drake, "How To Install Linux, Apache, MySQL, PHP (LAMP) stack on Ubuntu 18.04," *DigitalOcean*. [Online]. Available: <https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-ubuntu-18-04>.
2. B. Boucheron, "How To Install WordPress with LAMP on Ubuntu 18.04," *DigitalOcean*. [Online]. Available: <https://www.digitalocean.com/community/tutorials/how-to-install-wordpress-with-lamp-on-ubuntu-18-04>.
3. B., "How To Set Up Apache Virtual Hosts on Ubuntu 16.04," *DigitalOcean*. [Online]. Available: <https://www.digitalocean.com/community/tutorials/how-to-set-up-apache-virtual-hosts-on-ubuntu-16-04>.
4. "Getting Started on Heroku with PHP," *Heroku*. [Online]. Available: <https://devcenter.heroku.com/articles/getting-started-with-php>.

## 扯些别的

专题[《FUN@HK 香港玩啲乜》](../funathk/)暂时跳票了。在这个专题里，我将会分享许多香港鲜为人知的好去处。然而由于资料整理起来比较耗时间，这个专题何时上线还不确定。

回国以后补、追了这些番：

- [《青春之旅》（『アオハライド』）](https://zh.moegirl.org/zh-cn/青春之旅)：狗粮，还蛮温馨的；
- [《Slow Start》（『スロウスタート』）](https://zh.moegirl.org/zh-cn/Slow_Start)：没get到萌点；
- [《Comic Girls》（『こみっくがーるず』）](https://zh.moegirl.org/zh-cn/Comic_Girls)：萝莉们好萌啊，挺励志的；
- [《此花亭奇谭》（『このはな綺譚』）](https://zh.moegirl.org/zh-cn/此花亭奇谭)：兽耳娘们好萌啊，故事设定也很温馨；
- [《清恋》（『セイレン』）](https://zh.moegirl.org/zh-cn/Seiren)：污恋，[《缘之空》](https://zh.moegirl.org/zh-cn/缘之空)既视感，还不错；
- [《DARLING in the FRANXX》（『ダーリン・イン・ザ・フランキス』）](https://zh.moegirl.org/zh-cn/DARLING_in_the_FRANXX)：我TM吹爆[京紫](https://zh.moegirl.org/zh-cn/紫罗兰永恒花园)；
- [《刀剑神域外传 Gun Gale Online》（『ソードアート・オンライン オルタナティブ ガンゲイル・オンライン』）](https://zh.moegirl.org/zh-cn/刀剑神域外传_Gun_Gale_Online)：故事一般般，坐等十月[正篇第三季](https://zh.moegirl.org/zh-cn/刀剑神域)；
- [《比宇宙更远的地方》（『宇宙よりも遠い場所』）](https://zh.moegirl.org/zh-cn/比宇宙更远的地方)：一月霸权，故事很棒，然而去一趟南极太贵了；
- [《Another》](https://zh.moegirl.org/zh-cn/Another)：故事很棒，画面太阴暗，人偶比较恐怖；
- [《漫画家与助手》（『マンガ家さんとアシスタントさんと』）](https://zh.moegirl.org/zh-cn/漫画家与助手)：搞笑，可惜男主是个绅士；
- [《摇曳露营△》（『ゆるキャン△』）](https://zh.moegirl.org/zh-cn/摇曳露营)：一月霸权，感同身受但还是不建议一个人去露营。
