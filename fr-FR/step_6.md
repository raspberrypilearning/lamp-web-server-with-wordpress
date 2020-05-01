## Télécharger WordPress

Tu peux télécharger WordPress à partir de [wordpress.org](http://wordpress.org/) en utilisant la commande `wget`. Heureusement, une copie de la dernière version de WordPress est toujours disponible sur [wordpress.org/latest.tar.gz](https://wordpress.org/latest.tar.gz) , afin que tu puisses récupérer la dernière version sans avoir à la rechercher sur le site Web. Au moment de la rédaction, il s'agit de la version 4.5.

--- collapse ---

---
title: Qu'est-ce qu'un fichier .tar.gz ?
---

Au cas où tu te poses la question, `.tar.gz` signifie « archive tar compressée par gzip ». `gzip` est un outil pour compresser des fichiers, ce qui signifie réduire leur taille afin qu'ils puissent être stockés ou distribués plus facilement. `.tar` signifie tarball, qui est un format de fichier informatique qui combine et compresse plusieurs fichiers. Le logiciel est souvent disponible pour téléchargement en format `.tar.gz`, car le téléchargement d'une archive « tar » est beaucoup plus rapide que le téléchargement des fichiers non compressés.

--- /collapse ---

+ Change le répertoire en `/var/www/html/` et supprime tous les fichiers du dossier.

```bash
cd /var/www/html/
sudo rm *
```

+ Télécharger WordPress en utilisant `wget`.

```bash
sudo wget http://wordpress.org/latest.tar.gz
```

+ Extrais l'archive « tar » de WordPress pour accéder aux fichiers WordPress.

```bash
sudo tar xzf latest.tar.gz
```

+ Déplace le contenu du répertoire `wordpress` extrait dans le répertoire actuel.

```bash
sudo mv wordpress/* .
```

+ Remets de l'ordre en supprimant l'archive tar et le répertoire `wordpress` qui est maintenant vide.

```bash
sudo rm -rf wordpress latest.tar.gz
```

- L'exécution de la commande `ls` ou `tree -L 1` te montreras maintenant le contenu d'un projet WordPress :

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

C'est la source d'une installation WordPress par défaut. Les fichiers que tu modifies pour personnaliser ton installation appartiennent au dossier `wp-contents` .

+ Tu dois maintenant changer la propriété de tous ces fichiers à l'utilisateur Apache :

```bash
sudo chown -R www-data: .
```
