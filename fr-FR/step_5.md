## Install MariaDB

MariaDB is a popular database engine. Comme PHP, il est largement utilisé sur les serveurs Web, c'est pourquoi des projets comme WordPress l'utilisent, et pourquoi ces projets sont si populaires.

Install the MariaDB Server and PHP-MySQL packages by entering the following command into the terminal window:

```bash
sudo apt-get install mariadb-server php-mysql -y
```

Redémarre maintenant Apache :

```bash
sudo service apache2 restart
```
