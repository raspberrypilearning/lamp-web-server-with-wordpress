## Instalace MariaDB

MariaDB je populární databázový engine. Stejně jako PHP se hojně používá na webových serverech, a proto ho používají projekty jako WordPress a proč jsou tyto projekty tak populární.


--- task ---

Zadej tento příkaz pro instalaci balíčků MariaDB Server a PHP-MySQL:

--- code ---
---
language: bash
line_numbers: false
---
sudo apt install mariadb-server php-mysql -y

--- /code ---

--- /task ---

--- task ---

Nyní restartuj Apache:

--- code ---
---
language: bash
line_numbers: false
---
sudo service apache2 restart

--- /code ---

--- /task ---

### Nastavení

--- task ---

Spusť příkaz pro bezpečnou instalaci MySQL v terminálovém okně.

--- code ---
---
language: bash
line_numbers: false
---
sudo mysql_secure_installation

--- /code ---

--- /task ---

--- task ---

Projdi si průvodce nastavením pomocí následujících odpovědí:

+ `Zadej aktuální heslo pro root (enter, pokud žádné nemáš):` — stiskni **Enter**.

+ `Přepnout na ověřování unix_socket [A/n]` - Zadejte **N** a stiskněte **Enter**

+ `Změnit heslo roota?` - Zadej **Y** a stiskni **Enter**

+ `Nové heslo:` - Zadej heslo a stiskni **Enter**a poté opakuj podruhé. **Důležité:** zapamatuj si toto heslo root, protože ho budeš později potřebovat k nastavení WordPressu.

+ `Odebrat anonymní uživatele` - Zadej **Y**

+ `Zakázat vzdálené přihlášení root` - Zadej **Y**

+ `Odebrat testovací databázi a přístup k ní` - Zadej **Y**

+ `Znovu načíst tabulky oprávnění` - Zadej **Y**

--- /task ---

Po dokončení se zobrazí zpráva `All done!` a `Thanks for using MariaDB!`.
