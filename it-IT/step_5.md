## Installa MariaDB

MariaDB è un popolare motore di database. Come PHP, è molto usato sui server Web, per questo motivo progetti come WordPress lo utilizzano ed è anche per questo che tali progetti sono così utilizzati.

Installa i pacchetti MariaDB Server e PHP-MySQL inserendo il seguente comando nella finestra del terminale:

```bash
sudo apt-get install mariadb-server php-mysql -y
```

Ora riavvia Apache:

```bash
sudo service apache2 restart
```
