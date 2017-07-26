## Set up your WordPress Database

To get your WordPress site set up, you need a database. Run the `mysql` command in the terminal and provide your login credentials (e.g. username `root`, password `password`):

```bash
mysql -uroot -ppassword
```

Here I have provided my password (the word `password`) on the command line; there is no space between `-p` and your password.

Alternatively you can simply supply an empty `-p` flag and wait to be asked for a password:

```bash
mysql -uroot -p
```

Now you will be prompted to enter the root user password you created earlier.

Once you're connected to MySQL, you can create the database your WordPress installation will use:

```
mysql> create database wordpress;
```

Note the semi-colon ending the statement. On success you should see the following message:

```
Query OK, 1 row affected (0.00 sec)
```

Exit out of the MySQL prompt with `Ctrl + D`.

