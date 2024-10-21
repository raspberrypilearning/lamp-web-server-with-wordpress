## Configurazione di WordPress

+ Apri il browser web sul tuo Pi e vai all'indirizzo `http://localhost`, dovresti vedere una pagina di WordPress che chiede di scegliere la tua lingua.

![Seleziona la lingua di WordPress](images/wordpress_language.png)

+ Seleziona la tua lingua e fai clic su **Continue**.

Ti verrà presentata la schermata di benvenuto di WordPress.

![Schermata di benvenuto di WordPress](images/wordpress-welcome.png)

+ Fai clic sul pulsante **Iniziamo!**.

+ Ora compila le informazioni di base sul sito in questo modo:

```
Database Name:      wordpress
User Name:          root
Password:           <YOUR PASSWORD>
Database Host:      localhost
Table Prefix:       wp_
```

+ Fai clic su **Invia** per continuare.

+ Fai clic sul pulsante **Avvia l'installazione**.

Ci siamo quasi!

![Schermata di benvenuto di WordPress](images/wp-info.png)

Compila le informazioni: dai un titolo al tuo sito, crea un nome utente e una password e inserisci il tuo indirizzo email. Fai clic sul pulsante `Installa WordPress`, e accedi con l'account appena creato.

Ora che hai effettuato l'accesso e hai configurato il tuo sito, puoi vederlo visitando `http://localhost/wp-admin`.

--- collapse ---

---
Accedi a WordPress da un altro computer
---

Per accedere da un altro computer, apri un browser e vai su ` http://PI-IP-ADDRESS/wp-admin`, utilizzando l'indirizzo IP del tuo Raspberry Pi.

Puoi trovare l'indirizzo IP del tuo Raspberry PI usando questo comando:

```bash
hostname -I
```

![hostname](images/hostname_annotated.png)

--- /collapse ---


### Permalink facili da usare

È meglio modificare le impostazioni dei permalink per rendere l'indirizzo permanente della pagine più facili da usare.

Per farlo, accedi a WordPress e vai alla Bacheca.

+ Apri **Impostazioni**, e scegli **Permalink**.

+ Scegli l'opzione **Nome articolo** e fai clic su **Salva le modifiche**.

Dovrai abilitare il modulo `rewrite` di Apache:

```bash
sudo a2enmod rewrite
```

Dovrai anche dire all'host virtuale associato al sito di consentire la sovrascrittura delle richieste.

+ Modifica il file di configurazione del tuo host virtuale Apache:

```bash
sudo mousepad /etc/apache2/sites-available/000-default.conf
```

+ Aggiungi le seguenti righe dopo la riga 1.

```
<Directory "/var/www/html">
    AllowOverride All
</Directory>
```

- Assicurati che sia all'interno di `<VirtualHost *:80>` come in questo esempio:

```
<VirtualHost *:80>
    <Directory "/var/www/html">
        AllowOverride All
    </Directory>
    ...
```

+ Salva il file ed esci.

+ Riavvia Apache.

```bash
sudo service apache2 restart
```

### Personalizzazione

WordPress è molto personalizzabile. Facendo clic sul nome del tuo sito nel banner WordPress in cima alla pagina (quando sei autenticato), verrai portato alla Bacheca. Da lì, puoi cambiare il tema, aggiungere pagine e post, modificare il menu, aggiungere plug-in e molto altro. Questo è solo un assaggio delle cose interessanti che si possono fare con il web server di Raspberry Pi.
