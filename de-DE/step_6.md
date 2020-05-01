## Lade WordPress herunter

Du kannst WordPress von [wordpress.org](http://wordpress.org/), mit dem Befehl `wget`, herunterladen. Nützlicherweise ist eine Kopie der neusten Version von WordPress immer unter [wordpress.org/latest.tar.gz](https://wordpress.org/latest.tar.gz) verfügbar, so kannst du einfach die neuste Version laden, ohne auf der Website nachschauen zu müssen. Zum Zeitpunkt des Schreibens ist dies Version 4.5.

--- collapse ---
---
title: Was ist eine .tar.gz Datei?
---

Falls du dich fragst, `.tar.gz` steht für 'gzip-compressed tar archive' (also gzip-komprimiertes Tar-Archiv). `gzip` ist ein Werkzeug zum Komprimieren von Dateien, dass heißt ihre Größe zu reduzieren damit sie einfacher gespeichert oder verteilt werden können. `.tar` steht für "tarball" (engl.: "Teerklumpen"), ein Computerdateiformat, das mehrere Dateien kombiniert und komprimiert. Software steht häufig im `.tar.gz` Format zum Download zur Verfügung, da das Herunterladen eines Tarballs viel schneller ist als das Herunterladen der nicht komprimierten Dateien.

--- /collapse ---

+ Wechsel ins Verzeichnis `/var/www/html/` und lösche alle Dateien im Verzeichnis.

```bash
cd /var/www/html/
sudo rm *
```

+ Lade WordPress mit `wget` herunter.

```bash
sudo wget http://wordpress.org/latest.tar.gz
```

+ Extrahiere den WordPress-Tarball um an die WordPress-Dateien zu gelangen.

```bash
sudo tar xzf latest.tar.gz
```

+ Verschiebe den Inhalt des entpackten `wordpress` Verzeichnisses in das aktuelle Verzeichnis.

```bash
sudo mv wordpress/* .
```

+ Räum auf, indem du den Tarball und das, nun leere, `wordpress` Verzeichnis löscht.

```bash
sudo rm -rf wordpress latest.tar.gz
```

- Wenn du jetzt den `ls` oder `tree -L 1` Befehl ausführst, wird der Inhalt des WordPress-Projekts angezeigt:

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

Dies ist die Quelle einer Standardinstallation von WordPress. Die Dateien, die du bearbeitest, um deine Installation anzupassen, gehören in den Ordner `wp-content`.

+ Du solltest jetzt den Besitzer all dieser Datein auf den Apache-Benutzer ändern:

```bash
sudo chown -R www-data: .
```
