## Set up an Apache web server

Apache is a popular web server application you can install on the Raspberry Pi to allow it to serve web pages.

On its own, Apache can serve HTML files over HTTP. With additional modules it can serve dynamic web pages using scripting languages such as PHP.

### Install Apache

--- task --- Open a terminal window by selecting **Accessories** > **Terminal** from the menu. --- /task ---

--- task --- Type the following command into the terminal and press <kbd>Enter</kbd> to install `apache2`

--- code ---
---
language: bash
line_numbers: false
---
sudo apt install apache2 -y --- /code ---

**Tip:** If you see an error, make sure you are using the latest version of Raspberry Pi OS. --- /task ---


### Test the web server

By default, Apache puts a test HTML file in the web folder that you will be able to view from your Pi or another computer on your network.

--- task --- Open Chromium by selecting **Internet** > **Chromium Web Browser** from the menu. --- /task ---

--- task --- Type `localhost` in the address bar. --- /task ---

You should see this in your browser window:

![Apache it works](images/apache-it-works.png)

This means you have Apache working!

### Changing the default web page

This default web page is just a HTML file on the file system. It is located at `/var/www/html/index.html`.

--- task --- Type the following command in the terminal to change to the directory containing the HTML file:

--- code ---
---
language: bash
line_numbers: false
---
cd /var/www/html --- /code ---

--- /task ---

--- task --- Open the `index.html` file using Thonny

--- code ---
---
language: bash
line_numbers: false
---
sudo thonny index.html --- /code ---

--- /task ---

--- task --- Delete the contents of the file, then type a short message and save your changes. --- /task ---

--- task --- Go back to Chromium and refresh the browser. You will see your message appear on the web page.

--- /task ---

--- collapse ---
---
title: Access the page from another device on the network
---

You can open your web page from any other computer on your network, using the IP address of your Raspberry Pi, e.g. `http://192.168.1.10`.

To find out your Raspberry Pi's IP address, type `hostname -I` into the terminal window.

--- /collapse ---
