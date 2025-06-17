## Set up your WordPress Database

--- task ---

Run `mysql` in the terminal window:

--- code ---
---
language: bash
line_numbers: false
---
sudo mysql -uroot -p

--- /code ---

--- /task ---

--- task ---

Enter the root password you created when you set up the database.

You will see the message `Welcome to the MariaDB monitor` and then the `MariaDB [(none)]>` prompt.

--- /task ---

--- task ---

At the `MariaDB [(none)]>` prompt, type: **Tip:** Don't forget to type the semicolon at the end.

--- code ---
---
language: sql
line_numbers: false
---
create database wordpress;

--- /code ---



--- /task ---

If this has been successful, you should see `Query OK, 1 row affected (0.00 sec)`.

--- task ---

At the MariaDB prompt, grant database privileges to the root user. Change `YOURPASSWORD` to the password you created before.

--- code ---
---
language: sql
line_numbers: false
---

GRANT ALL PRIVILEGES ON wordpress.* TO 'root'@'localhost' IDENTIFIED BY 'YOURPASSWORD';

--- /code ---

--- /task ---

--- task ---

For the changes to take effect, you will need to flush the database privileges:

--- code ---
---
language: sql
line_numbers: false
---
FLUSH PRIVILEGES;

--- /code ---

--- /task ---

--- task ---

Exit the MariaDB prompt with <kbd>Ctrl</kbd> + <kbd>D</kbd>.

--- /task ---

--- task ---

Restart your Raspberry Pi by typing this command in the terminal:

--- code ---
---
language: bash
line_numbers: false
---
sudo reboot

--- /code ---

--- /task ---
