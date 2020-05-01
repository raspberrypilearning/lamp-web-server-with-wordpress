## Κάνε λήψη του WordPress

Μπορείς να κάνεις λήψη του WordPress από την [wordpress.org](http://wordpress.org/) χρησιμοποιώντας την εντολή `wget`. Ένα αντίγραφο της τελευταίας έκδοσης του WordPress είναι πάντα διαθέσιμο στη διεύθυνση [wordpress.org/latest.tar.gz](https://wordpress.org/latest.tar.gz), ώστε να μπορείς να αποκτήσεις την πιο πρόσφατη έκδοση χωρίς να χρειάζεται να την αναζητήσεις στον ιστότοπο. Τη στιγμή της σύνταξης, υπάρχει η έκδοση 4.5.

--- collapse ---

---
title: Τι είναι ένα αρχείο .tar.gz;
---

Σε περίπτωση που αναρωτιέσαι, το `.tar.gz` σημαίνει «gzip-συμπιεσμένο αρχείο tar». Το `gzip` είναι ένα εργαλείο συμπίεσης αρχείων, που σημαίνει μείωση του μεγέθους τους ώστε να μπορούν να αποθηκευτούν ή να διανεμηθούν πιο εύκολα. Το `.tar` σημαίνει tarball, που είναι μια μορφή αρχείου του υπολογιστή που συνδυάζει και συμπιέζει πολλά αρχεία. Το λογισμικό είναι συχνά διαθέσιμο για λήψη σε μορφή `.tar.gz`, επειδή η λήψη ενός tarball είναι πολύ πιο γρήγορη από τη λήψη των μη συμπιεσμένων αρχείων.

--- /collapse ---

+ Άλλαξε τον κατάλογο στον `/var/www/html/` και διέγραψε όλα τα αρχεία στο φάκελο.

```bash
cd /var/www/html/
sudo rm *
```

+ Κάνε λήψη του WordPress χρησιμοποιώντας την εντολή `wget`.

```bash
sudo wget http://wordpress.org/latest.tar.gz
```

+ Αποσυμπίεσε το WordPress tarball για να λάβεις τα αρχεία του WordPress.

```bash
sudo tar xzf latest.tar.gz
```

+ Μετακίνησε τα περιεχόμενα του αποσυμπιεσμένου καταλόγου `wordpress` στον τρέχοντα κατάλογο.

```bash
sudo mv wordpress/* .
```

+ Τακτοποίησε λίγο αφαιρώντας το tarball και τον άδειο κατάλογο `wordpress`.

```bash
sudo rm -rf wordpress latest.tar.gz
```

- Η εκτέλεση τώρα της εντολής `ls` ή της `tree -L 1` θα σου δείξει το περιεχόμενο του έργου WordPress:

```bash
.
├── index.php
├── license.txt
├── readme.html
├── wp-activate.php
├── wp-admin
├── wp-blog-header.php
├── wp-comments-post.php
├── wp-config-sample.php
├── wp-content
├── wp-cron.php
├── wp-includes
├── wp-links-opml.php
├── wp-load.php
├── wp-login.php
├── wp-mail.php
├── wp-settings.php
├── wp-signup.php
├── wp-trackback.php
└── xmlrpc.php

3 κατάλογοι, 16 αρχεία
```

Αυτή είναι η πηγή μιας προεπιλεγμένης εγκατάστασης WordPress. Τα αρχεία για επεξεργασία ώστε να προσαρμόσεις την εγκατάστασή σου ανήκουν στον φάκελο `wp-content`.

+ Τώρα πρέπει να αλλάξεις την ιδιοκτησία όλων αυτών των αρχείων στον χρήστη Apache:

```bash
sudo chown -R www-data: .
```
