## Zainstaluj MariaDB

MariaDB to popularny silnik baz danych. Podobnie jak PHP, jest szeroko stosowany na serwerach internetowych, dlatego projekty takie jak WordPress go używają i dlatego są one tak popularne.

Zainstaluj pakiety MariaDB Server i PHP-MySQL, wpisując następujące polecenie w oknie terminala:

```bash
sudo apt-get install mariadb-server php-mysql -y
```

Teraz uruchom ponownie Apache:

```bash
sudo service apache2 restart
```
