## Install MariaDB

MariaDB is a popular database engine. Like PHP, it's widely used on web servers, which is why projects like WordPress use it, and why those projects are so popular.

Install the MariaDB Server and PHP-MySQL packages by entering the following command into the terminal window:

```bash
sudo apt-get install mariadb-server php-mysql -y
```

Now restart Apache:

```bash
sudo service apache2 restart
```
