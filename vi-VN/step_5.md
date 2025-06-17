## Download WordPress

WordPress is a popular tool used to quickly create a website or blog with an easy to use editor for creating new content.


--- task ---

In your terminal, make sure you are still in the directory `/var/www/html/`

--- code ---
---
language: bash
line_numbers: false
---
cd /var/www/html/

--- /code ---

--- /task ---

--- task ---

Delete all the files in the folder.

--- code ---
---
language: bash
line_numbers: false
---
sudo rm *

--- /code ---

--- /task ---

--- task ---

Type this command to download WordPress

--- code ---
---
language: bash
line_numbers: false
---
sudo wget http://wordpress.org/latest.tar.gz

--- /code ---

--- /task ---

--- task ---

Extract the WordPress software:

--- code ---
---
language: bash
line_numbers: false
---
sudo tar xzf latest.tar.gz

--- /code ---

--- /task ---

--- task ---

Move the contents of the extracted `wordpress` directory to the current directory. **Tip:** Make sure you type the whole command including the dot.

--- code ---
---
language: bash
line_numbers: false
---
sudo mv wordpress/* .

--- /code ---

--- /task ---

--- task ---

Tidy up by removing the download, and the now empty `wordpress` directory.

--- code ---
---
language: bash
line_numbers: false
---
sudo rm -rf wordpress latest.tar.gz

--- /code ---

--- /task ---

---task ---

Change the ownership of all these files to the Apache user: **Tip:** Make sure you type the whole command including the dot.

--- code ---
---
language: bash
line_numbers: false
---
sudo chown -R www-data: .

--- /code ---

--- /task ---
