## Scarica WordPress

Puoi scaricare WordPress da [wordpress.org](http://wordpress.org/) usando il comando `wget`. Per fortuna, una copia dell'ultima versione di WordPress è sempre disponibile all'indirizzo [wordpress.org/latest.tar.gz](https://wordpress.org/latest.tar.gz) così puoi scaricare l'ultima versione senza doverla cercare sul sito. Adesso, mentre stiamo preparando questa guida, la versione più aggiornata è la 4.5.

--- collapse ---

---
Cos'è un file .tar.gz?
---

Nel caso te lo stia chiedendo, `.tar.gz` significa 'archivio tar compresso con gzip'. `gzip` è uno strumento per comprimere i file, il che significa ridurne le dimensioni in modo che possano essere archiviati o distribuiti più facilmente. `.tar` sta per tarball, che è un formato di file per computer che combina e comprime più file. Il software è spesso disponibile per il download nel formato `.tar.gz`, perché scaricare un file tar è molto più veloce che scaricare file non compressi.

--- /collapse ---

+ Vai nella directory `/var/www/html/` ed elimina tutti i file presenti.

```bash
cd /var/www/html/
sudo rm *
```

+ Scarica WordPress usando `wget`.

```bash
sudo wget http://wordpress.org/latest.tar.gz
```

+ Decomprimi il file tarball di WordPress per accedere ai file.

```bash
sudo tar xzf latest.tar.gz
```

+ Sposta il contenuto della cartella `wordpress` appena decompressa in quella corrente.

```bash
sudo mv wordpress/* .
```

+ Riordina un po' eliminando il file tarball e la directory `wordpress`, ormai vuota.

```bash
sudo rm -rf wordpress latest.tar.gz
```

- Lanciando il comando`ls` o `tree -L 1` potrai vedere i file che compongono un progetto WordPress:

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

Questa è l'origine di un'installazione WordPress predefinita. I file che modifichi per personalizzare la tua installazione appartengono alla cartella `wp-content`.

+ Ora dovresti cambiare la proprietà di tutti questi file all'utente Apache:

```bash
sudo chown -R www-data: .
```
