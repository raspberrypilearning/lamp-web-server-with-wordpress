## Install MySQL

MySQL (pronounced *My Sequel* or *My S-Q-L*) is a popular database engine. Like PHP, its overwhelming presence on web servers enhanced its popularity. This is why projects like WordPress use it, and why those projects are so popular.

Install the MySQL Server and PHP-MySQL packages by entering the following command into the terminal:

```bash
sudo apt-get install mysql-server php5-mysql -y
```

When installing MySQL you will be asked for a root password. You'll need to remember this to allow your website to access the database.

Now restart Apache:

```bash
sudo service apache2 restart
```

