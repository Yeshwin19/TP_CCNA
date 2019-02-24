# I. Préparation du lab

----------

**Pour ce I. il n'y a aucune machine à lancer. Uniquement des VMs/routeurs à préparer. Ce sont les infos préliminaires, avec un tableau récapitulatif à la fin. C'est pour que preniez connaissance et que vous mettiez en place le contexte du TP.**

----------

## [](https://github.com/It4lik/B1-Reseau-2018/tree/master/tp/5#1-pr%C3%A9paration-vms)1. Préparation VMs

**1. Création d'un nouveau host-only**

-   peu importe l'adresse on s'en servira juste pour faire du  [SSH](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/lexique.md#ssh--secure-shell)
-   **activez le DHCP**  comme ça on aura pas besoin de saisir les IPs

**2. Création des VMs**

-   On va juste cloner trois VMs depuis le patron du TP précédent :
    -   `server1.tp5.b1`  sera dans  `net1`  et portera l'IP  `10.5.1.10/24`
   ![insertion](server1ip.PNG)

    -   `client1.tp5.b1`  sera dans  `net2`  et portera l'IP  `10.5.2.10/24`
   ![insertion](client1ip.PNG)

    -   `client2.tp5.b1`  sera dans  `net2`  et portera l'IP  `10.5.2.11/24`
   ![insertion](client2ip.PNG)

-   Ajoutez aux trois VMs une interface host-only  **en deuxième carte**  dans le host-only précédemment créé

**3. Vous clonez juste les VMs, vous ne les allumez pas.**

-   Ensuite RDV dans GNS3 : Edit > Preferences > VirtualBox VMs et vous ajoutez les trois VMs.

**4. Config réseau des dans GNS3**

-   Sur les 3 VMs
    -   Clic-droit > Configure > Network
    -   mettre 2 cartes réseau

## [](https://github.com/It4lik/B1-Reseau-2018/tree/master/tp/5#2-pr%C3%A9paration-routeurs-cisco)2. Préparation Routeurs Cisco

Importez l'ISO du routeur et mettez-en deux dans GNS3 :

-   `router1.tp5.b1`  est dans :
    -   `net1`  et portera l'IP  `10.5.1.254/24`
    -   `net12`
  

-   `router2.tp5.b1`  est dans :
    -   `net2`  et portera l'IP  `10.5.2.254/24`
    -   `net12`
  


**Vous devrez déterminer vous-même un réseau et un masque pour  `net12`  et le justifier**. Il n'y aura que deux routeurs dans ce réseau.

## [](https://github.com/It4lik/B1-Reseau-2018/tree/master/tp/5#3-pr%C3%A9paration-switches)3. Préparation Switches

Rien à faire ici, on va utiliser les Ethernet Switches de GNS3 comme de bêtes multiprises. Un switch n'a pas d'IP.

## [](https://github.com/It4lik/B1-Reseau-2018/tree/master/tp/5#4-topologie-et-tableau-r%C3%A9capitulatif)4. Topologie et tableau récapitulatif

**Topologie :**

```
                                             client1
                                            /
Server1 --net1-- R1 --net12-- R2 --net2-- Sw
                                            \
                                             client2

```

**Réseaux :**

-   `net1`  :  `10.5.1.0/24`
-   `net2`  :  `10.5.2.0/24`
-   `net12`  : `10.5.3.0/30 (pour pouvoir utiliser les ips (10.5.12.1 et 10.5.12.2)`

**Machines :**


|  Machine	|   Net 1	|   Net 2	|   Net 12	|
|---	|---	|---	|---	|
|  client1.tp5 	|   X	|   10.5.2.10	|   X	|
| client2.tp5  	|   X |  10.5.2.11 	|   X	|
|   server1.tp5|  10.5.1.10 	|   X	|   X	|
|   router1.tp5	|  10.5.1.254 	|   X	|  10.5.12.1 	|
|   router2.tp5	| X  	|   10.5.2.254	|   	10.5.12.2|


# [](https://github.com/It4lik/B1-Reseau-2018/tree/master/tp/5#ii-lancement-et-configuration-du-lab)II. Lancement et configuration du lab

Lancez toutes les machines (ou une par une). Je vous conseille de vous posez tranquillement, et de vous conformez à une liste d'étapes pour ce faire. Ici encore je la fais pour vous,  **habituez-vous à utiliser ce genre de petites techniques pour gagner en rigueur**.

**Prenez des notes de ce que vous faites.**

### [](https://github.com/It4lik/B1-Reseau-2018/tree/master/tp/5#checklist-ip-vms)Checklist IP VMs

On parle de  `client1.tp5.b1`,  `client2.tp5.b1`  et  `server1.tp5.b1`  :

-   Désactiver SELinux
    -   déja fait dans le patron
-   Installation de certains paquets réseau
    -   déja fait dans le patron
-   Désactivation de la carte NAT
    -   déja fait dans le patron
-   [Définition des IPs statiques](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/procedures.md#d%C3%A9finir-une-ip-statique)
-   La connexion SSH doit être fonctionnelle
    -   une fois fait, vous avez vos trois fenêtres SSH ouvertes, une dans chaque machine
-   [Définition du nom de domaine](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/procedures.md#changer-son-nom-de-domaine)

### [](https://github.com/It4lik/B1-Reseau-2018/tree/master/tp/5#checklist-ip-routeurs)Checklist IP Routeurs

On parle de  `router1.tp5.b1`  et  `router2.tp5.b1`  :

-   [Définition des IPs statiques](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/procedures-cisco.md#d%C3%A9finir-une-ip-statique)
-   [Définition du nom de domaine](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/procedures-cisco.md#changer-son-nom-de-domaine)

### [](https://github.com/It4lik/B1-Reseau-2018/tree/master/tp/5#checklist-routes)Checklist routes

On parle de toutes les machines :

-   `router1.tp5.b1`
 ```
 router1.tp5#show ip int br
Interface                  IP-Address      OK? Method Status                Protocol
Ethernet0/0                10.5.1.254      YES manual up                    up
Ethernet0/1                10.5.12.1       YES manual up                    up
Ethernet0/2                unassigned      YES unset  administratively down down
Ethernet0/3                unassigned      YES unset  administratively down down

```

route net2: 
```
Gateway of last resort is not set

     10.0.0.0/24 is subnetted, 3 subnets
C       10.5.12.0 is directly connected, Ethernet0/1
S       10.5.2.0 [1/0] via 10.5.12.2
C       10.5.1.0 is directly connected, Ethernet0/0

```

-   `router2.tp5.b1`
```
router2.tp5#show ip int br
Interface                  IP-Address      OK? Method Status                Protocol
Ethernet0/0                10.5.12.2       YES manual up                    up
Ethernet0/1                10.5.2.254      YES manual up                    up
Ethernet0/2                unassigned      YES unset  administratively down down
Ethernet0/3                unassigned      YES unset  administratively down down
```

net 1:

```
Gateway of last resort is not set

     10.0.0.0/24 is subnetted, 3 subnets
C       10.5.12.0 is directly connected, Ethernet0/0
C       10.5.2.0 is directly connected, Ethernet0/1
S       10.5.1.0 [1/0] via 10.5.12.1

```
-   `server1.tp5.b1`
    -   directement connecté à  `net1`
    ![insertion](server1ip.PNG)
    
    -   [route à ajouter](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/procedures.md#ajouter-une-route-statique)  :  `net2`
    ![insertion](serverrajoutroute.PNG)

    -   [fichiers  `hosts`](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/procedures.md#editer-le-fichier-hosts)  à remplir :  `client1.tp5.b1`,  `client2.tp5.b1`
   ![insertion](serverfichierhosts.PNG)

-   `client1.tp5.b1`
   ![insertion](client1ip.PNG) 
 
    -   directement connecté à  `net2`
    -   [route à ajouter](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/procedures.md#ajouter-une-route-statique)  :  `net1`
   ![insertion](client1route.PNG)

    -   [fichiers  `hosts`](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/procedures.md#editer-le-fichier-hosts)  à remplir :  `server1.tp5.b1`,  `client2.tp5.b1`
   ![insertion](client1fichierhosts.PNG)


-   `client2.tp5.b1`
    -   directement connecté à  `net2`
    ![insertion](client2ip.PNG)

    -   [route à ajouter](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/procedures.md#ajouter-une-route-statique)  :  `net1`
    ![insertion](client2route.PNG)

    -   [fichiers  `hosts`](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/procedures.md#editer-le-fichier-hosts)  à remplir :  `server1.tp5.b1`,  `client1.tp5.b1`
   ![insertion](client2hosts.PNG)

Pour tester :
-   les deux clients doivent pouvoir  `ping server1.tp5.b1`
-   et réciproquement  🔥

- `J'ai fais le test et ça marche correctement`

> **Notez que les clients/serveurs n'ont pas de route vers  `net12`**. Et ui. C'est un réseau privé que seuls les routeurs connaissent.

# [](https://github.com/It4lik/B1-Reseau-2018/tree/master/tp/5#iii-dhcp)III. DHCP

Attribuer des IPs statiques et des routes sur les VMs c'est chiant non ?  **Serveur  [DHCP](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/lexique.md#dhcp--dynamic-host-configuration-protocol)**  à la rescousse.

Une section dédiée popera dans le cours d'ici peu.

Un serveur  [DHCP](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/lexique.md#dhcp--dynamic-host-configuration-protocol)  :

-   permet d'attribuer dynamiquement des IPs
    -   on a pas besoin de les définir à la main
-   est principalement utilisé pour des  [clients](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/3.md#clientserveur)
    -   on préfère avoir des IPs fixes (statiques) pour les  [serveurs](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/3.md#clientserveur)  et les équipements réseaux (comme les  [routeurs](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/lexique.md#routeur))
    -   ce serait un peu le dawa s'ils changeaient tout le temps
-   permet aussi de distribuer d'autres infos aux  [clients](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/3.md#clientserveur)
    -   comme des routes !

## [](https://github.com/It4lik/B1-Reseau-2018/tree/master/tp/5#1-mise-en-place-du-serveur-dhcp)1. Mise en place du serveur DHCP

On va recycler  `client2.tp5.b1`  pour ça (pour économiser un peu de ressources).

**1.  [Renommer la machine](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/procedures.md#changer-son-nom-de-domaine)**

-   pour porter le nom  `dhcp-net2.tp5.b1`
![insertion](dhcp.PNG)



**2. Installer le serveur DHCP**  en faisant un peu de crasse :

-   éteindre la VM dans GNS3
-   ouvrir VirtualBox
-   ajouter une troisième carte en NAT à la VM
-   démarrer la VM dans VirtualBox
-   s'assurer que la nouvelle carte (`enp0s9`  ?) possède une IP
    -   c'est juste pour accéder à internet vite fait, le temps d'installer notre serveur DHCP.
  ![insertion](enp0s9.PNG)

-   `sudo yum install -y dhcp`
-   shutdown la VM

**3. Rallumer la VM dans GNS**

**4. Configuration du serveur DHCP**

-   le fichier de configuration se trouve dans  `/etc/dhcp/dhcpd.conf`
    -   le modifier, et copier le contenu du  [modèle](https://github.com/It4lik/B1-Reseau-2018/blob/master/tp/5/dhcp/dhcpd.conf)  dedans
![insertion](dhcpconf.PNG)


**5. Démarrer le serveur DHCP**

-   `sudo systemctl start dhcpd`
-   en cas d'erreur, mp moi
-   s'il se passe rien, c'est bon (`systemctl status dhcpd`  pour vérifier)
![insertion](dhcpstatus.PNG)



**6. Faire un test**

-   avec une nouvelle VM ou  `client1.tp5.b1`
    -   [configurer l'interface en DHCP, en dynamique (pas en statique)](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/procedures.md#d%C3%A9finir-une-ip-dynamique-dhcp)
![insertion](intdhcp.PNG)


    -   utiliser  [`dhclient`](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/lexique.md#dhclient-linux-only)
-   dans un cas comme dans l'autre, vous devriez récupérer une IP dans la plage d'IP définie dans  `dhcpd.conf`

## [](https://github.com/It4lik/B1-Reseau-2018/tree/master/tp/5#2-explorer-un-peu-dhcp)2. Explorer un peu DHCP

Le principe du  [protocole DHCP](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/lexique.md#dhcp--dynamic-host-configuration-protocol)  est le suivant :

-   on a un serveur sur un réseau, il attend que des clients lui demande des IPs
-   des clients peuvent arriver sur le réseau (câble, WiFi, ou autres) et demander une IP
-   le serveur attribuera une IP dans une plage prédéfinie
-   le serveur va créer un  **"bail DHCP"**  par client, pour s'en souvenir
    -   **dans le bail il y a écrit "j'ai donné telle IP à telle MAC"**
    -   comme ça, si le même client revient, il garde son IP

----------

[_Le cours 6 détaille ces opérations au sujet du DHCP_.](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/6.md#dhcp)

La discussion entre le client et le serveur DHCP se fait en 4 messages simples,  **"DORA"**  :

-   **"Discover"**  : du client vers le serveur
    -   le client cherche un serveur DHCP en envoyant des Discover en broadcast
-   **"Offer"**  : du serveur vers le client
    -   Si un serveur reçoit un "Discover" il peut répondre un "Offer" au client
    -   Il propose une IP au client
-   **"Request"**  : du client vers le serveur
    -   Permet de demander une IP au serveur
    -   C'est celle que le serveur lui a proposé
-   **"Acknowledge"**  : du serveur vers le client
    -   Le serveur attribue l'adresse IP au client
    -   Il crée un bail DHCP en local
    -   Il peut aussi fournir au client d'autres infos comme l'adresse de gateway

----------

**OKAY**, le but :

-   faire une demande DHCP
    -   avec  [`dhclient`](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/lexique.md#dhclient-linux-only)
    ![insertion](bail.PNG)
    
    -   capturer avec Wireshark l'échange du DORA
        -   vous pouvez  [`tcpdump`](https://github.com/It4lik/B1-Reseau-2018/blob/master/cours/lexique.md#tcpdump)  sur le  `client1.tp5.b1`  ou sur  `dhcp-net2.tp5.b1`
        -   ou vous pouvez clic-droit sur un lien dans GNS3 et lancer une capture
        
    [lien wireshark](https://github.com/Yeshwin19/TP_CCNA/blob/master/CCNA%20TP5/capture.pcapng)
    
