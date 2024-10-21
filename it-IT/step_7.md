## Configura il tuo database WordPress

#### Configura MySQL/MariaDB

Per far funzionare il tuo sito WordPress, hai bisogno di un database. È qui che entrano in gioco MySQL e MariaDB!

+ Esegui il comando di installazione sicura MySQL nella finestra del terminale.

```bash
sudo mysql_secure_installation
```

+ Ti verrà chiesto `Enter current password for root (enter for none):` - premi **Invio**.

+ Digita **Y** e premi **Invio** alla domanda `Set root password?`.

+ Digita una password alla richiesta`New password:` e premi **Invio**. **Importante:** ricorda questa password di root, perché dopo ti servirà per configurare WordPress.

+ Digita **Y ** alla richiesta `Rimuovi utenti anonimi`.

+ Digita **Y ** alla richiesta `Non consentire l'accesso root da remoto`.

+ Digita **Y** alla richiesta `Rimuovi il database dei test e accedi ad esso`.

+ Digita **Y** alla richiesta `Ricarica ora le tabelle dei privilegi`.

Al termine, vedrai il messaggio `Tutto fatto!` e `Grazie per aver utilizzato MariaDB!`.

#### Crea il database WordPress

+ Esegui ` mysql ` nella finestra del terminale:

```bash 
sudo mysql -uroot -p
```

+ Inserisci la password di root che hai creato.

Verrai accolto dal messaggio `Benvenuto nel monitor di MariaDB`.

+ Crea il database per la tua installazione di WordPress al prompt `MariaDB [(none)]>` usando:

```
create database wordpress;
```

  Nota il punto e virgola alla fine del comando.

Se l'operazione ha avuto successo, dovresti vedere questo:

```
Query OK, 1 row affected (0.00 sec)
```

![crea database](images/create-database.png)

+ Ora concedi i privilegi del database all'utente root. **Nota:** dovrai inserire la tua password dopo `IDENTIFIED BY`.

```
GRANT ALL PRIVILEGES ON wordpress.* TO 'root'@'localhost' IDENTIFIED BY 'YOURPASSWORD';
```

+ Per rendere effettive le modifiche, è necessario ricaricare i privilegi del database:

```
FLUSH PRIVILEGES;
```

+ Esci dal prompt di MariaDB con <kbd>Ctrl</kbd> + <kbd>D</kbd>.

+ Riavvia il tuo Raspberry Pi:

```
sudo reboot
```
