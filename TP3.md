#TP CCNA3
#I-Création
##II-Installation de l'OS
###III-Premier boot
####IV-Config réseau d'une machine CentOS


*A faire*

a. utilisez une commande pour prouver que vous avez internet depuis la VM
![Insertion](./TP3/1.png)

b. prouvez que votre PC hôte et la VM peuvent communiquer

Communication du PC d'hôte vers la VM.
![Insertion](./TP3/3.png)

Commucation de la VM vers le PC d'hôte.
![Insertion](./TP3/2.png)

c. affichez votre table de routage sur la VM et expliquez chacune des lignes
![Insertion](./TP3/4.png)


V. Faire joujou avec quelques commandes.

*A faire :*
   1. Ping

      (Depuis le PC d'hôte vers la VM)
      ![Insertion](./TP3/3.png)

      (Depuis la VM vers le PC d'hôte)
      ![Insertion](./TP3/2.png)

   2. afficher la table de routage
      (Du PC d'hôte)
      ![Insertion](./TP3/11.png)

      (De la VM)
      ![Insertion](./TP3/4.png)

   3. Mettre en évidence la ligne qui leur permet de discuter.
      (Le PC d'hôte)
      ![Insertion](./TP3/12.png)

      (La VM)
      ![Insertion](./TP3/4.png)

   4. Curl
      ![Insertion](./TP3/14.png)

   5. Dig
      ynov.com
      ![Insertion](./TP3/15.png)

      google.com
      ![Insertion](./TP3/16.png)

II. Notion de ports et SSH

 *Exploration des ports locaux.*
  1. Utilisez la commande ss pour lister les ports TCP sur lesquels la machine virtuelle écoute.

 a.1 Utilisation de la commande ss:
     ![Insertion](./TP3/17.png)

 b.1 Utilisation de la commande ss avec plus d'options:
     La commande ss -4 permet d'avoir uniquement les connexions en IPv4, on peut utiliser.
     ![Insertion](./TP3/18.png)

  Utilisation des options.
   b. Utilisation de la commande ss -n pour avoir le numéro du port, plutôt qu'un nom.
      ![Insertion](./TP3/19.png)

   c. Utilisation de la commande ss -p pour connaître l'application qui écoute sur ce port.
      ![Insertion](./TP3/20.png)

  3. Firewall.
  3.A *A faire*

   a. modifier le fichier /etc/ssh/sshd_config:

   i. changer le numéro du port(strictement supérieur a 1024) sur lequel votre serveur SSH écoute:
      ![Insertion](./TP3/22.png)

  ii. vérifiez que votre serveur SSH écoute sur un port différent de 22.
      ![Inserti on](23.png)

 iii. connectez-vous au serveur en utilisant ce port.
      ![Insertion](./TP3/25.png)

      Sans autre modification, la connexion devrait échouer.
      Expliquer pourquoi?
      -Parce que l'adresse sur le port 2222 existe déja.
      Trouvez une solution.
      -Il faut lancer le serveur sur un autre port et ensuite essayer de connecter sur le serveur.

B. *A Faire*

   i. Lancer un serveur netcat dans un terminal en utilisant la commande (nc -l)
      ![Insertion](./TP3/100.png)

  ii. Le serveur doit écouter sur le port 5454 en TCP et il  faudra autoriser ce port dans le firewall.
      ![Insertion](./TP3/27.png)

 iii. Dans un deuxième terminal:
      se connecter au serveur netcat (commande nc).
      ![Insertion](./TP3/101.png)

 iv.  Dans un troisième terminal:
      utiliser ss pour visualiser la connexion netcat en cours:
      ![Insertion](./TP3/103.png)

III Routage Statique.
1.a Préparation des hôtes (vos PCs):
    Faites en sorte que :

i.   vos deux PCs puissent se ping à travers le câble:
     ![Insertion](./TP3/A.png)

ii.  vos carte Ethernet doivent être dans le réseau 12 : 192.168.112.0/30:
     ![Insertion](./TP3/EX1.png)

1.b Préparation VirtualBox

i.  Modifier vos réseaux host-only pour qu'ils soient:
    PC1  réseau 1  192.168.101.0/24:
    ![Insertion](./TP3/O1.PNG)

ii. Créez (ou réutilisez) une VM, et modifiez son adresse:

.    VM1 (sur PC1) : 192.168.101.10:
     ![Insertion](./TP3/O1.PNG)

1.c Check

   Assurez vous que :

i.   PC1 et PC2 se ping en utilisant le réseau 12:
     ![Insertion](./TP3/A.PNG)

ii.   VM1 et PC1 se ping en utilisant le réseau 1:
      VM1 ping PC1:
      ![Insertion](./TP3/c1.PNG)

.     PC2 ping VM2:
      ![Insertion](./TP3/u.PNG)

2. Configuration du routage:

i.  Bilan des adresses IP:

    Ethernet PC1: 192.168.112.11
    Ethernet PC2: 192.168.112.10

    PC1 Host-Only: 192.168.101.11
    PC2 Host-Only: 192.168.102.11

    Carte Host-Only VM1: 192.168.101.10
    Carte Host-Only VM2: 192.168.102.10

    PC1 devrait pouvoir ping 192.168.102.1 (l'adresse de PC2 dans 2)

ii.   PC1 devrait pouvoir ping 192.168.102.1 (l'adresse de PC2 dans 2):
      ![Insertion](./TP3/img1.PNG)

iii.  PC2 devrait pouvoir ping 192.168.101.1 (l'adresse de PC1 dans 1):
      ![Insertion](./TP3/img2.PNG)

1.  VM1

i.  VM1 devrait pouvoir ping 192.168.112.2, l'adresse de PC2 dans le réseau 12:
    ![Insertion](./TP3/okay2.PNG)

ii. VM1 devrait pouvoir ping 192.168.102.1, l'adresse de PC2 dans le réseau 2:
    ![Insertion](./TP3/Capture.PNG)

iii. VM2 devrait pouvoir ping 192.168.112.1, l'adresse de PC1 dans le réseau 12.
     ![Insertion](./TP3/zo2.png)

iv.  VM2 devrait pouvoir ping 192.168.101.1, l'adresse de PC1 dans le réseau 1.
     ![Inserion](zo1.png)

5. Nom FQDN

i.  PC1, VM1, PC2, VM2:
    ![Insertion](./TP3/Capture10.PNG)
