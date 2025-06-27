## Nastavení databáze pro WordPress

--- task ---

V terminálovém okně spusť `mysql`:

--- code ---
---
language: bash
line_numbers: false
---
sudo mysql -uroot -p

--- /code ---

--- /task ---

--- task ---

Zadej heslo uživatele root, které jsi vytvořil při nastavení databáze.

Zobrazí se zpráva `Vítejte v monitoru MariaDB` a poté výzva `MariaDB [(none)]>`.

--- /task ---

--- task ---

V příkazovém řádku `MariaDB [(none)]>` zadej: **Tip:** Nezapomeň na konec zadat středník.

--- code ---
---
language: sql
line_numbers: false
---
create database wordpress;

--- /code ---



--- /task ---

Pokud se to podařilo, měl bys vidět `Query OK, 1 row affected (0.00 sec)`.

--- task ---

V příkazovém řádku MariaDB uděl uživateli root oprávnění k databázi. Změň `YOURPASSWORD` na heslo, které sis vytvořil dříve.

--- code ---
---
language: sql
line_numbers: false
---

GRANT ALL PRIVILEGES ON wordpress.* TO 'root'@'localhost' IDENTIFIED BY 'YOURPASSWORD';

--- /code ---

--- /task ---

--- task ---

Aby se změny projevily, budeš muset obnovit oprávnění databáze:

--- code ---
---
language: sql
line_numbers: false
---
FLUSH PRIVILEGES;

--- /code ---

--- /task ---

--- task ---

Ukonči příkazový řádek MariaDB stisknutím <kbd>Ctrl</kbd> + <kbd>D</kbd>.

--- /task ---

--- task ---

Restartuj Raspberry Pi zadáním tohoto příkazu do terminálu:

--- code ---
---
language: bash
line_numbers: false
---
sudo reboot

--- /code ---

--- /task ---
