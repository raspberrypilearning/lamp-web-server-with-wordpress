## Install MySQL

MySQL (pronounced *My Sequel* or *My S-Q-L*) is a popular database engine. Like PHP, its overwhelming presence on web servers enhanced its popularity. This is why projects like WordPress use it, and why those projects are so popular.

Install the MySQL Server and PHP-MySQL packages by entering the following command into the terminal:

```bash
sudo apt-get install mysql-server php-mysql -y
```

Now restart Apache:

```bash
sudo service apache2 restart
```

