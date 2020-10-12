## Ρύθμισε ένα διακομιστή ιστού Apache

Ο Apache είναι μια δημοφιλής εφαρμογή διακομιστή ιστού που μπορείς να εγκαταστήσεις στο Raspberry Pi για να επιτρέψεις την προβολή ιστοσελίδων.

Από μόνος του ο Apache μπορεί να εξυπηρετεί αρχεία HTML μέσω HTTP. Με πρόσθετα αρθρώματα μπορεί να εξυπηρετήσει δυναμικές ιστοσελίδες χρησιμοποιώντας γλώσσες δέσμης ενεργειών όπως η PHP.

### Εγκατέστησε τον Apache

+ Άνοιξε ένα παράθυρο τερματικού επιλέγοντας **Εργαλεία** > **Τερματικό** από το μενού.

+ Εγκατέστησε το πακέτο `apache2` πληκτρολογώντας την ακόλουθη εντολή στο τερματικό και πάτησε <kbd>Enter<kbd>:</p></li></ul> 
  
  <pre><code class="bash">sudo apt-get install apache2 -y
</code></pre>
  
  <p spaces-before="0">
    <img src="images/install_apache.png" alt="install apache" />
  </p>

<h3 spaces-before="0">
  Δοκίμασε τον διακομιστή ιστού
</h3>

<p spaces-before="0">
  Από προεπιλογή, ο Apache τοποθετεί ένα δοκιμαστικό αρχείο HTML στο φάκελο ιστού που θα μπορείς να δεις από το Pi ή από άλλον υπολογιστή στο δίκτυό σου.
</p>

<p spaces-before="0">
  Άνοιξε την προεπιλεγμένη ιστοσελίδα του Apache στο Raspberry Pi:
</p>

<ul>
  <li>
    <p spaces-before="0">
      Άνοιξε το Chromium επιλέγοντας <strong x-id="1">Διαδίκτυο</strong> > <strong x-id="1">Πρόγραμμα περιήγησης ιστού Chromium</strong> από το μενού.
    </p>
  </li>
  <li>
    <p spaces-before="0">
      Πληκτρολόγησε τη διεύθυνση <code>http://localhost</code>.
    </p>
  </li>
</ul>

<p spaces-before="0">
  Θα πρέπει να δεις αυτό στο παράθυρο του προγράμματος περιήγησής σου:
</p>

<p spaces-before="0">
  <img src="images/apache-it-works.png" alt="Apache it works" />
</p>

<p spaces-before="0">
  Αυτό σημαίνει ότι ο Apache λειτουργεί!
</p>

<p spaces-before="0">
  Θα μπορείς επίσης να ανοίξεις αυτήν την ιστοσελίδα από οποιονδήποτε άλλο υπολογιστή στο δίκτυό σου χρησιμοποιώντας τη διεύθυνση IP του Raspberry Pi, π.χ. <code>http://192.168.1.10</code>.
</p>

<p spaces-before="0">
  Για να μάθεις τη διεύθυνση IP του Raspberry Pi, πληκτρολόγησε στο παράθυρο του τερματικού την εντολή <code>hostname -I</code>.  Η <a href="https://www.raspberrypi.org/documentation/remote-access/ip-address.md">διεύθυνση IP</a> του Raspberry Pi είναι πραγματικά χρήσιμη και θα σου επιτρέψει να έχεις απομακρυσμένη πρόσβαση σε αυτό.
</p>

<h3 spaces-before="0">
  Άλλαξε την προεπιλεγμένη ιστοσελίδα
</h3>

<p spaces-before="0">
  Αυτή η προεπιλεγμένη ιστοσελίδα είναι απλώς ένα αρχείο HTML στο σύστημα αρχείων. Βρίσκεται στη διεύθυνση <code>/var/www/html/index.html</code>.
</p>

<ul>
  <li>
    Μετακινήσου σε αυτόν τον κατάλογο στο τερματικό και ρίξε μια ματιά στο εσωτερικό του:
  </li>
</ul>

<pre><code>cd /var/www/html
ls -al
</code></pre>

<p spaces-before="0">
  Θα πρέπει να το δείς αυτό στο παράθυρο:
</p>

<pre><code class="bash">total 12
drwxr-xr-x  2 root root 4096 Jan  8 01:29 .
drwxr-xr-x  3 root root 4096 Jan  8 01:28 ..
-rw-r--r--  1 root root  177 Jan  8 01:29 index.html
</code></pre>

<p spaces-before="0">
  Αυτό δείχνει ότι υπάρχει ένα αρχείο στον κατάλογο <code>/var/www/html/</code> που ονομάζεται <code>index.html</code>. <code>.</code> refers to the directory itself <code>/var/www/html</code>, and <code>..</code> refers to the parent directory <code>/var/www/</code>.
</p>

<h3 spaces-before="0">
  What the columns mean
</h3>

<ol start="1">
  <li>
    The permissions of the file or directory
  </li>
  
  <li>
    The number of files in the directory (or <code>1</code> if it's a file).
  </li>
  
  <li>
    The user that owns the file or directory
  </li>
  
  <li>
    The group that owns the file or directory
  </li>
  
  <li>
    The size of the file or directory
  </li>
  
  <li>
    The date and time of the last modification
  </li>
</ol>

<p spaces-before="0">
  As you can see, the <code>html</code> directory and <code>index.html</code> file are both owned by the <code>root</code> user, so you'll need to use <code>sudo</code> to edit them.
</p>

<p spaces-before="0">
  You can edit this file using mousepad:
</p>

<pre><code class="bash">sudo mousepad index.html
</code></pre>

<p spaces-before="0">
  If you make a change to the file, save it, and refresh the browser, you will see your change appear.
</p>
