## Install MariaDB

MariaDB is a popular database engine. PHP is een zeer populaire taal op internet: grote projecten zoals Facebook en Wikipedia zijn geschreven in PHP.


--- task ---

Installeer het PHP-pakket met de volgende opdracht:

--- code ---
---
language: bash
line_numbers: false
---
sudo apt install mariadb-server php-mysql -y

--- /code ---

--- /task ---

--- task ---

Now restart Apache:

--- code ---
---
language: bash
line_numbers: false
---
sudo service apache2 restart

--- /code ---

--- /task ---

### Set up

--- task ---

Run the MySQL secure installation command in the terminal window.

--- code ---
---
language: bash
line_numbers: false
---
sudo mysql_secure_installation

--- /code ---

--- /task ---

--- task ---

Go through the setup wizard using the following answers:

+ `Enter current password for root (enter for none):` — press **Enter**.

+ `Switch to unix_socket authentication [Y/n]` - Type in **N** and press **Enter**

+ `Change the root password?` - Type in **Y** and press **Enter**

+ `New password:` - Type in a password and press **Enter**, then repeat a second time. **Important:** remember this root password, as you will need it later to set up WordPress.

+ `Remove anonymous users` - Type in **Y**

+ `Disallow root login remotely` - Type in **Y**

+ `Remove test database and access to it` - Type in **Y**

+ `Reload privilege tables now` - Type in **Y**

--- /task ---

When complete, you will see the message `All done!` and `Thanks for using MariaDB!`.
