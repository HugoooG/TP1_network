### I. Quelques pings

```
🌞 Prouvez que votre configuration est effective

PS C:\Users\user> Get-NetIPAddress -InterfaceAlias "Ethernet"


IPAddress         : fe80::4262:3244:42fe:67e9%8
InterfaceIndex    : 8
InterfaceAlias    : Ethernet
AddressFamily     : IPv6
Type              : Unicast
PrefixLength      : 64
PrefixOrigin      : WellKnown
SuffixOrigin      : Link
AddressState      : Preferred
ValidLifetime     :
PreferredLifetime :
SkipAsSource      : False
PolicyStore       : ActiveStore

IPAddress         : 10.1.1.2
InterfaceIndex    : 8
InterfaceAlias    : Ethernet
AddressFamily     : IPv4
Type              : Unicast
PrefixLength      : 24
PrefixOrigin      : Manual
SuffixOrigin      : Manual
AddressState      : Preferred
ValidLifetime     :
PreferredLifetime :
SkipAsSource      : False
PolicyStore       : ActiveStore


🌞 Tester que votre LAN + votre adressage IP est fonctionnel

PS C:\Users\user> ping 10.1.1.1

Envoi d’une requête 'Ping'  10.1.1.1 avec 32 octets de données :
Réponse de 10.1.1.1 : octets=32 temps<1ms TTL=128
Réponse de 10.1.1.1 : octets=32 temps<1ms TTL=128
Réponse de 10.1.1.1 : octets=32 temps<1ms TTL=128
Réponse de 10.1.1.1 : octets=32 temps<1ms TTL=128

Statistiques Ping pour 10.1.1.1:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 0ms, Maximum = 0ms, Moyenne = 0ms
```
### II. Utilisation des ports

```
🌞 Sur le PC serveur

"Dorian est le serveur"

🌞 Sur le PC serveur toujours

IDEM

🌞 Sur le PC client

PS C:\Users\user> ncat 10.1.1.1 69

🌞 Echangez-vous des messages

PS C:\Users\user> ncat 10.1.1.1 69
je t'aime - Serveur
Moi aussi <3 - client

🌞 Utilisez une commande qui permet de voir la connexion en cours

TCP    10.1.1.2:3546          10.1.1.1:69            ESTABLISHED
 [ncat.exe]


🌞 Inversez les rôles

🌞 Sur le PC serveur

PS C:\Users\user> ncat -l 6

🌞 Sur le PC serveur toujours

PS C:\WINDOWS\system32> netstat -a -b -n

Connexions actives

  Proto  Adresse locale         Adresse distante       État
  TCP    0.0.0.0:6              0.0.0.0:0              LISTENING
 [ncat.exe]

PS C:\Users\user> ncat -l 6
t bo - client
Je sais <3 - Serveur
```

### III. Analyse de vos applications usuelles

🌞 Pour les 5 applications
```
discord.pcapng
chrome.pcapng
epicgamelauncher.pcapng
teamviewer.pcapng
geforceexperience.pcapng
