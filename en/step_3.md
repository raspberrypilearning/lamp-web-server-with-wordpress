## Set up an Apache web server

Apache is a popular web server application you can install on the Raspberry Pi to allow it to serve web pages.

On its own, Apache can serve HTML files over HTTP. With additional modules it can serve dynamic web pages using scripting languages such as PHP.

### Install Apache

--- task ---
Open a terminal window by selecting **Accessories** > **Terminal** from the menu.
--- /task ---

--- task ---
Type the following command into the terminal and press <kbd>Enter</kbd> to install `apache2`

```bash
sudo apt-get install apache2 -y
```

**Tip:** If you see an error, make sure you are using the latest version of Raspberry Pi OS.
--- /task ---

--- task ---
Type the following command to see your Raspberry Pi's IP address:

```bash
hostname -I
```
--- /task ---

### Test the web server

By default, Apache puts a test HTML file in the web folder that you will be able to view from your Pi or another computer on your network. 

--- task ---
Open Chromium by selecting **Internet** > **Chromium Web Browser** from the menu.
--- /task ---

--- task ---
Type `localhost` in the address bar.
--- /task ---

You should see this in your browser window:

![Apache it works](images/apache-it-works.png)

This means you have Apache working!

### Changing the default web page

This default web page is just a HTML file on the file system. It is located at `/var/www/html/index.html`.

--- task ---
Type the following command in the terminal to change to the directory containing the HTML file:
```bash
cd /var/www/html
```
--- /task ---

--- task ---
Open the `index.html` file using mousepad

```bash
sudo mousepad index.html
```
--- /task ---

--- task ---
Make a change to the file, then save it and refresh the browser. You will see your change appear on the web page.
--- /task ---

--- collapse ---
--- 
title: Access the page from another device on the network
---

You can open your web page from any other computer on your network, using the IP address of your Raspberry Pi, e.g. `http://192.168.1.10`.

To find out your Raspberry Pi's IP address, type `hostname -I` into the terminal window.  

--- /collapse ---
