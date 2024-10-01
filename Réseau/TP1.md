### Tp1 Les premier pas 



### I. Récolte d'informations

```
ip config

PS C:\Users\user>
Configuration IP de Windows

🌞affiche l'adresse IP que ta machine a sur sa carte réseau WiFi
Carte réseau sans fil Wi-Fi :

   Suffixe DNS propre à la connexion. . . :
   Adresse IPv6 de liaison locale. . . . .: fe80::ccb1:f62d:367a:eb%6
   Adresse IPv4. . . . . . . . . . . . . .: 10.33.77.165
   Masque de sous-réseau. . . . . . . . . : 255.255.240.0
   Passerelle par défaut. . . . . . . . . : 10.33.79.254


🌞affiche l'adresse IP que ta machine a sur sa carte réseau ethernet

Carte Ethernet Ethernet :

   Statut du média. . . . . . . . . . . . : Média déconnecté
   Suffixe DNS propre à la connexion. . . : home

Carte Ethernet Ethernet 2 :

   Suffixe DNS propre à la connexion. . . :
   Adresse IPv6 de liaison locale. . . . .: fe80::d907:a853:40be:86ed%5
   Adresse IPv4. . . . . . . . . . . . . .: 192.168.56.1
   Masque de sous-réseau. . . . . . . . . : 255.255.255.0
   Passerelle par défaut. . . . . . . . . :



🌞l'adresse IP de la passerelle du réseau local

Carte réseau sans fil Wi-Fi :

   Suffixe DNS propre à la connexion. . . :
   Adresse IPv6 de liaison locale. . . . .: fe80::ccb1:f62d:367a:eb%6
   Adresse IPv4. . . . . . . . . . . . . .: 10.33.77.165
   Masque de sous-réseau. . . . . . . . . : 255.255.240.0
   Passerelle par défaut. . . . . . . . . : 10.33.79.254

🌞affiche l'adresse IP du serveur DNS que connaît ton PC
🌞affiche l'adresse IP du serveur DHCP que connaît ton PC

 Serveur DHCP . . . . . . . . . . . . . : 10.33.79.254
   IAID DHCPv6 . . . . . . . . . . . : 171231549
   DUID de client DHCPv6. . . . . . . . : 00-01-00-01-27-4A-C4-C9-3C-7C-3F-5F-CD-96
   Serveurs DNS. . .  . . . . . . . . . . : 8.8.8.8
                                       1.1.1.1
   NetBIOS sur Tcpip. . . . . . . . . . . : Activé


```

### II. Utiliser le réseau

```
🌞ping vers ta propre adresse IP

PS C:\Users\user> ping  192.168.56.1

Envoi d’une requête 'Ping'  192.168.56.1 avec 32 octets de données :
Réponse de 192.168.56.1 : octets=32 temps<1ms TTL=128
Réponse de 192.168.56.1 : octets=32 temps<1ms TTL=128
Réponse de 192.168.56.1 : octets=32 temps<1ms TTL=128
Réponse de 192.168.56.1 : octets=32 temps<1ms TTL=128

Statistiques Ping pour 192.168.56.1:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 0ms, Maximum = 0ms, Moyenne = 0ms

🌞vers l'adresse ip 127.0.0.0

PS C:\Users\user> ping 127.0.0.1

Envoi d’une requête 'Ping'  127.0.0.1 avec 32 octets de données :
Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128
Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128
Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128
Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128

Statistiques Ping pour 127.0.0.1:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 0ms, Maximum = 0ms, Moyenne = 0ms


🌞 On continue avec ping. Envoie un ping vers...

🌞Passerelle: 

PS C:\Users\user> ping 10.33.79.254

Envoi d’une requête 'Ping'  10.33.79.254 avec 32 octets de données :
Délai d’attente de la demande dépassé.
Délai d’attente de la demande dépassé.
Délai d’attente de la demande dépassé.
Délai d’attente de la demande dépassé.

Statistiques Ping pour 10.33.79.254:
    Paquets : envoyés = 4, reçus = 0, perdus = 4 (perte 100%),

🌞un(e) pote sur le réseau

PS C:\Users\user> ping 10.33.66.78

Envoi d’une requête 'Ping'  10.33.66.78 avec 32 octets de données :
Réponse de 10.33.66.78 : octets=32 temps=59 ms TTL=64
Réponse de 10.33.66.78 : octets=32 temps=62 ms TTL=64
Réponse de 10.33.66.78 : octets=32 temps=73 ms TTL=64
Réponse de 10.33.66.78 : octets=32 temps=86 ms TTL=64

Statistiques Ping pour 10.33.66.78:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 59ms, Maximum = 86ms, Moyenne = 70ms

🌞un site internet

PS C:\Users\user> ping www.thinkerview.com

Envoi d’une requête 'ping' sur www.thinkerview.com [188.114.96.7] avec 32 octets de données :
Réponse de 188.114.96.7 : octets=32 temps=15 ms TTL=55
Réponse de 188.114.96.7 : octets=32 temps=15 ms TTL=55
Réponse de 188.114.96.7 : octets=32 temps=16 ms TTL=55
Réponse de 188.114.96.7 : octets=32 temps=16 ms TTL=55

Statistiques Ping pour 188.114.96.7:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 15ms, Maximum = 16ms, Moyenne = 15ms

🌞 Faire une requête DNS à la main
PS C:\Users\user> nslookup www.thinkerview.com
Serveur :   dns.google
Address:  8.8.8.8

Réponse ne faisant pas autorité :
Nom :    www.thinkerview.com
Addresses:  2a06:98c1:3120::7
          2a06:98c1:3121::7
          188.114.96.7
          188.114.97.7

PS C:\Users\user> nslookup www.wikileaks.org
Serveur :   dns.google
Address:  8.8.8.8

Réponse ne faisant pas autorité :
Nom :    wikileaks.org
Addresses:  51.159.197.136
          80.81.248.21
Aliases:  www.wikileaks.org

PS C:\Users\user> nslookup www.torproject.org
Serveur :   dns.google
Address:  8.8.8.8

Réponse ne faisant pas autorité :
Nom :    www.torproject.org
Addresses:  2a01:4f8:fff0:4f:266:37ff:feae:3bbc
          2620:7:6002:0:466:39ff:fe32:e3dd
          2a01:4f9:c010:19eb::1
          2620:7:6002:0:466:39ff:fe7f:1826
          2a01:4f8:fff0:4f:266:37ff:fe2c:5d19
          204.8.99.146
          204.8.99.144
          116.202.120.166
          95.216.163.36
          116.202.120.165

```
### III. Sniffer le réseau

```
🌞 J'attends dans le dépôt git de rendu un fichier ping.pcap
"fichier sur mon git"

🌞 Livrez un deuxième fichier : dns.pcap
"fichier sur mon git 

```

### IV. Network scanning et adresses IP
 
```
🌞 Effectue un scan du réseau auquel tu es connecté

    PS C:\Users\user> nmap -sn -PR 10.33.64.0/20
Starting Nmap 7.95 ( https://nmap.org ) at 2024-09-27 17:38 Paris, Madrid (heure dÆÚtÚ)
Nmap scan report for 10.33.66.78
Host is up (0.083s latency).
MAC Address: E4:B3:18:48:36:68 (Intel Corporate)
Nmap scan report for 10.33.69.82
Host is up (1.2s latency).

MAC Address: 7C:5A:1C:D3:D8:76 (Sophos)
Nmap scan report for 10.33.77.165
Host is up.
Nmap done: 4096 IP addresses (141 hosts up) scanned in 107.08 seconds

🌞 Changer d'adresse IP

Carte réseau sans fil Wi-Fi :

   ancienne adresse reseau 
   
   Suffixe DNS propre à la connexion. . . :
   Adresse IPv6 de liaison locale. . . . .: fe80::ccb1:f62d:367a:eb%6
   Adresse IPv4. . . . . . . . . . . . . .: 10.33.77.165
   Masque de sous-réseau. . . . . . . . . : 255.255.240.0
   Passerelle par défaut. . . . . . . . . : 10.33.79.254

Nouvelle adresse reseau 

Carte réseau sans fil Wi-Fi :

   Suffixe DNS propre à la connexion. . . :
   Adresse IPv6 de liaison locale. . . . .: fe80::ccb1:f62d:367a:eb%6
   Adresse IPv4. . . . . . . . . . . . . .: 10.33.77.165
   Masque de sous-réseau. . . . . . . . . : 255.255.240.0
   Passerelle par défaut. . . . . . . . . : 10.33.79.254