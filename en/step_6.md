## Download WordPress

You can download WordPress from [wordpress.org](http://wordpress.org/) using the `wget` command. Helpfully, a copy of the latest version of WordPress is always available at [wordpress.org/latest.tar.gz](https://wordpress.org/latest.tar.gz) and [wordpress.org/latest.zip](https://wordpress.org/latest.zip), so you can grab the latest version without having to look it up on the website. At the time of writing, this is version 4.5.

+ Change directory to `/var/www/html/` and delete all the files in the folder.

```bash
cd /var/www/html/
sudo rm *
```

+ Download WordPress using `wget`.

```bash
sudo wget http://wordpress.org/latest.tar.gz
```

+ Extract the WordPress tarball.

```bash
sudo tar xzf latest.tar.gz
```

+ Move the contents of the `wordpress` directory it extracted to the current directory.

```bash
sudo mv wordpress/* .
```

+ Tidy up by removing the, now empty, `wordpress` directory and tarball 

```bash
sudo rm -rf wordpress latest.tar.gz
```

Running the `ls` or `tree -L 1` command here will show you the contents of a WordPress project:

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

+ You should now change the ownership of these files to the Apache user:

```bash
sudo chown -R www-data: .
```

