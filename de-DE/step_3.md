## Richte einen Apache Webserver ein

Apache ist eine beliebte Webserveranwendung, die du auf dem Raspberry Pi installieren kannst, damit er Webseiten bereitstellen kann.

Apache kann selbstständig HTML-Dateien über HTTP bereitstellen. Mit zusätzlichen Modulen kann es dynamische Webseiten mit Skriptsprachen wie PHP bereitstellen.

### Apache installieren

+ Öffne ein Terminal-Fenster, indem du im Menü **Zubehör** > **Terminal** auswählst.

+ Installiere das `apache2` Paket, indem du den folgenden Befehl in das Terminal tippst und dann <kbd>Enter<kbd> drückst:</p></li> </ul> 
  
  <pre><code class="bash">sudo apt-get install apache2 -y
</code></pre>
  
  <p spaces-before="0">
    <img src="images/install_apache.png" alt="install apache" />
  </p>

<h3 spaces-before="0">
  Teste den Webserver
</h3>

<p spaces-before="0">
  Standardmäßig legt Apache eine Test-HTML-Datei in den Web-Ordner, die du von deinem Pi oder einem anderen Computer in deinem Netzwerk ansehen kannst.
</p>

<p spaces-before="0">
  Öffne die Apache-Standard-Website auf deinem Raspberry Pi:
</p>

<ul>
  <li>
    <p spaces-before="0">
      Öffne Chromium, indem du <strong x-id="1">Internet</strong> > <strong x-id="1">Chromium-Webbrowser</strong> vom Menü auswählst.
    </p>
  </li>
  <li>
    <p spaces-before="0">
      Gib die Adresse <code>http://localhost</code> ein.
    </p>
  </li>
</ul>

<p spaces-before="0">
  Du solltest folgendes in deinem Browser-Fenster sehen:
</p>

<p spaces-before="0">
  <img src="images/apache-it-works.png" alt="Apache it works" />
</p>

<p spaces-before="0">
  Das heißt, dass dein Apache funktioniert!
</p>

<p spaces-before="0">
  Du kannst diese Website auch von jedem anderen Computer in deinem Netzwerk öffnen, indem du die IP-Adresse deines Raspberry Pi verwendest, z.B.: <code>http://192.168.1.10</code>.
</p>

<p spaces-before="0">
  Um die IP-Adresse deines Raspberry Pi herauszufinden, tippe <code>hostname -I</code> in das Terminal-Fenster.  Die <a href="https://www.raspberrypi.org/documentation/remote-access/ip-address.md">IP-Adresse</a> deines Raspberry Pi ist wirklich nützlich und ermöglicht es dir aus der Ferne darauf zuzugreifen.
</p>

<h3 spaces-before="0">
  Die Standard-Website ändern
</h3>

<p spaces-before="0">
  Diese Standard-Website ist nur eine HTML-Datei im Dateisystem. Sie befindet sich in <code>/var/www/html/index.html</code>.
</p>

<ul>
  <li>
    Navigiere im Terminal zu diesem Verzeichnis und schau was sich darin befindet:
  </li>
</ul>

<pre><code>cd /var/www/html
ls -al
</code></pre>

<p spaces-before="0">
  Du solltest folgendes im Fenster sehen:
</p>

<pre><code class="bash">total 12
drwxr-xr-x  2 root root 4096 Jan  8 01:29 .
drwxr-xr-x  3 root root 4096 Jan  8 01:28 ..
-rw-r--r--  1 root root  177 Jan  8 01:29 index.html
</code></pre>

<p spaces-before="0">
  Das zeigt, dass sich in <code>/var/www/html/</code> eine Datei namens <code>index.html</code> befindet. <code>.</code> refers to the directory itself <code>/var/www/html</code>, and <code>..</code> refers to the parent directory <code>/var/www/</code>.
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
