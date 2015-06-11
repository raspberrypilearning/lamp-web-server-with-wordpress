# Configuration du serveur Web et de WordPress

Mettre en place un serveur Web sur votre Pi et installer WordPress, un système de gestion de contenu qui rend plus facile la création de sites Web.

## Étape 1: Mettre en place le serveur Web Apache

Apache est le serveur Web le plus populaire, vous pouvez l'installer sur le Raspberry Pi pour lui permettre d'héberger et de générer des pages Web.

Utilisé seul, Apache peut générer des fichiers HTML via le protocole HTTP, et avec des modules supplémentaires, il peut générer des pages Web dynamiques utilisant des langages de script tel que PHP.

### Installer Apache

D'abord installez le paquet `apache2` en tapant la commande suivante dans le terminal :

```bash
sudo apt-get install apache2 -y
```

### Tester le serveur Web

Par défaut, Apache met un fichier HTML de test dans le dossier Web. Cette page Web par défaut est générée lorsque vous naviguez vers `http: // localhost /` sur le Pi lui-même, ou `http: // 192.168.1.10` (quelle que soit l'adresse IP du Pi) depuis un autre ordinateur sur le réseau. Pour connaître l'adresse IP du Pi, tapez `hostname -i` en ligne de commande (pour en savoir plus sur la manière de trouver de votre [IP address](http://www.raspberrypi.org/documentation/troubleshooting/hardware/networking/ip-address.md) dans notre documentation).

Accédez à la page Web par défaut, soit sur le Pi ou depuis un autre ordinateur sur le réseau, et vous devriez voir ce qui suit:

![](images/apache-it-works.png)

Cela signifie qu'Apache est en service et fonctionne !

#### Changer la page Web par défaut

This default Web page is just an HTML file on the filesystem; it is located at `/var/www/index.html`. Navigate to this directory in the terminal and have a look at what's inside:

Cette page Web par défaut est simplement un fichier HTML placé sur le gestionnaire de fichiers ; il est situé à `/ var / www / index.html` . Accédez à ce répertoire via le terminal et jetez un oeil à ce qui est à l'intérieur :

```bash
cd /var/www
ls -al
```

Vous devriez alors voir ceci :

```bash
total 12
drwxr-xr-x  2 root root 4096 Jan  8 01:29 .
drwxr-xr-x 12 root root 4096 Jan  8 01:28 ..
-rw-r--r--  1 root root  177 Jan  8 01:29 index.html
```

Cela montre qu'il y a un fichier dans `/var/www/` appelé `index.html`. Le `.` se réfère au répertoire lui-même `/var/www/` et le `..` se réfère au répertoire parent `/var/`.

La 3ème colonne montre que, par défaut, le répertoire `www` et le fichier `index.html` appartiennent tous les deux à l'utilisateur `root`. Afin de modifier le fichier, vous devez obtenir les permissions de `root`. Vous devrez donc soit changer les droits de votre propre utilisateur avant l'édition (en utilisant `sudo chown pi: index.html`), soit en utilisant le préfixe `sudo` lors de la commande d'édition (`sudo nano index.html`).

Essayez d'éditer ce fichier puis rafraîchissez la page Web pour voir le changement. Appuyez sur `Ctrl + X` puis sur `Enter` pour sauvegarder et quitter.

## Étape 2 : Installer PHP

PHP est un préprocesseur : c'est le code qui fonctionne lorsque le serveur reçoit une requête pour une page Web. Il se lance, génère tout ce qui doit être montré sur la page, puis envoie la page dans le navigateur. Contrairement à du HTML statique, PHP peut montrer un contenu différent dans des circonstances différentes. D'autres langages sont capables de cela, mais étant donné que WordPress est écrit en PHP, c'est ce que nous devons utiliser ici. PHP est un langage très populaire sur le Web, de grands projets tels que Facebook et Wikipédia sont écrits en PHP .

Installez les paquets PHP et Apache avec la commande suivante :

```bash
sudo apt-get install php5 libapache2-mod-php5 -y
```

### Test PHP

Créez un fichier index.php:

```bash
sudo nano index.php
```

Insérez-y du contenu php :

```php
<?php echo "hello world";
```

Sauvegarder le fichier puis supprimer le fichier index.html car il a précédence sur le fichier index.php:
```bash
sudo rm index.html
```

Rafraîchissez votre page. Vous devriez y lire "hello world". Ce n'est pas dynamique mais bien généré par PHP. Essayez du contenu dynamique, par exemple :

```php
<?php echo date('Y-m-d H:i:s');
```

Ou affichez les informations de PHP :

```php
<?php phpinfo();
```

## Étape 3 : Installer MySQL

MySQL (prononcé *Maï S-Q-L*) est un moteur de base de données très répandu. Comme PHP, sa présence écrasante sur les serveurs Web a accru sa popularité. Voilà pourquoi des projets comme WordPress l'utilisent, et pourquoi ces projets sont si populaires.

Installez les paquets serveur MySQL et PHP - MySQL en entrant la commande suivante dans le terminal :

```bash
sudo apt-get install mysql-server php5-mysql -y
```

A l'installation de MySQL, un mot de passe vous sera demandé pour l'utilisateur root. Vous devriez le choisir avec soin et vous en rappeler car vous en aurez besoin pour permettre à votre Site Web d'accéder à la baase de données.

## Étape 4 : Télécharger WordPress

Vous pouvez télécharger WordPress à partir de son site [ wordpress.org ] ( http://wordpress.org/ ) en utilisant la commande `wget`. Par chance, une copie de la dernière version de WordPress est toujours disponible au [ wordpress.org/latest.tar.gz](https://wordpress.org/latest.tar.gz ) et [ wordpress.org/latest.zip ] ( https://wordpress.org/latest.zip ), de sorte que vous pouvez récupérer la dernière version sans avoir à chercher sur le Site. A la rédaction de ce tutoriel, il s'agit de la version 4.0.

Accédez à `/var/www/`, et téléchargez WordPress à cet emplacement. Vous aurez besoin de vider le dossier en premier ( assurez-vous de ne pas supprimer de fichiers dont vous avez besoin avant d'exécuter `rm` ) et donnez la propriété de ce dossier à l'utilisateur de `pi` également.

```bash
cd /var/www
sudo chown pi: .
sudo rm *
wget http://wordpress.org/latest.tar.gz
```

Maintenant, veuillez décompresser l'archive et déplacez le contenu extrait (`wordpress`) dans le répertoire courant et supprimer le dossier (maintenant vide) ainsi que l'archive :

```bash
tar xzf latest.tar.gz
mv wordpress/* .
rm -rf wordpress latest.tar.gz
```

L'exécution de la commande `ls` ou (` -L arbre 1`) ici va vous montrer le contenu d'un projet WordPress :

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
```

Ceci est une installation WordPress par défaut. Les fichiers que vous modifiez pour personnaliser votre installation sont contenus dans le dossier `wp-content`.

## Étape 5 : Mettre en place votre base de données WordPress

Pour la mise en place votre site WordPress, vous avez besoin d'une base de données. Exécutez la commande `mysql` dans le terminal et fournissez vos identifiants de connexion (par exemple nom d'utilisateur `root` , mot de passe `password`) :

```bash
mysql -uroot -ppassword
```

Ici, je vous ai fourni mon mot de passe (le mot `password`) sur la ligne de commande ; il n'y a pas d'espace entre `-p` et le mot de passe.

Sinon, vous pouvez simplement fournir un flag `-p` vide et attendez d'être invité pour renseigner le mot de passe :

```bash
mysql -uroot -p
```

Maintenant, vous serez invité à entrer le mot de passe de l'utilisateur root que vous avez créé plus tôt.

Une fois que vous êtes connecté à MySQL, vous pouvez créer la base de données nécessaire à l'installation de WordPress :

```
mysql> create database wordpress;
```

Notez le point-virgule terminant la déclaration. En cas de succès, vous devriez voir le message suivant :

```
Query OK, 1 row affected (0.00 sec)
```

Quittez l'invite MySQL avec `Ctrl+D`.

## Étape 6 : Configurer WordPress

Vous devez connaître l'adresse IP de votre Pi pour y accéder dans le navigateur, donc dans le terminal tapez la commande `hostname -i` .

Accédez à `http://VOTRE-ADRESSE-IP` par exemple `http://192.168.1.5` dans le navigateur Web de votre Pi .

Vous devriez voir une page d'erreur WordPress : c'est bon ! Cliquez sur le gros bouton marqué `Create a Configuration File` puis sur le bouton `Let's go!` de la page suivante.

Maintenant, remplissez les informations de base du site comme suit : 

```
Database Name:      wordpress
User Name:          root
Password:           <YOUR PASSWORD>
Database Host:      localhost
Table Prefix:       wp_
```

Une fois la connexion à la base de données réussie, le contenu de votre fichier `wp-config.php` sera affiché :

![](images/wp-config.png)

Copiez ce texte, retournez sur le terminal du Pi et éditez le fichier avec la commande `nano wp- config.php`. Collez le texte dans ce fichier, sauvegarder et quitter avec `Ctrl+X`, puis `Y` pour oui et tapez `Enter`.

Maintenant, cliquez sur le bouton `Run the install`.

### Ecran d'accueil

Vous y êtes presque.

![](images/wp-info.png)

Remplissez les informations : donnez un titre à votre site, créez un nom d'utilisateur et un mot de passe, ajoutez votre adresse email et décochez la case des moteurs de recherche. Appuyez sur le bouton `Install WordPress` , puis connectez-vous en utilisant le compte que vous venez de créer .

Maintenant connecté et votre site mis en place, vous pouvez consulter le site Web en visitant votre adresse IP dans le navigateur sur le Pi ou un autre ordinateur sur le réseau. Pour vous connecter à nouveau (ou sur un autre ordinateur), aller à `http://VOTRE-ADRESSE-IP/wp-admin`.

### Permaliens

Il est recommandé de modifier les paramètres permaliens pour rendre vos URL plus facilement mémorables. Pour ce faire, connectez-vous à WordPress et aller sur votre tableau de bord. Allez à `Settings` puis `Permalinks`. Sélectionnez l'option `Post name` et cliquez sur `Save Changes`. Après l'enregistrement, vous serez invité à mettre à jour votre fichier `.htaccess`. Vous n'en avez probablement pas encore un, par conséquent ajoutez-en un dans `/var/www/` en tapant `nano .htaccess`. Notez que ceci est un fichier caché, donc il commence par un point. Puis collez-y les contenus suivants :

```
<IfModule mod_rewrite.c>
RewriteEngine On
RewriteBase /
RewriteRule ^index\.php$ - [L]
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule . /index.php [L]
</IfModule>
```

Enregistrez le fichier et revenez à la page d'accueil du site. Cliquez sur le titre ou le lien de la page d'échantillon et vous verrez probablement une page d'erreur `Not Found`. C'est parce que le `rewrite` module n'a pas été activé dans Apache. Pour l'activer, entrez `sudo a2enmod rewrite`.


Vous aurez également besoin de dire à l'hôte virtuel du site d'autoriser la réécriture des requêtes. Pour ce faire,  éditez le fichier d'hôte virtuel ( avec les permissions root ) : `sudo nano /etc/apache2/sites-available/default`; Par ailleurs, changez le réglage `AllowOverride` de la ligne 11 (dans le bloc `<Directory /var/www/>`) de `None` à `All`. Sauvegarder le fichier puis redémarrez Apache avec `sudo service apache2 restart`. Une fois redémarré, rafraîchissez la page et elle devrait se charger correctement. DOrénavant, chaque article aura une url de type `/hello-world/` au lieu de `/?p=123`, et chaque page aura une URL de type `/sample-page/` au lieu de `/?page_id=2`.

### Personnalisation

WordPress est très personnalisable. En cliquant sur le nom de votre site dans la bannière WordPress le long du haut de la page (lorsque vous êtes connecté), vous serez redirigé vers votre tableau de bord. De là, vous pouvez changer le thème, ajouter des pages et des articles, modifier le menu, ajouter des plugins et beaucoup plus. Ceci est juste un avant-goût de ce que vous pouvez obtenir de cette intéressante configuration serveur Web du Raspberry Pi.