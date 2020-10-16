## Stel een Apache-webserver in

Apache is een populaire webserver-applicatie die je op de Raspberry Pi kunt installeren om webpagina's te kunnen weergeven.

Op zichzelf kan Apache HTML-bestanden via HTTP doorgeven. Met extra modules kan het dynamische webpagina's doorgeven met scripttalen zoals PHP.

### Installeer Apache

+ Open een terminalvenster door **Hulpmiddelen** > **Terminal** te selecteren in het menu.

+ Installeer het `apache2` pakket door de volgende opdracht in de terminal te typen en op <kbd>Enter<kbd> te drukken: 
  
```bash
sudo apt-get install apache2 -y
```
  
![install apache](images/install_apache.png)


###  Test de webserver

Apache plaatst standaard een HTML-testbestand in de webmap die je vanaf je Pi of een andere computer in je netwerk kunt bekijken.

Open de standaard Apache-webpagina op je Raspberry Pi:

+ Open Chromium door <strong x-id="1">Internet</strong> > <strong x-id="1">Chromium Web Browser</strong> te selecteren in het menu.

+ Voer het adres <code>http://localhost</code> in.

Je zou dit in je browservenster moeten zien:

![Apache it works](images/apache-it-works.png)


Dit betekent dat Apache werkt!

Je kunt deze webpagina ook vanaf elke andere computer in je netwerk openen met het IP-adres van je Raspberry Pi, bijvoorbeeld <code>http://192.168.1.10</code>.

Typ <code>hostname -I</code> in het terminalvenster om het IP-adres van je Raspberry Pi te achterhalen.  Het <a href="https://www.raspberrypi.org/documentation/remote-access/ip-address.md">IP-adres</a> van je Raspberry Pi is erg handig en stelt je in staat om er op afstand toegang toe te krijgen.

### De standaard webpagina wijzigen

Deze standaard webpagina is slechts een HTML-bestand op het bestandssysteem. Deze bevindt zich op <code>/var/www/html/index.html</code>.

- Navigeer naar deze map in de terminal en kijk wat erin zit:

```
cd /var/www/html
ls -al
```

Je zou dit in het venster moeten zien:

```bash
total 12
drwxr-xr-x  2 root root 4096 Jan  8 01:29 .
drwxr-xr-x  3 root root 4096 Jan  8 01:28 ..
-rw-r--r--  1 root root  177 Jan  8 01:29 index.html
```


Dit laat zien dat er één bestand is in <code>/var/www/html/</code> genaamd <code>index.html</code>. <code>.</code> verwijst naar de map  <code>/var/www/html</code> zelf, en <code>..</code> verwijst naar de bovenliggende map <code>/var/www/</code>.

### Wat de kolommen betekenen

1. De rechten van het bestand of de map
1. Het aantal bestanden in de map (of <code>1</code> als het een bestand is).
1. De gebruiker die eigenaar is van het bestand of de map
1. De groep die de eigenaar is van het bestand of de map
1. De grootte van het bestand of de map
1. De datum en tijd van de laatste wijziging


Zoals je kunt zien, zijn de <code>html</code> map en het <code>index.html</code> bestand beide eigendom van de <code>root</code> gebruiker, dus je moet <code>sudo</code> gebruiken om ze te bewerken.

Je kunt dit bestand bewerken met mousepad:

```bash
sudo mousepad index.html
```

Als je een wijziging aanbrengt in het bestand, het opslaat en de browser vernieuwt, zie je je wijziging verschijnen.
