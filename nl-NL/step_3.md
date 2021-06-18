## Stel een Apache-webserver in

Apache is een populaire webserver-applicatie die je op de Raspberry Pi kunt installeren om webpagina's te kunnen weergeven.

Op zichzelf kan Apache HTML-bestanden via HTTP doorgeven. Met extra modules kan het dynamische webpagina's doorgeven met scripttalen zoals PHP.

### Installeer Apache

+ Open een terminalvenster door **Hulpmiddelen** > **Terminal** te selecteren in het menu.

+ Installeer het `apache2` pakket door de volgende opdracht in de terminal te typen en op <kbd>Enter<kbd> te drukken:</p></li> </ul> 
  
  <pre><code class="bash">sudo apt-get install apache2 -y
</code></pre>
  
  <p spaces-before="0">
    <img src="images/install_apache.png" alt="install apache" />
  </p>

<h3 spaces-before="0">
  Test de webserver
</h3>

<p spaces-before="0">
  Apache plaatst standaard een HTML-testbestand in de webmap die je vanaf je Pi of een andere computer in je netwerk kunt bekijken.
</p>

<p spaces-before="0">
  Open de standaard Apache-webpagina op je Raspberry Pi:
</p>

<ul>
  <li>
    <p spaces-before="0">
      Open Chromium door <strong x-id="1">Internet</strong> > <strong x-id="1">Chromium Web Browser</strong> te selecteren in het menu.
    </p>
  </li>
  <li>
    <p spaces-before="0">
      Voer het adres <code>http://localhost</code> in.
    </p>
  </li>
</ul>

<p spaces-before="0">
  Je zou dit in je browservenster moeten zien:
</p>

<p spaces-before="0">
  <img src="images/apache-it-works.png" alt="Apache it works" />
</p>

<p spaces-before="0">
  Dit betekent dat Apache werkt!
</p>

<p spaces-before="0">
  Je kunt deze webpagina ook vanaf elke andere computer in je netwerk openen met het IP-adres van je Raspberry Pi, bijvoorbeeld <code>http://192.168.1.10</code>.
</p>

<p spaces-before="0">
  Typ <code>hostname -I</code> in het terminalvenster om het IP-adres van je Raspberry Pi te achterhalen.  Het <a href="https://www.raspberrypi.org/documentation/remote-access/ip-address.md">IP-adres</a> van je Raspberry Pi is erg handig en stelt je in staat om er op afstand toegang toe te krijgen.
</p>

<h3 spaces-before="0">
  De standaard webpagina wijzigen
</h3>

<p spaces-before="0">
  Deze standaard webpagina is slechts een HTML-bestand op het bestandssysteem. Deze bevindt zich op <code>/var/www/html/index.html</code>.
</p>

<ul>
  <li>
    Navigeer naar deze map in de terminal en kijk wat erin zit:
  </li>
</ul>

<pre><code>cd /var/www/html
ls -al
</code></pre>

<p spaces-before="0">
  Je zou dit in het venster moeten zien:
</p>

<pre><code class="bash">total 12
drwxr-xr-x 2 root root 4096 8 januari 01:29.
drwxr-xr-x  3 root root 4096 Jan  8 01:28 ..
-rw-r--r--  1 root root  177 Jan  8 01:29 index.html
</code></pre>

<p spaces-before="0">
  Dit laat zien dat er één bestand is in <code>/var/www/html/</code> genaamd <code>index.html</code>. <code>.</code> verwijst naar de map <code>/var/www/html</code> zelf, en <code>..</code> verwijst naar de bovenliggende map <code>/var/www/</code>.
</p>

<h3 spaces-before="0">
  Wat de kolommen betekenen
</h3>

<ol start="1">
  <li>
    De rechten van het bestand of de map
  </li>
  
  <li>
    Het aantal bestanden in de map (of <code>1</code> als het een bestand is).
  </li>
  
  <li>
    De gebruiker die eigenaar is van het bestand of de map
  </li>
  
  <li>
    De groep die de eigenaar is van het bestand of de map
  </li>
  
  <li>
    De grootte van het bestand of de map
  </li>
  
  <li>
    De datum en tijd van de laatste wijziging
  </li>
</ol>

<p spaces-before="0">
  Zoals je kunt zien, zijn de <code>html</code> map en het <code>index.html</code> bestand beide eigendom van de <code>root</code> gebruiker, dus je moet <code>sudo</code> gebruiken om ze te bewerken.
</p>

<p spaces-before="0">
  Je kunt dit bestand bewerken met mousepad:
</p>

<pre><code class="bash">sudo mousepad index.html
</code></pre>

<p spaces-before="0">
  Als je een wijziging aanbrengt in het bestand, het opslaat en de browser vernieuwt, zie je je wijziging verschijnen.
</p>
