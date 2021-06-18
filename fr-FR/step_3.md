## Configurer un serveur Web Apache

Apache est un serveur Web populaire que tu peux installer sur le Raspberry Pi pour lui permettre d'héberger des pages Web.

À lui seul, Apache peut servir des fichiers HTML sur HTTP. Avec des modules supplémentaires, il peut servir des pages Web dynamiques en utilisant des langages de script tels que PHP.

### Installer Apache

+ Ouvre un terminal en sélectionnant **Accessoires** > **Terminal** dans le menu.

+ Installe le paquet `apache2` en tapant la commande suivante dans le terminal et en appuyant sur <kbd>Entrée<kbd> : </p></li> </ul> 
  
  <pre><code class="bash">sudo apt-get install apache2 -y
</code></pre>
  
  <p spaces-before="0">
    <img src="images/install_apache.png" alt="install apache" />
  </p>

<h3 spaces-before="0">
  Teste le serveur Web
</h3>

<p spaces-before="0">
  Par défaut, Apache place un fichier HTML de test dans le dossier Web que tu pourras visualiser depuis ton Pi ou un autre ordinateur de ton réseau.
</p>

<p spaces-before="0">
  Ouvre la page Web par défaut d'Apache sur ton Raspberry Pi :
</p>

<ul>
  <li>
    <p spaces-before="0">
      Ouvre Chrome en sélectionnant <strong x-id="1">Internet</strong> > <strong x-id="1">Navigateur Web Chromium</strong> dans le menu.
    </p>
  </li>
  <li>
    <p spaces-before="0">
      Entre l'adresse <code>http://localhost</code> .
    </p>
  </li>
</ul>

<p spaces-before="0">
  Tu devrais voir ceci dans la fenêtre de ton navigateur :
</p>

<p spaces-before="0">
  <img src="images/apache-it-works.png" alt="Apache it works" />
</p>

<p spaces-before="0">
  Cela signifie que Apache fonctionne !
</p>

<p spaces-before="0">
  Tu pourras également ouvrir cette page Web depuis n'importe quel autre ordinateur de ton réseau en utilisant l'adresse IP de ton Raspberry Pi, par exemple <code>http://192.168.1.10</code> .
</p>

<p spaces-before="0">
  Pour connaître l'adresse IP de ton Raspberry Pi, tape <code>hostname -I </code> dans la fenêtre du terminal.  <a href="https://www.raspberrypi.org/documentation/remote-access/ip-address.md">L'adresse IP</a> de ton Raspberry Pi est vraiment utile et te permettras d'y accéder à distance.
</p>

<h3 spaces-before="0">
  Modification de la page Web par défaut
</h3>

<p spaces-before="0">
  Cette page Web par défaut n'est qu'un fichier HTML sur le système de fichiers. Il se trouve à <code>/var/www/html/index.html</code> .
</p>

<ul>
  <li>
    Accède à ce répertoire dans le terminal et regarde ce qu'il contient :
  </li>
</ul>

<pre><code>cd /var/www/html
ls -al
</code></pre>

<p spaces-before="0">
  Tu devrais voir ceci dans la fenêtre :
</p>

<pre><code class="bash">total 12
drwxr-xr-x 2 root root 4096 Jan 8 01:29.
drwxr-xr-x  3 root root 4096 Jan  8 01:28 ..
-rw-r-r-- 1 root root 177 Jan  8 01:29 index.html
</code></pre>

<p spaces-before="0">
  Cela montre qu'il y a un fichier dans <code>/var/www/html/</code> appelé <code>index.html</code> . <code>.</code> refers to the directory itself <code>/var/www/html</code>, and <code>..</code> refers to the parent directory <code>/var/www/</code>.
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
