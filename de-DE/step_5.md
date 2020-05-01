## Installiere MySQL

MySQL (ausgesprochen *My Sequel* oder *Mei S-Q-L*) ist eine beliebte Datenbank-Engine. Wie PHP wird es häufig auf Webservern verwendet, weshalb Projekte wie WordPress es verwenden und weshalb diese Projekte so beliebt sind.

Installiere die MySQL-Server- und PHP-MySQL-Pakete, indem du folgenden Befehl in das Terminal-Fenster eingibst:

```bash
sudo apt-get install mysql-server php-mysql -y
```

Starte jetzt Apache neu:

```bash
sudo service apache2 restart
```
