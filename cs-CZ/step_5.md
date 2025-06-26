## Stažení nástroje WordPress

WordPress je oblíbený nástroj používaný k rychlé tvorbě webových stránek nebo blogů s snadno použitelným editorem pro tvorbu nového obsahu.


--- task ---

V terminálu se ujistěti, že jsi stále v adresáři `/var/www/html/`

--- code ---
---
language: bash
line_numbers: false
---
cd /var/www/html/

--- /code ---

--- /task ---

--- task ---

Smaž všechny soubory ve složce.

--- code ---
---
language: bash
line_numbers: false
---
sudo rm *

--- /code ---

--- /task ---

--- task ---

Zadej tento příkaz pro stažení WordPressu

--- code ---
---
language: bash
line_numbers: false
---
sudo wget http://wordpress.org/latest.tar.gz

--- /code ---

--- /task ---

--- task ---

Rozbal software WordPress:

--- code ---
---
language: bash
line_numbers: false
---
sudo tar xzf latest.tar.gz

--- /code ---

--- /task ---

--- task ---

Přesuň obsah extrahovaného adresáře `wordpress` do aktuálního adresáře. **Tip:** Ujisti se, že zadáváš celý příkaz včetně tečky.

--- code ---
---
language: bash
line_numbers: false
---
sudo mv wordpress/* .

--- /code ---

--- /task ---

--- task ---

Smaž stažený soubor a prázdný adresář`wordpress`.

--- code ---
---
language: bash
line_numbers: false
---
sudo rm -rf wordpress latest.tar.gz

--- /code ---

--- /task ---

---task ---

Změň vlastnictví všech těchto souborů na uživatele Apache: **Tip:** Ujisti se, že jsi zadal celý příkaz včetně tečky.

--- code ---
---
language: bash
line_numbers: false
---
sudo chown -R www-data: .

--- /code ---

--- /task ---
