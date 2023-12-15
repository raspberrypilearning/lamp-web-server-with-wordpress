## Installer MariaDB

MariaDB est un moteur de base de données populaire. Comme PHP, il est largement utilisé sur les serveurs Web, c'est pourquoi des projets comme WordPress l'utilisent, et pourquoi ces projets sont si populaires.

Installe les packages MariaDB Server et PHP-MySQL en saisissant la commande suivante dans la fenêtre du terminal :

```bash
sudo apt-get install mariadb-server php-mysql -y
```

Redémarre maintenant Apache :

```bash
sudo service apache2 restart
```
