## Download WordPress

You can download WordPress from [wordpress.org](http://wordpress.org/) using the `wget` command. Helpfully, a copy of the latest version of WordPress is always available at [wordpress.org/latest.tar.gz](https://wordpress.org/latest.tar.gz), so you can grab the latest version without having to look it up on the website. At the time of writing, this is version 4.5.

--- collapse ---

---
title: What is a .tar.gz file?
---

In case you're wondering, `.tar.gz` stands for 'gzip-compressed tar archive'. `gzip` is a tool for compressing files, which means reducing their size so they can be stored or distributed more easily. `.tar` stands for tarball, which is a computer file format that combines and compresses multiple files. Software is often available for download in `.tar.gz` format, because downloading a tarball is a lot faster than downloading the non-compressed files.

--- /collapse ---

+ Change directory to `/var/www/html/` and delete all the files in the folder.

```bash
cd /var/www/html/
sudo rm *
```

+ Download WordPress using `wget`.

```bash
sudo wget http://wordpress.org/latest.tar.gz
```

+ Extract the WordPress tarball to get at the WordPress files.

```bash
sudo tar xzf latest.tar.gz
```

+ Move the contents of the extracted `wordpress` directory to the current directory.

```bash
sudo mv wordpress/* .
```

+ Tidy up by removing the tarball and the now empty `wordpress` directory.

```bash
sudo rm -rf wordpress latest.tar.gz
```

- Running the `ls` or `tree -L 1` command now will show you the contents of a WordPress project:

```bash
.
├── index.php
├── license.txt
├── readme.html
├── wp-activate.php
├── wp-admin
├── wp-blog-header.php
├── wp-comments-post.php
├── wp-config-sample.php
├── wp-content
├── wp-cron.php
├── wp-includes
├── wp-links-opml.php
├── wp-load.php
├── wp-login.php
├── wp-mail.php
├── wp-settings.php
├── wp-signup.php
├── wp-trackback.php
└── xmlrpc.php

3 directories, 16 files
```

This is the source of a default WordPress installation. The files you edit to customise your installation belong in the `wp-content` folder.

+ You should now change the ownership of all these files to the Apache user:

```bash
sudo chown -R www-data: .
```
