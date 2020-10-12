## Install MariaDB

MariaDB is a popular database engine. Όπως και η PHP, χρησιμοποιείται ευρέως σε διακομιστές ιστού και γι' αυτό τον λόγο  έργα όπως το WordPress την χρησιμοποιούν και επειδή  αυτά τα έργα είναι τόσο δημοφιλή.

Install the MariaDB Server and PHP-MySQL packages by entering the following command into the terminal window:

```bash
sudo apt-get install mariadb-server php-mysql -y
```

Τώρα κάνε επανεκκίνηση τον Apache:

```bash
sudo service apache2 restart
```
