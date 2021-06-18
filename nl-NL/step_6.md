## Download WordPress

Je kunt WordPress downloaden van [wordpress.org](http://wordpress.org/) met behulp van de `wget` opdracht. Een kopie van de nieuwste versie van WordPress is altijd beschikbaar op [wordpress.org/latest.tar.gz](https://wordpress.org/latest.tar.gz), zodat je de nieuwste versie kunt pakken zonder deze op te zoeken op de website. Op het moment van schrijven is dit versie 5.4.

--- collapse ---

---
title: Wat is een .tar.gz-bestand?
---

Mocht je het je afvragen, `.tar.gz` staat voor 'gzip-compressed tar archive'. `gzip` is een tool voor het comprimeren van bestanden, wat betekent dat ze kleiner worden gemaakt, zodat ze gemakkelijker kunnen worden opgeslagen of gedistribueerd. `.tar` staat voor tarball, een computerbestandsformaat dat meerdere bestanden combineert en comprimeert. Software is vaak beschikbaar om te downloaden in `.tar.gz` formaat, omdat het downloaden van een tarball veel sneller is dan het downloaden van de niet-gecomprimeerde bestanden.

--- /collapse ---

+ Ga naar directory `/var/www/html/` en verwijder alle bestanden in de map.

```bash
cd /var/www/html/
sudo rm *
```

+ Download WordPress met `wget`.

```bash
sudo wget http://wordpress.org/latest.tar.gz
```

+ Pak de WordPress tarball uit om bij de WordPress-bestanden te komen.

```bash
sudo tar xzf latest.tar.gz
```

+ Verplaats de inhoud van de uitgepakte `wordpress` directory naar de huidige directory.

```bash
sudo mv wordpress/* .
```

+ Ruim op door het verwijderen van de tarball en de nu lege `wordpress` directory.

```bash
sudo rm -rf wordpress latest.tar.gz
```

- Het uitvoeren van de `ls` of `tree -L 1` opdracht toont nu de inhoud van een WordPress-project:

```bash
.
├── index.php
├── license.txt
├── readme.html
├── wp-activate.php
├── wp-admin
├── wp-blog-header.php
├── wp-comments-post.php
├── wp-config-sample.php
├── wp-content
├── wp-cron.php
├── wp-includes
├── wp-links-opml.php
├── wp-load.php
├── wp-login.php
├── wp-mail.php
├── wp-settings.php
├── wp-signup.php
├── wp-trackback.php
└── xmlrpc.php

3 directories, 16 files
```

Dit is de bron van een standaard WordPress-installatie. De bestanden die je bewerkt om je installatie aan te passen, horen thuis in de `wp-content` map.

+ Je moet nu het eigendom van al deze bestanden wijzigen in de Apache-gebruiker:

```bash
sudo chown -R www-data: .
```
