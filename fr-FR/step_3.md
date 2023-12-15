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
  Cela montre qu'il y a un fichier dans <code>/var/www/html/</code> appelé <code>index.html</code> . <code>.</code> fait référence au répertoire lui-même <code>/var/www/html</code>, et <code>..</code> fait référence au répertoire parent <code>/var/www/</code>.
</p>

<h3 spaces-before="0">
  Ce que signifient les colonnes
</h3>

<ol start="1">
  <li>
    Les permissions du fichier ou du répertoire
  </li>
  
  <li>
    Le nombre de fichiers dans le répertoire (ou <code>1</code> si c'est un fichier).
  </li>
  
  <li>
    L'utilisateur propriétaire du fichier ou du répertoire
  </li>
  
  <li>
    Le groupe propriétaire du fichier ou du répertoire
  </li>
  
  <li>
    La taille du fichier ou du répertoire
  </li>
  
  <li>
    La date et l'heure de la dernière modification
  </li>
</ol>

<p spaces-before="0">
  peut voir, le répertoire <code>html</code> et le fichier <code>index.html</code> appartiennent tous deux à l'utilisateur <code>root</code> , vous devrez donc utiliser <code>sudo</code> pour les modifier.
</p>

<p spaces-before="0">
  Vous pouvez modifier ce fichier à l'aide du tapis de souris :
</p>

<pre><code class="bash">sudo mousepad index.html
</code></pre>

<p spaces-before="0">
  Si vous apportez une modification au fichier, enregistrez-le et actualisez le navigateur, vous verrez votre modification apparaître.
</p>
