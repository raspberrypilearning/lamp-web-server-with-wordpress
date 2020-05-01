## Richte einen Apache Webserver ein

Apache ist eine beliebte Webserveranwendung, die du auf dem Raspberry Pi installieren kannst, damit er Webseiten bereitstellen kann.

Apache kann selbstständig HTML-Dateien über HTTP bereitstellen. Mit zusätzlichen Modulen kann es dynamische Webseiten mit Skriptsprachen wie PHP bereitstellen.

### Apache installieren

+ Öffne ein Terminal-Fenster, indem du im Menü **Zubehör** > **Terminal** auswählst.

+ Installiere das `apache2` Paket, indem du den folgenden Befehl in das Terminal tippst und dann <kbd>Enter<kbd> drückst: 
  
```bash
sudo apt-get install apache2 -y
```
  
![install apache](images/install_apache.png)


### Teste den Webserver

Standardmäßig legt Apache eine Test-HTML-Datei in den Web-Ordner, die du von deinem Pi oder einem anderen Computer in deinem Netzwerk ansehen kannst.

Öffne die Apache-Standard-Website auf deinem Raspberry Pi:

+ Öffne Chromium, indem du **Internet** > **Chromium-Webbrowser** vom Menü auswählst.

+ Gib die Adresse `http://localhost` ein.

Du solltest folgendes in deinem Browser-Fenster sehen:


![Apache it works](images/apache-it-works.png)

Das heißt, dass dein Apache funktioniert!

Du kannst diese Website auch von jedem anderen Computer in deinem Netzwerk öffnen, indem du die IP-Adresse deines Raspberry Pi verwendest, z.B.: `http://192.168.1.10`.

Um die IP-Adresse deines Raspberry Pi herauszufinden, tippe `hostname -I` in das Terminal-Fenster.  Die [IP-Adresse](https://www.raspberrypi.org/documentation/remote-access/ip-address.md) deines Raspberry Pi ist wirklich nützlich und ermöglicht es dir aus der Ferne darauf zuzugreifen.

### Die Standard-Website ändern

Diese Standard-Website ist nur eine HTML-Datei im Dateisystem. Sie befindet sich in `/var/www/html/index.html`.

- Navigiere im Terminal zu diesem Verzeichnis und schau was sich darin befindet:

```
cd /var/www/html
ls -al
```

Du solltest folgendes im Fenster sehen:


```
total 12
drwxr-xr-x  2 root root 4096 Jan  8 01:29 .
drwxr-xr-x  3 root root 4096 Jan  8 01:28 ..
-rw-r--r--  1 root root  177 Jan  8 01:29 index.html
```

Das zeigt, dass sich in `/var/www/html/` eine Datei namens `index.html` befindet. `.` verweist auf das Verzeichnis selbst `/var/www/html` und `..` verweist auf das Eltern-Verzeichnis `/var/www/`.

### Was die Spalten bedeuten

1. Die Berechtigungen der Datei oder des Verzeichnisses
1. Die Anzahl an Dateien im Verzeichnis (oder `1` falls es eine Datei ist).
1. Der Benutzer, der die Datei oder das Verzeichnis besitzt
1. Die Gruppe, die die Datei oder das Verzeichnis besitzt
1. Die Größe der Datei oder des Verzeichnisses
1. Das Datum und die Zeit der letzten Änderung

Wie du siehst, gehören das Verzeichnis `html` und die Datei `index.html` beide dem `root`-Benutzer, also musst du `sudo` nutzen um sie 

Du kannst diese Datei mit leafpad bearbeiten:

```bash
sudo leafpad index.html
```

Wenn du die Datei änderst, speichere sie und lade den Browser neu, damit die Änderungen sichtbar werden.

