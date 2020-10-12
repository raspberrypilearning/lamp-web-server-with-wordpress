## Set up an Apache web server

Apache is a popular web server application you can install on the Raspberry Pi to allow it to serve web pages.

On its own, Apache can serve HTML files over HTTP. With additional modules it can serve dynamic web pages using scripting languages such as PHP.

### Install Apache

+ Open a terminal window by selecting **Accessories** > **Terminal** from the menu.

+ Install the `apache2` package by typing the following command into the terminal and pressing <kbd>Enter<kbd>:</p></li> </ul> 
  
  <pre><code class="bash">sudo apt-get install apache2 -y
</code></pre>
  
  <p spaces-before="0">
    <img src="images/install_apache.png" alt="install apache" />
  </p>

<h3 spaces-before="0">
  Test the web server
</h3>

<p spaces-before="0">
  By default, Apache puts a test HTML file in the web folder that you will be able to view from your Pi or another computer on your network.
</p>

<p spaces-before="0">
  Open the Apache default web page on your Raspberry Pi:
</p>

<ul>
  <li>
    <p spaces-before="0">
      Open Chromium by selecting <strong x-id="1">Internet</strong> > <strong x-id="1">Chromium Web Browser</strong> from the menu.
    </p>
  </li>
  <li>
    <p spaces-before="0">
      Enter the address <code>http://localhost</code>.
    </p>
  </li>
</ul>

<p spaces-before="0">
  You should see this in your browser window:
</p>

<p spaces-before="0">
  <img src="images/apache-it-works.png" alt="Apache it works" />
</p>

<p spaces-before="0">
  This means you have Apache working!
</p>

<p spaces-before="0">
  You will also be able to open this web page from any other computer on your network using the IP address of your Raspberry Pi, e.g. <code>http://192.168.1.10</code>.
</p>

<p spaces-before="0">
  To find out your Raspberry Pi's IP address, type <code>hostname -I</code> into the terminal window.  Your Raspberry Pi's <a href="https://www.raspberrypi.org/documentation/remote-access/ip-address.md">IP address</a> is a really useful and will allow you to remotely access it.
</p>

<h3 spaces-before="0">
  Changing the default web page
</h3>

<p spaces-before="0">
  This default web page is just a HTML file on the file system. It is located at <code>/var/www/html/index.html</code>.
</p>

<ul>
  <li>
    Navigate to this directory in the terminal and have a look at what's inside:
  </li>
</ul>

<pre><code>cd /var/www/html
ls -al
</code></pre>

<p spaces-before="0">
  You should see this in the window:
</p>

<pre><code class="bash">total 12
drwxr-xr-x  2 root root 4096 Jan  8 01:29 .
drwxr-xr-x  3 root root 4096 Jan  8 01:28 ..
-rw-r--r--  1 root root  177 Jan  8 01:29 index.html
</code></pre>

<p spaces-before="0">
  This shows that there is one file in <code>/var/www/html/</code> called <code>index.html</code>. <code>.</code> refers to the directory itself <code>/var/www/html</code>, and <code>..</code> refers to the parent directory <code>/var/www/</code>.
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
