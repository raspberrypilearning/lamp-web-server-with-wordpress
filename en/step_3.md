## Set up an Apache web server

Apache is a popular web server application you can install on the Raspberry Pi to allow it to serve web pages.

On its own, Apache can serve HTML files over HTTP. With additional modules it can serve dynamic web pages using scripting languages such as PHP.

### Install Apache

+ Open a terminal window by selecting **Accessories** > **Terminal** from the menu.

+ Install the `apache2` package by typing the following command into the terminal and pressing <kbd>Enter<kbd>:

```bash
sudo apt-get install apache2 -y
```

![install apache](images/install_apache.png)

### Test the web server

By default, Apache puts a test HTML file in the web folder that you will be able to view from your Pi or another computer on your network. 

Open the Apache default web page on your Raspberry Pi:

+ Open Chromium by selecting **Internet** > **Chromium Web Browser** from the menu.

+ Enter the address `http://localhost`.

You should see this in your browser window:

![Apache it works](images/apache-it-works.png)

This means you have Apache working!

You will also be able to open this web page from any other computer on your network using the IP address of your Raspberry Pi, e.g. `http://192.168.1.10`.

To find out your Raspberry Pi's IP address, type `hostname -I` into the terminal window.  Your Raspberry Pi's [IP address](https://www.raspberrypi.org/documentation/remote-access/ip-address.md) is a really useful and will allow you to remotely access it.

### Changing the default web page

This default web page is just a HTML file on the file system. It is located at `/var/www/html/index.html`.

- Navigate to this directory in the terminal and have a look at what's inside:

```
cd /var/www/html
ls -al
```

You should see this in the window:

```bash
total 12
drwxr-xr-x  2 root root 4096 Jan  8 01:29 .
drwxr-xr-x  3 root root 4096 Jan  8 01:28 ..
-rw-r--r--  1 root root  177 Jan  8 01:29 index.html
```

This shows that there is one file in `/var/www/html/` called `index.html`. `.` refers to the directory itself `/var/www/html`, and `..` refers to the parent directory `/var/www/`.

### What the columns mean

1. The permissions of the file or directory
1. The number of files in the directory (or `1` if it's a file).
1. The user that owns the file or directory
1. The group that owns the file or directory
1. The size of the file or directory
1. The date and time of the last modification

As you can see, the `html` directory and `index.html` file are both owned by the `root` user, so you'll need to use `sudo` to edit them.

You can edit this file using mousepad:

```bash
sudo mousepad index.html
```

If you make a change to the file, save it, and refresh the browser, you will see your change appear.
