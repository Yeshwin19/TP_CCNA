# TP 2

## Gateway

* ouvrir `cmd`
* utiliser `ipconfig`
* repérer les champs "Nom, Adresse MAC et adresse IP de l'interface WiFi."

```_
C:\Users\yeshwin>ipconfig

Configuration IP de Windows


Carte Ethernet Ethernet :

   Statut du média. . . . . . . . . . . . : Média déconnecté
   Suffixe DNS propre à la connexion. . . :

Carte réseau sans fil Connexion au réseau local* 3 :

   Statut du média. . . . . . . . . . . . : Média déconnecté
   Suffixe DNS propre à la connexion. . . :

Carte réseau sans fil Connexion au réseau local* 2 :

   Statut du média. . . . . . . . . . . . : Média déconnecté
   Suffixe DNS propre à la connexion. . . :

Carte réseau sans fil Wi-Fi :

   Suffixe DNS propre à la connexion. . . :
   Adresse IPv6 de liaison locale. . . . .: fe80::c569:1b9a:afb1:3f1%17
   Adresse IPv4. . . . . . . . . . . . . .: 10.188.83.190
   Masque de sous-réseau. . . . . . . . . : 255.255.0.0
   Passerelle par défaut. . . . . . . . . : 10.188.0.1

Carte Ethernet Connexion réseau Bluetooth :

   Statut du média. . . . . . . . . . . . : Média déconnecté
   Suffixe DNS propre à la connexion. . . :

*Le nom c'est Carte Ethernet Ethernet.
*L'adresse MAC c'est fe80::c569:1b9a:afb1:3f1%17.
*L'adresse IP de l'interface WiFi c'est 10.188.83.190.
* ma passerelle c'est 10.188.0.1.
* Adresse de Réseau 10.188.83.190.
* Adresse de Broadcast 10.188.83.191.
```

* ouvrir `cmd`
* utiliser `ipconfig/all`
* repérer les champs "Nom, Adresse MAC et adresse IP de l'interface WiFi."

```_
C:\Users\yeshwin>ipconfig/all

Configuration IP de Windows

   Nom de l’hôte . . . . . . . . . . : yeshwin
   Suffixe DNS principal . . . . . . :
   Type de noeud. . . . . . . . . .  : Hybride
   Routage IP activé . . . . . . . . : Non
   Proxy WINS activé . . . . . . . . : Non

Carte Ethernet Ethernet :

   Statut du média. . . . . . . . . . . . : Média déconnecté
   Suffixe DNS propre à la connexion. . . :
   Description. . . . . . . . . . . . . . : Realtek PCIe GBE Family Controller
   Adresse physique . . . . . . . . . . . : A0-1D-48-B3-FE-29
   DHCP activé. . . . . . . . . . . . . . : Non
   Configuration automatique activée. . . : Oui

Carte réseau sans fil Connexion au réseau local* 3 :

   Statut du média. . . . . . . . . . . . : Média déconnecté
   Suffixe DNS propre à la connexion. . . :
   Description. . . . . . . . . . . . . . : Microsoft Wi-Fi Direct Virtual Adapter
   Adresse physique . . . . . . . . . . . : 1A-E3-47-FB-06-D6
   DHCP activé. . . . . . . . . . . . . . : Oui
   Configuration automatique activée. . . : Oui

Carte réseau sans fil Connexion au réseau local* 2 :

   Statut du média. . . . . . . . . . . . : Média déconnecté
   Suffixe DNS propre à la connexion. . . :
   Description. . . . . . . . . . . . . . : Microsoft Wi-Fi Direct Virtual Adapter #2
   Adresse physique . . . . . . . . . . . : 2A-E3-47-FB-06-D6
   DHCP activé. . . . . . . . . . . . . . : Oui
   Configuration automatique activée. . . : Oui

Carte réseau sans fil Wi-Fi :

   Suffixe DNS propre à la connexion. . . :
   Description. . . . . . . . . . . . . . : Qualcomm Atheros QCA9565 802.11b|g|n WiFi Adapter
   Adresse physique . . . . . . . . . . . : 28-E3-47-FB-06-D6
   DHCP activé. . . . . . . . . . . . . . : Oui
   Configuration automatique activée. . . : Oui
   Adresse IPv6 de liaison locale. . . . .: fe80::c569:1b9a:afb1:3f1%17(préféré)
   Adresse IPv4. . . . . . . . . . . . . .: 10.188.83.190(préféré)
   Masque de sous-réseau. . . . . . . . . : 255.255.0.0
   Bail obtenu. . . . . . . . . . . . . . : lundi 7 janvier 2019 21:36:08
   Bail expirant. . . . . . . . . . . . . : lundi 14 janvier 2019 21:59:06
   Passerelle par défaut. . . . . . . . . : 10.188.0.1
   Serveur DHCP . . . . . . . . . . . . . : 10.188.0.1
   IAID DHCPv6 . . . . . . . . . . . : 69788487
   DUID de client DHCPv6. . . . . . . . : 00-01-00-01-23-30-71-AA-A0-1D-48-B3-FE-29
   Serveurs DNS. . .  . . . . . . . . . . : 10.188.0.1
   NetBIOS sur Tcpip. . . . . . . . . . . : Activé

Carte Ethernet Connexion réseau Bluetooth :

   Statut du média. . . . . . . . . . . . : Média déconnecté
   Suffixe DNS propre à la connexion. . . :
   Description. . . . . . . . . . . . . . : Bluetooth Device (Personal Area Network)
   Adresse physique . . . . . . . . . . . : 28-E3-47-FB-3D-86
   DHCP activé. . . . . . . . . . . . . . : Oui
   Configuration automatique activée. . . : Oui
```

* Le nom c'est Carte Ethernet Connexion réseau Bluetooth.
* L'adresse MAC c'est 28-E3-47-FB-3D-86
* NOTE : Je n’ai pas d’adresse IP pour l’interface Ethernet et pas de masque.

* Affichage de l'adresse IP du passerelle par défaut :

```_
Carte réseau sans fil Wi-Fi :

   Suffixe DNS propre à la connexion. . . :
   Description. . . . . . . . . . . . . . : Qualcomm Atheros QCA9565 802.11b|g|n WiFi Adapter
   Adresse physique . . . . . . . . . . . : 28-E3-47-FB-06-D6
   DHCP activé. . . . . . . . . . . . . . : Oui
   Configuration automatique activée. . . : Oui
   Adresse IPv6 de liaison locale. . . . .: fe80::c569:1b9a:afb1:3f1%17(préféré)
   Adresse IPv4. . . . . . . . . . . . . .: 10.188.83.190(préféré)
   Masque de sous-réseau. . . . . . . . . : 255.255.0.0
   Bail obtenu. . . . . . . . . . . . . . : lundi 7 janvier 2019 21:36:08
   Bail expirant. . . . . . . . . . . . . : lundi 14 janvier 2019 21:59:06
   Passerelle par défaut. . . . . . . . . : 10.188.0.1
   Serveur DHCP . . . . . . . . . . . . . : 10.188.0.1
   IAID DHCPv6 . . . . . . . . . . . : 69788487
   DUID de client DHCPv6. . . . . . . . : 00-01-00-01-23-30-71-AA-A0-1D-48-B3-FE-29
   Serveurs DNS. . .  . . . . . . . . . . : 10.188.0.1
   NetBIOS sur Tcpip. . . . . . . . . . . : Activé
```

* Ma passerelle c'est 10.188.0.1

* Affichage de l’adresse IP, la MAC et la gateway pour l'interface WiFi de votre PC en GUI :

```_
Suffixe DNS propre à la connexion:
Description:                          Qualcomm Atheros QCA9565 802.11b|g|n WiFi Adapter
Adresse physique:                     28-E3-47-FB-06-D6
DHCP activé:                          Oui
Adresse IPv4:                         10.188.83.190
Masque de sous-réseau IPv4:           255.255.0.0
Bail obtenu:                          lundi 7 janvier 2019 21:36:08
Bail expirant:                        lundi 14 janvier 2019 22:14:54
Passerelle par défaut IPv4:           10.188.0.1
Serveur DHCP IPv4:                    10.188.0.1
Serveur DNS IPv4:                     10.188.0.1
Serveur WINS IPv4:
NetBIOS sur TCP/IP activé:            Oui
Adresse IPv6 locale de lien:          fe80::c569:1b9a:afb1:3f1%17
Passerelle par défaut IPv6:
Serveur DNS IPv6:
```

* A quoi sert la gateway dans le réseau d'Ingésup ?

```_
La gateway dans le réseau d’Ingésup sert a communiquer avec des machines en dehors du réseau.
```

* 2.Modifications des informations

```_
J’ai changé l’IP a 10.188.83.162
Masque sous réseau – 255.255.0.0
Premiere adresse IP – 10.188.83.161
Derniere adresse IP – 10.188.83.162
```

* 2B. nmap
* Utilisation de nmap pour faire un Ping Scan
* Commande: nmap -sn 10.188.0.1

```_
Starting Nmap 7.60 ( https://nmap.org ) at 2019-01-07 22:58 Paris, Madrid

Nmap scan report for lanspeedtest.wifirst.fr (10.188.0.1)

Host is up (0.0020s latency).

MAC Address: 20:47:47:83:1C:60 (Dell)

Nmap done: 1 IP address (1 host up) scanned in 4.61 seconds


```

* Trouver le "nom" associés aux adresses IP
* Commande: nmap -sL 10.188.0.1

```_
Starting Nmap 7.60 ( https://nmap.org ) at 2019-01-07 23:00 Paris, Madrid

Nmap scan report for lanspeedtest.wifirst.fr (10.188.0.1)

Nmap done: 1 IP address (0 hosts up) scanned in 3.90 seconds

```

* Exemple de commande nmap -sn -PE :

``` _
Starting Nmap 7.60 ( https://nmap.org ) at 2019-01-07 23:08 Paris, Madrid

Nmap scan report for 10.188.83.137

Host is up (0.0020s latency).

MAC Address: 78:24:AF:B6:F2:52 (Asustek Computer)

Nmap scan report for 10.188.83.162

Host is up.

Nmap done: 1024 IP addresses (2 hosts up) scanned in 39.06 seconds
```

``` _
Je n'ai pas d'adresse IP libre
```

* II. Exploration locale en duo
* 1.Prerequis

``` _
On avait tous les équipements nécessaires.
```

* 2.Cablage

``` _
On a branché le câble RJ45 aux deux ports de nos PCs
```

* 3 et 4 Création du réseau et utilisation d'un des deux comme Gateway

``` _
* On a désactiver nos pares feux.
* Et sur un PC on a désactiver internet et sur l'autre on a activer Internet.
* On est parti sur Panneau de configuration, Réseau et internet, afficher l’état de la gestion du réseau.
* On a sélectionné le wifi, puis propriété et on a changé l’IP des deux machines (premier pc 172.16.18.10 et       deuxième pc 172.16.18.11) et on a aussi testé avec 192.168.10.20 sur un PC et 192.168.10.21 sur l’autre PC.
* On a lancé un ping et on a pu constater que les deux PCs communiquent sans problème.
* On a lancé un ping sur 8.8.8.8 et sans problème.
* On est parti sur Réseau et internet, afficher l’état de la gestion, sur partage et on a partagé internet d’un   pc ou internet était activé vers l’autre et sans problème.
* On a lancé un ping sur 8.8.8.8 et sans problème.
* Le PC ou il y avait pas internet a pu communiquer avec le PC ou il y avait internet.
```

* 5.Petit chat privé

```_
NOTE : On a pas pu le faire car l’application se ferme constamment après l’exécution du premier commande (nc.exe        -l -p 172.16.18.11 8888 et l’autre commande nc.exe -l -p 8888)

Donc on s’est arrêté ici !.
```
