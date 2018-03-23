## Set up your WordPress Database

#### Set up MySQL/MariaDB

To get your WordPress site set up, you need a database. This is where MySQL and MariaDB come in!

+ Run the MySQL secure installation command in the terminal window.

```bash
sudo mysql_secure_installation
```

+ You will be asked `Enter current password for root (enter for none):` — press **Enter**.

+ Type in **Y** and press **Enter** to `Set root password?`.

+ Type in a password at the `New password:` prompt, and press **Enter**. **Important:** remember this root password, as you will need it later to set up WordPress.

+ Type in **Y** to `Remove anonymous users`.

+ Type in **Y** to `Disallow root login remotely`.

+ Type in **Y** to `Remove test database and access to it`.

+ Type in **Y** to `Reload privilege tables now`.

When complete, you will see the message `All done!` and `Thanks for using MariaDB!`.

#### Create the WordPress database

+ Run `mysql` in the terminal window:

```bash 
sudo mysql -uroot -p
```

+ Enter the root password you created.

You will be greeted by the message `Welcome to the MariaDB monitor`.

+ Create the database for your WordPress installation at the `MariaDB [(none)]>` prompt using:

```
create database wordpress;
```

  Note the semi-colon ending the statement. 

If this has been successful, you should see this:

```
Query OK, 1 row affected (0.00 sec)
```

![create database](images/create-database.png)

+ Now grant database privileges to the root user. **Note:** you will need to enter your own password after `IDENTIFIED BY`.

```
GRANT ALL PRIVILEGES ON wordpress.* TO 'root'@'localhost' IDENTIFIED BY 'YOURPASSWORD';
```

+ Flush the database privileges:

```
FLUSH PRIVILEGES;
```

+ Exit out of the MariaDB prompt with `Ctrl + D`.

