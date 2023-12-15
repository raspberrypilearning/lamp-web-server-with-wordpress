## Pobierz WordPress

Możesz pobrać WordPress z [wordpress.org](http://wordpress.org/) za pomocą polecenia `wget`. Dla ułatwienia, kopia najnowszej wersji WordPress jest zawsze dostępna na [wordpress.org/latest.tar.gz](https://wordpress.org/latest.tar.gz), dzięki czemu możesz pobrać najnowszą wersję bez konieczności wyszukiwania jej na stronie internetowej. W chwili pisania tego tekstu jest to wersja 4.5.

--- collapse ---

---
title: Co to jest plik .tar.gz?
---

Jeśli się zastanawiasz, `.tar.gz` oznacza „archiwum tar skompresowane za pomocą gzip”. `gzip` to narzędzie do kompresji plików, co oznacza zmniejszenie ich rozmiaru, aby można je było łatwiej przechowywać lub dystrybuować. `.tar` oznacza tarball, czyli format pliku komputerowego, który łączy i kompresuje wiele plików. Oprogramowanie jest często dostępne do pobrania w formacie `.tar.gz`, ponieważ pobieranie tarballa jest znacznie szybsze niż pobieranie nieskompresowanych plików.

--- /collapse ---

+ Zmień katalog na `/var/www/html/` i usuń wszystkie pliki w folderze.

```bash
cd /var/www/html/
sudo rm *
```

+ Pobierz WordPress za pomocą `wget`.

```bash
sudo wget http://wordpress.org/latest.tar.gz
```

+ Rozpakuj archiwum tarball WordPress, aby uzyskać dostęp do plików WordPress.

```bash
sudo tar xzf latest.tar.gz
```

+ Przenieś zawartość rozpakowanego katalogu `wordpress` do bieżącego katalogu.

```bash
sudo mv wordpress/* .
```

+ Uporządkuj, usuwając tarballa i teraz pusty katalog `wordpress`.

```bash
sudo rm -rf wordpress latest.tar.gz
```

- Uruchamianie polecenia `ls` lub `tree -L 1` pokaże teraz zawartość projektu WordPress:

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

To jest źródło domyślnej instalacji WordPress. Pliki, które edytujesz w celu dostosowania instalacji, znajdują się w katalogu `wp-content`.

+ Powinnaś teraz zmienić własność wszystkich tych plików na użytkownika Apache:

```bash
sudo chown -R www-data: .
```
