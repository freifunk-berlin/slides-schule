# Freifunk

![freifunk](logo.png)

---

# Was ist Freifunk

* freies Netzwerk an dem jede/jeder teilnehmen kann
* ein Stück selbstgebautes Internet das allen gehört (Gemeingut)
* Wie mach ich mit:
    * einfach das Netz zum Surfen nutzen
    * das Netz mit einem WLAN-Router erweitern
    * Inhalte zur Verfügung stellen, z.B. Webseiten, Minecraft-Server
    * die Freifunk Idee verbreiten (Flyer, Sticker)
* Seite: [http://berlin.freifunk.net](http://berlin.freifunk.net)
* twitter: [http://twitter.com/freifunk_berlin](http://twitter.com/freifunk_berlin)

---

# Karte

![http://berlin.freifunk.net/network/map/](map.jpg)

---

# Impressionen vom Freifunk

![rhxb](http://simple.1just.de/files/gimgs/27_just-8108.jpg)

---

# Impressionen vom Freifunk

![rhxb](http://simple.1just.de/files/gimgs/27_just-7768.jpg)

---

# Impressionen vom Freifunk

![rhxb](http://simple.1just.de/files/gimgs/27_just-7985.jpg)

---

# Freifunk @ Andreas-Gymnasium

* Installation auf dem Dach (Turm)
* WLAN-Verbindung z.B. zum Rathaus Neukölln und zur Segenskirche (Prenzlauer Berg)
* Access Points für den Schulhof
* Aufbau mit der WLAN-AG

---

# Netzwerkgrundlagen

---

# Wifi/WLAN

* elektromagnetische Welle
    * z.B. Radio, Satellitenfernsehn, Handy, Router, Bluetooth, ...
* verschiedene Frequenzbereiche im WLAN:
    * 2.4GHz (Kanal 1-13)
    * 5GHz (Kanal 36-140)

* zwei wichtige Modi:
    * Adhoc (http://berlin.freifunk.net/static/img/adhoc_netz_wikipedia.png)
    * Accesspoint/Client

* verhält sich wie Kabelnetzwerk (nur dass bei Wifi Pakete oft verloren gehen)

---

# Antennen

* Antennen habe eine Richtung in die sie strahlen (Richtcharakteristik)
* Verschiedene Antennentypen:
    * Rundstrahler
    * Parabolantenne
    * Panelantenne

---

# Datenübertragung

* Daten werden in Paketen zwischen Rechnern übertragen
* jedes Paket hat eine Ziel-Adresse und eine Absender-Adresse
* Domains (z.B. freifunk.net) werden umgewandelt in eine IP-Adresse (176.28.11.93), DNS

---

## IP-Adressen

* Wie normale Adressen (Post)
* Wie sieht eine IP-Adresse aus (192.168.42.1)
* großer Zahlenbereich von 0.0.0.0-255.255.255.255
* Wikipedia: [https://de.wikipedia.org/wiki/IP-Adresse](https://de.wikipedia.org/wiki/IP-Adresse)

---

## Subnetze

* Aufteilung des IP-Addressbereichs in Teilnetze
* Subnetz ist sowas wie eine Postleitzahlbereich
* Ein Subnetz besteht aus einer Netz-IP und einem Suffix "Größenangabe"
* Beispiele:
    * großes Netz: 192.168.42.0/24 (256 IPs: 192.168.42.0-255)
    * kleineres Netz: 192.168.42.0/25 (128 IPs: 192.168.42.0-127)
* Wikipedia: [https://de.wikipedia.org/wiki/Subnetz](https://de.wikipedia.org/wiki/Subnetz)

---

# Routing-Spiel

* wir bilden zweier/dreier Gruppen (insgesamt 8 Gruppen)
* jede Gruppe bekommt eine IP (z.B. 10.230.62.1) und eine Routingtabelle, z.B.:
* jede Gruppe schickt ein Paket mit einer Zieladresse (10.230.62.1-8) auf die Reise

<pre>
    Ziel               Router
    ----------------------------------
    Standard     über  10.230.62.2
    10.230.62.7  über  10.230.62.8
    10.230.62.6  über  10.230.62.8
    10.230.62.5  über  10.230.62.8
    10.230.62.8        direkter Nachbar
    10.230.62.2        direkter Nachbar
</pre>

---

# Router einrichten

* Jede Gruppe erhält einen Router
* Zu jedem Router gehören zwei "Mesh-IPs" und ein DHCP-Subnetz (IPs für Smartphones & Notebooks)
* Jede Gruppe konfiguriert einen Router fürs Freifunk

---

# Grundlagen von OLSR

* Jeder Router sagt seinen Nachbarn "Hallo"
* Jeder Router lernt so seine Nachbarn kennen
* Aus den Informationen über die Nachbarn generiert jeder Router seine Routing-Tabelle
* Wenn ein Router ausfällt übernehmen andere Router die Weiterleitung der Paket
