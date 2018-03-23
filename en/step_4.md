## Install PHP

PHP is a **preprocessor**: it's code that runs when the server receives a request for a web page via a web browser. It works out what needs to be shown on the page, and then sends that page to the browser. Unlike static HTML, PHP can show different content under different circumstances. Other languages are also capable of doing this, but since WordPress is written in PHP, that's what we need to use this time. PHP is a very popular language on the web: huge projects like Facebook and Wikipedia are written in PHP.

+ Install the PHP and Apache packages with the following command:

```bash
sudo apt-get install php -y
```

### Test PHP

+ Create the file `index.php`:

```bash
sudo leafpad index.php
```

+ Put some PHP content in it:

```php
<?php echo "hello world"; ?>
```

+ Save the file. 

+ Delete `index.html`, because it takes precendence over `index.php`:

```bash
sudo rm index.html
```

Refresh your browser. You should see "hello world". This page is not dynamic, but it is still served by PHP.

![hello world](images/apache-hello-world.png)

If you see the raw PHP above instead of "hello world", reload and restart Apache like so:

```bash
sudo service apache2 restart
```

+ Edit `index.php` to include some dynamic content, for example:

```php
<?php echo date('Y-m-d H:i:s'); ?>
```

Or show your PHP info:

```php
<?php phpinfo(); ?>
```
