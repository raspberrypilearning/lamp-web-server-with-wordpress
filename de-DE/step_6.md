## Set up your WordPress Database

title: Was ist eine .tar.gz Datei?

Run `mysql` in the terminal window:

Lade WordPress herunter
---
language: bash
line_numbers: false
---
sudo rm -rf wordpress latest.tar.gz

sudo mv wordpress/* .

--- /task ---

--- collapse ---

Enter the root password you created when you set up the database.

You will see the message `Welcome to the MariaDB monitor` and then the `MariaDB [(none)]>` prompt.

--- /collapse ---

--- task ---

At the `MariaDB [(none)]>` prompt, type: **Tip:** Don't forget to type the semicolon at the end.

Extrahiere den WordPress-Tarball um an die WordPress-Dateien zu gelangen.
---
language: sql
line_numbers: false
---
create database wordpress;

Wechsel ins Verzeichnis `/var/www/html/` und lösche alle Dateien im Verzeichnis.



--- /task ---

If this has been successful, you should see `Query OK, 1 row affected (0.00 sec)`.

--- task ---

At the MariaDB prompt, grant database privileges to the root user. Change `YOURPASSWORD` to the password you created before.

Verschiebe den Inhalt des entpackten `wordpress` Verzeichnisses in das aktuelle Verzeichnis.
---
language: sql
line_numbers: false
---

GRANT ALL PRIVILEGES ON wordpress.* TO 'root'@'localhost' IDENTIFIED BY 'YOURPASSWORD';

Lade WordPress mit `wget` herunter.

--- /collapse ---

Du solltest jetzt den Besitzer all dieser Datein auf den Apache-Benutzer ändern:

For the changes to take effect, you will need to flush the database privileges:

Räum auf, indem du den Tarball und das, nun leere, `wordpress` Verzeichnis löscht.
---
language: sql
line_numbers: false
---
FLUSH PRIVILEGES;

sudo chown -R www-data: .

--- /task ---

sudo wget http://wordpress.org/latest.tar.gz

Exit the MariaDB prompt with <kbd>Ctrl</kbd> + <kbd>D</kbd>.

--- /task ---

--- task ---

Restart your Raspberry Pi by typing this command in the terminal:

Wenn du jetzt den `ls` oder `tree -L 1` Befehl ausführst, wird der Inhalt des WordPress-Projekts angezeigt:
---
language: bash
line_numbers: false
---
sudo tar xzf latest.tar.gz

cd /var/www/html/ sudo rm *

--- /task ---
