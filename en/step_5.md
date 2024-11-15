## Install MariaDB

MariaDB is a popular database engine. Like PHP, it's widely used on web servers, which is why projects like WordPress use it, and why those projects are so popular.


--- task ---

Type this command to install the MariaDB Server and PHP-MySQL packages:

--- code ---
---
language: bash
line_numbers: false
---
sudo apt-get install mariadb-server php-mysql -y
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
