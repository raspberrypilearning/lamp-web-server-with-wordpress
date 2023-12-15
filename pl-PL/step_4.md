## Zainstaluj PHP

PHP jest **preprocesorem**: to kod, który jest uruchamiany, gdy serwer otrzyma żądanie strony internetowej za pośrednictwem przeglądarki internetowej. Decyduje, co należy wyświetlić na stronie, a następnie wysyła tę stronę do przeglądarki. W przeciwieństwie do statycznego HTML, PHP może wyświetlać różne treści w różnych okolicznościach. Inne języki również są w stanie to zrobić, ale ponieważ WordPress jest napisany w języku PHP, zatem potrzebujemy go użyć. PHP jest bardzo popularnym językiem w Internecie: wielkie projekty, takie jak Facebook i Wikipedia, są napisane w języku PHP.

+ Zainstaluj pakiet PHP za pomocą następującego polecenia:

```bash
sudo apt-get install php -y
```

### Przetestuj PHP

+ Utwórz plik `index.php`:

```bash
sudo mousepad index.php
```

+ Umieść w nim trochę treści PHP:

```php
<? Php echo „witaj świecie”; ?>
```

+ Zapisz plik.

+ Usuń `index.html`, ponieważ ma on pierwszeństwo przed `index.php`:

```bash
sudo rm index.html
```

Odśwież swoją przeglądarkę. Powinieneś zobaczyć „witaj świecie”. Ta strona nie jest dynamiczna, ale nadal jest obsługiwana przez PHP.

![witaj świecie](images/apache-hello-world.png)

Jeśli widzisz surowy kod PHP zamiast „witaj świecie”, przeładuj i zrestartuj Apache w ten sposób:

```bash
sudo service apache2 restart
```

+ Edytuj `index.php`, żeby zawierał niektóre treści dynamiczne, na przykład:

```php
<?php echo date('Y-m-d H:i:s'); ?>
```

Lub pokaż swoje informacje PHP:

```php
<?php phpinfo(); ?>
```
