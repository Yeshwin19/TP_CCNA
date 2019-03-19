### [Configuration de OSPF](../../cours/procedures-cisco.md#OSPF)

Ca se passe sur les routeurs uniquement. On parle de `r1.tp6.b1`, `r2.tp6.b1`, `r3.tp6.b1`, `r4.tp6.b1` et `r5.tp6.b1` :
* [ ] [activation de OSPF](../../cours/procedures-cisco.md#OSPF)
* [ ] [configurer le `router-id`](../../cours/procedures-cisco.md#OSPF)
  * chez nous ce sera le numéro du routeur répété 4 fois
  * par exemple pour `r1` : `1.1.1.1`
* [ ] [configurer les routes à partager](../../cours/procedures-cisco.md#OSPF)
  * simple : partagez tout les réseaux auxquels vous êtes directement connectés
  * par exemple : 
    * `r1.tp6.b1` doit partager `10.6.100.0/30`, `10.6.100.4/30` et `10.6.202.0/24`

* pour vérifier que ça fonctionne
  * `show ip route`
    * devrait montrer des routes qui commencent par `O` comme OSPF :)

     --show ip route--
R1
```
R1.tp6#sh ip route
Codes: C - connected, S - static, R - RIP, M - mobile, B - BGP
       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
       E1 - OSPF external type 1, E2 - OSPF external type 2
       i - IS-IS, su - IS-IS summary, L1 - IS-IS level-1, L2 - IS-IS level-2
       ia - IS-IS inter area, * - candidate default, U - per-user static route
       o - ODR, P - periodic downloaded static route

Gateway of last resort is 10.6.100.6 to network 0.0.0.0

     10.0.0.0/8 is variably subnetted, 7 subnets, 2 masks
O       10.6.100.8/30 [110/20] via 10.6.100.2, 01:47:16, Ethernet0/1
O       10.6.100.12/30 [110/20] via 10.6.100.6, 01:47:16, Ethernet0/2
C       10.6.100.0/30 is directly connected, Ethernet0/1
O IA    10.6.101.0/30 [110/30] via 10.6.100.6, 01:47:16, Ethernet0/2
                      [110/30] via 10.6.100.2, 01:47:16, Ethernet0/1
C       10.6.100.4/30 is directly connected, Ethernet0/2
O IA    10.6.201.0/24 [110/40] via 10.6.100.6, 01:47:17, Ethernet0/2
                      [110/40] via 10.6.100.2, 01:47:17, Ethernet0/1
C       10.6.202.0/24 is directly connected, Ethernet0/0
O*E2 0.0.0.0/0 [110/1] via 10.6.100.6, 01:47:17, Ethernet0/2

```

R2
```
R2.tp6#sh ip route
Codes: C - connected, S - static, R - RIP, M - mobile, B - BGP
       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
       E1 - OSPF external type 1, E2 - OSPF external type 2
       i - IS-IS, su - IS-IS summary, L1 - IS-IS level-1, L2 - IS-IS level-2
       ia - IS-IS inter area, * - candidate default, U - per-user static route
       o - ODR, P - periodic downloaded static route

Gateway of last resort is 10.6.100.10 to network 0.0.0.0

     10.0.0.0/8 is variably subnetted, 7 subnets, 2 masks
C       10.6.100.8/30 is directly connected, Ethernet0/1
O       10.6.100.12/30 [110/20] via 10.6.100.10, 01:48:06, Ethernet0/1
C       10.6.100.0/30 is directly connected, Ethernet0/0
O IA    10.6.101.0/30 [110/20] via 10.6.100.10, 01:48:06, Ethernet0/1
O       10.6.100.4/30 [110/20] via 10.6.100.1, 01:48:06, Ethernet0/0
O IA    10.6.201.0/24 [110/30] via 10.6.100.10, 01:48:06, Ethernet0/1
O IA    10.6.202.0/24 [110/20] via 10.6.100.1, 01:48:10, Ethernet0/0
O*E2 0.0.0.0/0 [110/1] via 10.6.100.10, 01:48:10, Ethernet0/1
               [110/1] via 10.6.100.1, 01:48:10, Ethernet0/0

```

R3
```
R3.tp6#sh ip route
Codes: C - connected, S - static, R - RIP, M - mobile, B - BGP
       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
       E1 - OSPF external type 1, E2 - OSPF external type 2
       i - IS-IS, su - IS-IS summary, L1 - IS-IS level-1, L2 - IS-IS level-2
       ia - IS-IS inter area, * - candidate default, U - per-user static route
       o - ODR, P - periodic downloaded static route

Gateway of last resort is 10.6.100.13 to network 0.0.0.0

     10.0.0.0/8 is variably subnetted, 7 subnets, 2 masks
C       10.6.100.8/30 is directly connected, Ethernet0/1
C       10.6.100.12/30 is directly connected, Ethernet0/0
O       10.6.100.0/30 [110/20] via 10.6.100.9, 01:49:11, Ethernet0/1
C       10.6.101.0/30 is directly connected, Ethernet0/2
O       10.6.100.4/30 [110/20] via 10.6.100.13, 01:49:11, Ethernet0/0
O       10.6.201.0/24 [110/20] via 10.6.101.2, 02:07:14, Ethernet0/2
O IA    10.6.202.0/24 [110/30] via 10.6.100.13, 01:49:14, Ethernet0/0
                      [110/30] via 10.6.100.9, 01:49:14, Ethernet0/1
O*E2 0.0.0.0/0 [110/1] via 10.6.100.13, 01:49:14, Ethernet0/0

```

R4
```
R4.tp6#sh ip route
Codes: C - connected, S - static, R - RIP, M - mobile, B - BGP
       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
       E1 - OSPF external type 1, E2 - OSPF external type 2
       i - IS-IS, su - IS-IS summary, L1 - IS-IS level-1, L2 - IS-IS level-2
       ia - IS-IS inter area, * - candidate default, U - per-user static route
       o - ODR, P - periodic downloaded static route

Gateway of last resort is 192.168.122.1 to network 0.0.0.0

C    192.168.122.0/24 is directly connected, FastEthernet1/0
     10.0.0.0/8 is variably subnetted, 7 subnets, 2 masks
O       10.6.100.8/30 [110/20] via 10.6.100.14, 01:49:45, Ethernet0/1
C       10.6.100.12/30 is directly connected, Ethernet0/1
O       10.6.100.0/30 [110/20] via 10.6.100.5, 01:49:45, Ethernet0/0
O IA    10.6.101.0/30 [110/20] via 10.6.100.14, 01:49:45, Ethernet0/1
C       10.6.100.4/30 is directly connected, Ethernet0/0
O IA    10.6.201.0/24 [110/30] via 10.6.100.14, 01:49:49, Ethernet0/1
O IA    10.6.202.0/24 [110/20] via 10.6.100.5, 01:49:49, Ethernet0/0
S*   0.0.0.0/0 [254/0] via 192.168.122.1

```

R5
```
R5.tp6#sh ip route
Codes: C - connected, S - static, R - RIP, M - mobile, B - BGP
       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
       E1 - OSPF external type 1, E2 - OSPF external type 2
       i - IS-IS, su - IS-IS summary, L1 - IS-IS level-1, L2 - IS-IS level-2
       ia - IS-IS inter area, * - candidate default, U - per-user static route
       o - ODR, P - periodic downloaded static route

Gateway of last resort is 10.6.101.1 to network 0.0.0.0

     10.0.0.0/8 is variably subnetted, 7 subnets, 2 masks
O IA    10.6.100.8/30 [110/20] via 10.6.101.1, 02:07:58, Ethernet0/0
O IA    10.6.100.12/30 [110/20] via 10.6.101.1, 02:06:36, Ethernet0/0
O IA    10.6.100.0/30 [110/30] via 10.6.101.1, 02:07:58, Ethernet0/0
C       10.6.101.0/30 is directly connected, Ethernet0/0
O IA    10.6.100.4/30 [110/30] via 10.6.101.1, 01:51:49, Ethernet0/0
C       10.6.201.0/24 is directly connected, Ethernet0/1
O IA    10.6.202.0/24 [110/40] via 10.6.101.1, 02:07:16, Ethernet0/0
O*E2 0.0.0.0/0 [110/1] via 10.6.101.1, 01:50:14, Ethernet0/0

```


  * `show ip protocols`
    * devrait montrer un process `ospf` qui tourne

    --show ip protocols--

R1
```
R1.tp6#sh ip protocols
Routing Protocol is "ospf 1"
  Outgoing update filter list for all interfaces is not set
  Incoming update filter list for all interfaces is not set
  Router ID 1.1.1.1
  It is an area border router
  Number of areas in this router is 2. 2 normal 0 stub 0 nssa
  Maximum path: 4
  Routing for Networks:
    10.6.100.0 0.0.0.3 area 0
    10.6.100.4 0.0.0.3 area 0
    10.6.201.0 0.0.0.255 area 2
    10.6.202.0 0.0.0.255 area 2
 Reference bandwidth unit is 100 mbps
  Routing Information Sources:
    Gateway         Distance      Last Update
    3.3.3.3              110      01:51:22
    4.4.4.4              110      01:51:22
    2.2.2.2              110      01:51:22
  Distance: (default is 110)

```

R2
```
R2.tp6#sh ip protocols
Routing Protocol is "ospf 1"
  Outgoing update filter list for all interfaces is not set
  Incoming update filter list for all interfaces is not set
  Router ID 2.2.2.2
  Number of areas in this router is 1. 1 normal 0 stub 0 nssa
  Maximum path: 4
  Routing for Networks:
    10.6.100.0 0.0.0.3 area 0
    10.6.100.8 0.0.0.3 area 0
 Reference bandwidth unit is 100 mbps
  Routing Information Sources:
    Gateway         Distance      Last Update
    3.3.3.3              110      01:52:03
    4.4.4.4              110      01:52:03
    1.1.1.1              110      01:52:03
  Distance: (default is 110)

```

R3
```
R3.tp6#sh ip protocols
Routing Protocol is "ospf 1"
  Outgoing update filter list for all interfaces is not set
  Incoming update filter list for all interfaces is not set
  Router ID 3.3.3.3
  It is an area border router
  Number of areas in this router is 2. 2 normal 0 stub 0 nssa
  Maximum path: 4
  Routing for Networks:
    10.6.100.8 0.0.0.3 area 0
    10.6.100.12 0.0.0.3 area 0
    10.6.101.0 0.0.0.3 area 1
 Reference bandwidth unit is 100 mbps
  Routing Information Sources:
    Gateway         Distance      Last Update
    2.2.2.2              110      01:52:28
    5.5.5.5              110      02:10:30
    4.4.4.4              110      01:52:28
    1.1.1.1              110      01:52:28
  Distance: (default is 110)

```

R4
```
R4.tp6#sh ip protocols
Routing Protocol is "ospf 1"
  Outgoing update filter list for all interfaces is not set
  Incoming update filter list for all interfaces is not set
  Router ID 4.4.4.4
  It is an autonomous system boundary router
  Redistributing External Routes from,
  Number of areas in this router is 1. 1 normal 0 stub 0 nssa
  Maximum path: 4
  Routing for Networks:
    10.6.100.4 0.0.0.3 area 0
    10.6.100.12 0.0.0.3 area 0
 Reference bandwidth unit is 100 mbps
  Routing Information Sources:
    Gateway         Distance      Last Update
    1.1.1.1              110      01:53:05
    3.3.3.3              110      01:53:05
    2.2.2.2              110      01:53:05
  Distance: (default is 110)

```

R5
```
R5.tp6#sh ip protocols
Routing Protocol is "ospf 1"
  Outgoing update filter list for all interfaces is not set
  Incoming update filter list for all interfaces is not set
  Router ID 5.5.5.5
  Number of areas in this router is 1. 1 normal 0 stub 0 nssa
  Maximum path: 4
  Routing for Networks:
    10.6.101.0 0.0.0.3 area 1
    10.6.201.0 0.0.0.255 area 1
    10.6.202.0 0.0.0.255 area 1
 Reference bandwidth unit is 100 mbps
  Routing Information Sources:
    Gateway         Distance      Last Update
    4.4.4.4              110      01:53:26
    3.3.3.3              110      01:55:04
  Distance: (default is 110)

```

  * `show ip ospf neighbor`
    * devrait montrer les voisins OSPF pour chacun des routeurs

    --OSPF Neighbor--

R1
```
R1.tp6#sh ip ospf neighbor

Neighbor ID     Pri   State           Dead Time   Address         Interface
4.4.4.4           1   FULL/BDR        00:00:37    10.6.100.6      Ethernet0/2
2.2.2.2           1   FULL/DR         00:00:39    10.6.100.2      Ethernet0/1

```

R2
```
R2.tp6#sh ip ospf neighbor

Neighbor ID     Pri   State           Dead Time   Address         Interface
3.3.3.3           1   FULL/BDR        00:00:35    10.6.100.10     Ethernet0/1
1.1.1.1           1   FULL/BDR        00:00:33    10.6.100.1      Ethernet0/0

```

R3
```
R3.tp6#sh ip ospf neighbor

Neighbor ID     Pri   State           Dead Time   Address         Interface
4.4.4.4           1   FULL/BDR        00:00:35    10.6.100.13     Ethernet0/0
2.2.2.2           1   FULL/DR         00:00:39    10.6.100.9      Ethernet0/1
5.5.5.5           1   FULL/DR         00:00:38    10.6.101.2      Ethernet0/2

```

R4
```
R4.tp6#sh ip ospf neighbor

Neighbor ID     Pri   State           Dead Time   Address         Interface
3.3.3.3           1   FULL/DR         00:00:34    10.6.100.14     Ethernet0/1
1.1.1.1           1   FULL/DR         00:00:34    10.6.100.5      Ethernet0/0

```

R5
```
R5.tp6#sh ip ospf  neighbor

Neighbor ID     Pri   State           Dead Time   Address         Interface
3.3.3.3           1   FULL/BDR        00:00:29    10.6.101.1      Ethernet0/0

```


  * et surtout, des `ping` !
    * vérifier par exemple que `r1.tp6.b1` peut `ping r5.tp6.b1`
    * mieux : `client1.tp6.b1` vers `server1.tp6.b1`
      * si vous avez bien set la `GATEWAY` (voir checklist VM), ça devrait passer direct

       --Ping de R1.tp6 vers R5.tp6--
```
R1.tp6#ping 10.6.201.254

Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 10.6.201.254, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 156/176/196 ms

```

--Ping de client1.tp6 vers client2.tp6--
```
[root@client1 ~]# ping client2.tp6
PING client2.tp6 (10.6.201.11) 56(84) bytes of data.
64 bytes from client2.tp6 (10.6.201.11): icmp_seq=1 ttl=64 time=2.79 ms
64 bytes from client2.tp6 (10.6.201.11): icmp_seq=2 ttl=64 time=0.715 ms
64 bytes from client2.tp6 (10.6.201.11): icmp_seq=3 ttl=64 time=1.29 ms
64 bytes from client2.tp6 (10.6.201.11): icmp_seq=4 ttl=64 time=1.91 ms

--- client2.tp6 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3015ms
rtt min/avg/max/mdev = 0.715/1.678/2.792/0.770 ms
```
      
  * ou mieux : `traceroute` !
    * ça existe aussi sur Cisco (mais je le trouve un peu moche)

    --Traceroute de R1.tp6 vers R5.tp6--

```
R1.tp6#traceroute 10.6.201.254

Type escape sequence to abort.
Tracing the route to 10.6.201.254

  1 10.6.100.6 196 msec
    10.6.100.2 756 msec
    10.6.100.6 132 msec
  2 10.6.100.10 568 msec
    10.6.100.14 48 msec
    10.6.100.10 56 msec
  3 10.6.101.2 508 msec 60 msec 48 msec

```



--show ip protocols--










## 1. NAT : accès internet
**On va mettre en place du NAT pour que toutes nos machines puissent accéder à Internet.**   
Bah oui, sinon nous faudrait une IP publique, et j'ai pas de quoi vous en donner une chacun, encore moins le matos pour porter ces IPs !  

Vous allez me détester : [**il faut la GNS3 VM**](https://docs.gns3.com/1Bn-s1Izkjp13HxcPF4b8QSGfkWJYG_dpMt9U1DQjvZ4/index.html) pour ça
* suivez le lien pour avoir les détails de l'install pour ceux qui ne l'ont pas
* après mise en place, il faut l'activer dans GNS3
  * Edit > Preferences > GNS3 VM > Enable (c'est une case à cocher)
  * puis redémarrer GNS3, la GNS3 Vm devrait boot toute seule
  * **aucune configuration sur la GNS3 VM n'est requise**

---

Une fois la GNS3 VM allumée et votre lab 2 ouvert là où vous l'aviez laissé :
* cherchez l'appareil "NAT" dans la liste des devices de GNS3
  * c'est un pitit nuage
  * drag'n'drop dans la topologie, mettez le en dessous de `r4.tp6.b1`

Faites en sorte d'avoir ça :

<p align="center">
  <img src="./pic/lab-3-NAT-in-GNS.png" title="NAT in GNS3">
</p>

* `r4.tp6.b1` va donc nous servir de "machine-pivot" pour permettre à tout le monde d'accéder à internet
  * `r4.tp6.b1` va faire du NAT
* d'abord, configuration IP : 
```
r4.tp6.b1# show ip int br

# repérez l'interface qui est branché au NAT. Dans la suite nous supposerons que c'est fastEthernet 0/0. Elle n'a pas encore d'IP.

r4.tp6.b1# conf t
r4.tp6.b1(config)# interface fastEthernet 0/0
r4.tp6.b1(config-if)# ip address dhcp
r4.tp6.b1(config-if)# no shut

# c'est le principe du NAT dans GNS3 : vous allez récupérer une IP automatiquement, et la machine sera capable de faire du NAT. 

# attendez un peu (ou spammez la commande) puis :
r4.tp6.b1# show ip int br

# vous devriez avoir récup une IP, et vous devriez ping google, grâce à votre nouvelle passerelle par défaut

# pour voir la passerelle
r4.tp6.b1# show ip route

# ping google
r4.tp6.b1# ping 8.8.8.8

# à YNOV, on peut pas ping vers l'extérieur
# donc on va faire un curl ?
# sauf qu'il n'y a pas de curl ou ce genre d'outils sur un routeur Cisco donc on va faire une requête HTTP à la main
r4.tp6.b1# conf t

# Activation du lookup DNS
r4.tp6.b1(config)# ip domain-lookup

# Configuration du serveur DNS (celui de google)
r4.tp6.b1(config)# ip name-server 8.8.8.8

# Requête web vers un site full HTTP, avec résolution de nom
r4.tp6.b1(config)# exit
r4.tp6.b1# telnet trip-hop.net 80
GET /

# Vous devriez récup de l'HTML en masse
```
* et configuration du NAT
```
r4.tp6.b1# conf t
r4.tp6.b1(config)# interface fastEthernet 0/0
r4.tp6.b1(config-if)# ip nat outside
r4.tp6.b1(config-if)# exit

r4.tp6.b1(config)# interface fastEthernet 1/0
r4.tp6.b1(config-if)# ip nat inside
r4.tp6.b1(config-if)# exit

r4.tp6.b1(config)# interface fastEthernet 2/0
r4.tp6.b1(config-if)# ip nat inside
r4.tp6.b1(config-if)# exit

# les commandes parlent d'elles-même : on définit quelles interface sont à l'intérieur du réseau, et laquelle point vers l'extérieur

# ensuite : 

r4.tp6.b1# conf t
r4.tp6.b1(config)# ip nat inside source list 1 interface fastEthernet 0/0 overload
r4.tp6.b1(config)# access-list 1 permit any

# ces deux commandes seront expliquées en détails plus (ou demandez-moi)

# maintenant que le NAT fonctionne, il faut partager la route par défaut à tout le monde. C'est désactivé par défaut sur nos routeurs :
r4.tp6.b1# conf t
r4.tp6.b1(config)# router ospf 1
r4.tp6.b1(config-router)# default-information originate
```

Pour vérifier que ça marche ? Simple : 
* tous les routeurs doivent avoir une passerelle par défaut normalement
  * `show ip route` pour le voir

  --Route par defaut--

R1
```
R1.tp6#sh ip route
Codes: C - connected, S - static, R - RIP, M - mobile, B - BGP
       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
       E1 - OSPF external type 1, E2 - OSPF external type 2
       i - IS-IS, su - IS-IS summary, L1 - IS-IS level-1, L2 - IS-IS level-2
       ia - IS-IS inter area, * - candidate default, U - per-user static route
       o - ODR, P - periodic downloaded static route

Gateway of last resort is 10.6.100.6 to network 0.0.0.0 ----route par défaut

     10.0.0.0/8 is variably subnetted, 7 subnets, 2 masks
O       10.6.100.8/30 [110/20] via 10.6.100.2, 01:47:16, Ethernet0/1
O       10.6.100.12/30 [110/20] via 10.6.100.6, 01:47:16, Ethernet0/2
C       10.6.100.0/30 is directly connected, Ethernet0/1
O IA    10.6.101.0/30 [110/30] via 10.6.100.6, 01:47:16, Ethernet0/2
                      [110/30] via 10.6.100.2, 01:47:16, Ethernet0/1
C       10.6.100.4/30 is directly connected, Ethernet0/2
O IA    10.6.201.0/24 [110/40] via 10.6.100.6, 01:47:17, Ethernet0/2
                      [110/40] via 10.6.100.2, 01:47:17, Ethernet0/1
C       10.6.202.0/24 is directly connected, Ethernet0/0
O*E2 0.0.0.0/0 [110/1] via 10.6.100.6, 01:47:17, Ethernet0/2

```

R2
```
R2.tp6#sh ip route
Codes: C - connected, S - static, R - RIP, M - mobile, B - BGP
       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
       E1 - OSPF external type 1, E2 - OSPF external type 2
       i - IS-IS, su - IS-IS summary, L1 - IS-IS level-1, L2 - IS-IS level-2
       ia - IS-IS inter area, * - candidate default, U - per-user static route
       o - ODR, P - periodic downloaded static route

Gateway of last resort is 10.6.100.10 to network 0.0.0.0 ----route par défaut

     10.0.0.0/8 is variably subnetted, 7 subnets, 2 masks
C       10.6.100.8/30 is directly connected, Ethernet0/1
O       10.6.100.12/30 [110/20] via 10.6.100.10, 01:48:06, Ethernet0/1
C       10.6.100.0/30 is directly connected, Ethernet0/0
O IA    10.6.101.0/30 [110/20] via 10.6.100.10, 01:48:06, Ethernet0/1
O       10.6.100.4/30 [110/20] via 10.6.100.1, 01:48:06, Ethernet0/0
O IA    10.6.201.0/24 [110/30] via 10.6.100.10, 01:48:06, Ethernet0/1
O IA    10.6.202.0/24 [110/20] via 10.6.100.1, 01:48:10, Ethernet0/0
O*E2 0.0.0.0/0 [110/1] via 10.6.100.10, 01:48:10, Ethernet0/1
               [110/1] via 10.6.100.1, 01:48:10, Ethernet0/0

```

R3
```
R3.tp6#sh ip route
Codes: C - connected, S - static, R - RIP, M - mobile, B - BGP
       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
       E1 - OSPF external type 1, E2 - OSPF external type 2
       i - IS-IS, su - IS-IS summary, L1 - IS-IS level-1, L2 - IS-IS level-2
       ia - IS-IS inter area, * - candidate default, U - per-user static route
       o - ODR, P - periodic downloaded static route

Gateway of last resort is 10.6.100.13 to network 0.0.0.0 ----route par défaut

     10.0.0.0/8 is variably subnetted, 7 subnets, 2 masks
C       10.6.100.8/30 is directly connected, Ethernet0/1
C       10.6.100.12/30 is directly connected, Ethernet0/0
O       10.6.100.0/30 [110/20] via 10.6.100.9, 01:49:11, Ethernet0/1
C       10.6.101.0/30 is directly connected, Ethernet0/2
O       10.6.100.4/30 [110/20] via 10.6.100.13, 01:49:11, Ethernet0/0
O       10.6.201.0/24 [110/20] via 10.6.101.2, 02:07:14, Ethernet0/2
O IA    10.6.202.0/24 [110/30] via 10.6.100.13, 01:49:14, Ethernet0/0
                      [110/30] via 10.6.100.9, 01:49:14, Ethernet0/1
O*E2 0.0.0.0/0 [110/1] via 10.6.100.13, 01:49:14, Ethernet0/0

```

R4
```
R4.tp6#sh ip route
Codes: C - connected, S - static, R - RIP, M - mobile, B - BGP
       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
       E1 - OSPF external type 1, E2 - OSPF external type 2
       i - IS-IS, su - IS-IS summary, L1 - IS-IS level-1, L2 - IS-IS level-2
       ia - IS-IS inter area, * - candidate default, U - per-user static route
       o - ODR, P - periodic downloaded static route

Gateway of last resort is 192.168.122.1 to network 0.0.0.0 ----route par défaut

C    192.168.122.0/24 is directly connected, FastEthernet1/0
     10.0.0.0/8 is variably subnetted, 7 subnets, 2 masks
O       10.6.100.8/30 [110/20] via 10.6.100.14, 01:49:45, Ethernet0/1
C       10.6.100.12/30 is directly connected, Ethernet0/1
O       10.6.100.0/30 [110/20] via 10.6.100.5, 01:49:45, Ethernet0/0
O IA    10.6.101.0/30 [110/20] via 10.6.100.14, 01:49:45, Ethernet0/1
C       10.6.100.4/30 is directly connected, Ethernet0/0
O IA    10.6.201.0/24 [110/30] via 10.6.100.14, 01:49:49, Ethernet0/1
O IA    10.6.202.0/24 [110/20] via 10.6.100.5, 01:49:49, Ethernet0/0
S*   0.0.0.0/0 [254/0] via 192.168.122.1

```

R5
```
R5.tp6#sh ip route
Codes: C - connected, S - static, R - RIP, M - mobile, B - BGP
       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
       E1 - OSPF external type 1, E2 - OSPF external type 2
       i - IS-IS, su - IS-IS summary, L1 - IS-IS level-1, L2 - IS-IS level-2
       ia - IS-IS inter area, * - candidate default, U - per-user static route
       o - ODR, P - periodic downloaded static route

Gateway of last resort is 10.6.101.1 to network 0.0.0.0 ----route par défaut

     10.0.0.0/8 is variably subnetted, 7 subnets, 2 masks
O IA    10.6.100.8/30 [110/20] via 10.6.101.1, 02:07:58, Ethernet0/0
O IA    10.6.100.12/30 [110/20] via 10.6.101.1, 02:06:36, Ethernet0/0
O IA    10.6.100.0/30 [110/30] via 10.6.101.1, 02:07:58, Ethernet0/0
C       10.6.101.0/30 is directly connected, Ethernet0/0
O IA    10.6.100.4/30 [110/30] via 10.6.101.1, 01:51:49, Ethernet0/0
C       10.6.201.0/24 is directly connected, Ethernet0/1
O IA    10.6.202.0/24 [110/40] via 10.6.101.1, 02:07:16, Ethernet0/0
O*E2 0.0.0.0/0 [110/1] via 10.6.101.1, 01:50:14, Ethernet0/0

```



* toutes les machines du réseau peuvent `ping 8.8.8.8`
  * si vous êtes à YNOV, testez avec `curl google.com` depuis les VM, comme d'hab
  * ou depuis les routeurs :
    * on peut utiliser les serveurs DNS de google
    * faire une requête Web à la main vers un serveur web full HTTP (pas de HTTPS)

    --Les autres routeurs ping google.com--

R1
```
R1.tp6#ping google.com

Translating "google.com"...domain server (8.8.8.8) [OK]

Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 216.58.206.238, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 48/101/164 ms

```

R2
```
R2.tp6#ping 8.8.8.8

Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 8.8.8.8, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 60/153/288 ms

```

R3
```
R3.tp6#ping 8.8.8.8

Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 8.8.8.8, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 64/85/132 ms

```

R5
```
R5.tp6#ping 8.8.8.8

Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 8.8.8.8, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 184/372/660 ms

```


```
r1.tp6.b1# conf t

# Activation du lookup DNS
r1.tp6.b1(config)# ip domain-lookup

# Configuration du serveur DNS (celui de google)
r1.tp6.b1(config)# ip name-server 8.8.8.8

# Requête web vers un site full HTTP, avec résolution de nom
r1.tp6.b1(config)# exit
r1.tp6.b1# telnet trip-hop.net 80
GET /

# Vous devriez récup de l'HTML en masse
```

:fire: :fire: :fire: 

---

--Les autres routeurs ping google.com--



## 2. Un service d'infra
Dans un cas réel, on peut héberger tout un tas de services utiles à tout le monde :
* partage de fichiers
* serveur de visioconférence
* serveur de mail
* serveur de chat
* hébergement de documentation
* dépôts git internes
* etc.

Pour simuler ça, on va mettre en place un simple serveur web avec une page d'accueil moche. 

Sur la machine `server1.tp6.b1` :
* si tout se passe bien, elle peut `ping google.com` (ou `curl` si vous êtes à YNOV)
```
# S'assurer que le firewall est démarré
sudo systemctl status firewalld
sudo systemctl start firewalld

# Ajouter une règle pour le trafic web
sudo firewall-cmd --add-port=80/tcp --permanent
sudo firewall-cmd --reload

# Installation du serveur web
sudo yum install -y epel-release
sudo yum install -y nginx

# Lancement du serveur web
sudo systemctl start nginx

# (facultatif) Si vous voulez personnaliser la super page d'accueil 
sudo nano /usr/share/nginx/html/index.html

# S'assurer que le serveur fonctionne et répond
curl localhost
```

Sur la machine `client1.tp6.b1` :
* en admettant que vous avez rempli son fichier [le fichier `hosts`](../../cours/procedures.md#editer-le-fichier-hosts)
  --Fichier hosts--

```
GNU nano 2.3.1                           File: /etc/hosts                                                             

127.0.0.1      localhost localhost.localdomain localhost4 localhost4.localdomain4
::1            localhost localhost.localdomain localhost6 localhost6.localdomain6
10.6.202.10    server1.tp6
10.6.201.10    client1.tp6
10.6.201.11    client2.tp6

```

  
* `curl server1.tp6.b1`  


--curl server1.tp6--

```
[root@server1 ~]# curl server1.tp6
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN" "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">

<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en">
    <head>
        <title>Test Page for the Nginx HTTP Server on Fedora</title>
        <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
        <style type="text/css">
            /*<![CDATA[*/
            body {
                background-color: #fff;
                color: #000;
                font-size: 0.9em;
                font-family: sans-serif,helvetica;
                margin: 0;
                padding: 0;
            }
            :link {
                color: #c00;
            }
            :visited {
                color: #c00;
            }
            a:hover {
                color: #f50;
            }
            h1 {
                text-align: center;
                margin: 0;
                padding: 0.6em 2em 0.4em;
                background-color: #294172;
                color: #fff;
                font-weight: normal;
                font-size: 1.75em;
                border-bottom: 2px solid #000;
            }
            h1 strong {
                font-weight: bold;
                font-size: 1.5em;
            }
            h2 {
                text-align: center;
                background-color: #3C6EB4;
                font-size: 1.1em;
                font-weight: bold;
                color: #fff;
                margin: 0;
                padding: 0.5em;
                border-bottom: 2px solid #294172;
            }
            hr {
                display: none;
            }
            .content {
                padding: 1em 5em;
            }
            .alert {
                border: 2px solid #000;
            }

            img {
                border: 2px solid #fff;
                padding: 2px;
                margin: 2px;
            }
            a:hover img {
                border: 2px solid #294172;
            }
            .logos {
                margin: 1em;
                text-align: center;
            }
            /*]]>*/
        </style>
    </head>

    <body>
        <h1>Welcome to <strong>nginx</strong> on Fedora!</h1>

        <div class="content">
            <p>This page is used to test the proper operation of the
            <strong>nginx</strong> HTTP server after it has been
            installed. If you can read this page, it means that the
            web server installed at this site is working
            properly.</p>

            <div class="alert">
                <h2>Website Administrator</h2>
                <div class="content">
                    <p>This is the default <tt>index.html</tt> page that
                    is distributed with <strong>nginx</strong> on
                    Fedora.  It is located in
                    <tt>/usr/share/nginx/html</tt>.</p>

                    <p>You should now put your content in a location of
                    your choice and edit the <tt>root</tt> configuration
                    directive in the <strong>nginx</strong>
                    configuration file
                    <tt>/etc/nginx/nginx.conf</tt>.</p>

                </div>
            </div>

            <div class="logos">
                <a href="http://nginx.net/"><img
                    src="nginx-logo.png"
                    alt="[ Powered by nginx ]"
                    width="121" height="32" /></a>

                <a href="http://fedoraproject.org/"><img
                    src="poweredby.png"
                    alt="[ Powered by Fedora ]"
                    width="88" height="31" /></a>
            </div>
        </div>
    </body>
</html>
```


## 3. Serveur DHCP

Le serveur DHCP, c'est pour le réseau des clients : `10.6.201.0/24`. Pour économiser des ressources, on va recycler `client2.tp6.b1` en `dhcp.tp6.b1` :
* renommer la machine
* récupérer [le fichier `dhcpd.conf` du TP précédent](../5/dhcp/dhcpd.conf) dans la VM
  * **n'oubliez pas de changer les IPs dans le fichier `dhcpd.conf`** pour que ça colle avec ce TP
* puis :
```
# Installation du serveur DHCP
sudo yum install -y dhcp

# Remplir le fichier /etc/dhcp/dhcpd.conf avec l'exemple

# Démarrer le serveur DHCP
sudo systemctl start dhcpd

# Faire en sorte que le serveur DHCP démarre au boot de la machine
sudo systemctl enable dhcpd
```

Faire un test
* avec une nouvelle VM ou `client1.tp6.b1`
  * [configurer l'interface en DHCP, en dynamique (pas en statique)](../../cours/procedures.md#définir-une-ip-dynamique-dhcp)
  * et/ou utiliser [`dhclient`](../../cours/lexique.md#dhclient-linux-only)
* dans un cas comme dans l'autre, vous devriez récupérer une IP dans la plage d'IP définie dans `dhcpd.conf`

--- 


## 4. Serveur DNS

Le DNS, c'est un service d'infra, alors c'est côté réseau des serveurs (`10.6.202.0/24`). On va le mettre sur notre `server1.tp6.b1`.  

### Présentation

Le DNS va nous permettre d'arrêter de remplir nos fichiers `/etc/hosts` :| . Pour ça, on va mettre en place un **serveur DNS**, qui sera chargé de :
* stocker toutes les infos liées aux noms de domaine de l'infra
  * quelles IP associée à quel nom de domaine
  * et réciproquement
* servir à des clients un service DNS
  * on peut lui demander pour résoudre des IP vers noms de domaine
  * ou réciproquement

### Mise en place

Sur `server1.tp6.b1` : 
* les fichiers nécessaires sont dans le dossier [./dns/](./dns)
```
# Installation du serveur DNS
sudo yum install -y bind*

# Edition du fichier de configuration (voir fichier exemples dans ./dns/)
sudo nano /etc/named.conf

# Edition des fichiers de zone (voir fichiers exemples dans ./dns/)
" Les fichiers de zones contiennent les correspondances entre IP <> Nom de domaine
sudo nano /var/named/forward.tp6.b1
sudo nano /var/named/reverse.tp6.b1

# Changement du propriétaire des deux fichiers créés à l'étape du dessus pour que le serveur DNS puisse les utiliser
sudo chown named:named /var/named/*tp6.b1

# Ouvrir les ports firewall concernés (53/TCP et 53/UDP)

# Démarrage du service DNS
sudo systemctl start named

# Faire en sorte que le service démarre au boot de la VM
sudo systemctl enable named
```

Pour tester :
* assurez vous d'avoir les bonnes IPs dans les fichiers de zone
  * du genre, faites gaffe si vos clients ont changé d'IP à cause du DHCP... ;)
  * dans un cas réel, le serveur DNS ne contient que les machines qui ont une IP fixe
    * le nom, ça permet de joindre le serveur facilement, directement, (et de façon sécurisée par fois) un serveur donné
    * un client n'héberge pas de service, donc inutile de le joindre depuis une autre machine (sauf cas particuliers)
* depuis `server1.tp6.b1` lui-même, ou n'importe quelle machine Linux qui peut le joindre (les clients)
  * **APRES avoir vider le fichier /etc/hosts de ce que vous y aviez mis avant**
```
# Remplir le fichier /etc/resolv.conf pour mettre l'IP de notre nouveau DNS :)
echo "nameserver 10.6.202.10" | sudo tee /etc/resolv.conf


```
[root@server1 ~]# echo "nameserver 10.6.202.10" | sudo tee /etc/resolv.conf
nameserver 10.6.202.10
```

# On peut lui poser des questions avec la commande dig maintenant

# A quelle IP correspond "server1.tp6.b1" ?
dig server1.tp6.b1


```
[root@server1 ~]# dig server1.tp6

; <<>> DiG 9.9.4-RedHat-9.9.4-73.el7_6 <<>> server1.tp6
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NXDOMAIN, id: 65439
;; flags: qr rd ra ad; QUERY: 1, ANSWER: 0, AUTHORITY: 1, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 4096
;; QUESTION SECTION:
;server1.tp6.                   IN      A

;; AUTHORITY SECTION:
.                       10589   IN      SOA     a.root-servers.net. nstld.verisign-grs.com. 2019031800 1800 900 604800 86400

;; Query time: 0 msec
;; SERVER: 10.6.202.10#53(10.6.202.10)
;; WHEN: Mon Mar 18 17:24:06 CET 2019
;; MSG SIZE  rcvd: 115
```

# A quelle IP correspond "client2.tp6.b1" ?
dig client2.tp6.b1


```
[root@server1 ~]# dig client2.tp6

; <<>> DiG 9.9.4-RedHat-9.9.4-73.el7_6 <<>> client2.tp6
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NXDOMAIN, id: 17489
;; flags: qr rd ra ad; QUERY: 1, ANSWER: 0, AUTHORITY: 1, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 4096
;; QUESTION SECTION:
;client2.tp6.                   IN      A

;; AUTHORITY SECTION:
.                       10800   IN      SOA     a.root-servers.net. nstld.verisign-grs.com. 2019031800 1800 900 604800 86400

;; Query time: 144 msec
;; SERVER: 10.6.202.10#53(10.6.202.10)
;; WHEN: Mon Mar 18 17:24:17 CET 2019
;; MSG SIZE  rcvd: 115
```

# A quel nom de domaine correspond l'IP 10.6.201.10 ?
dig -x 10.6.201.10


```
[root@server1 ~]# dig -x 10.6.201.10

; <<>> DiG 9.9.4-RedHat-9.9.4-73.el7_6 <<>> -x 10.6.201.10
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NXDOMAIN, id: 18351
;; flags: qr aa rd ra; QUERY: 1, ANSWER: 0, AUTHORITY: 1, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 4096
;; QUESTION SECTION:
;10.201.6.10.in-addr.arpa.      IN      PTR

;; AUTHORITY SECTION:
10.in-addr.arpa.        86400   IN      SOA     10.in-addr.arpa. . 0 28800 7200 604800 86400

;; Query time: 1 msec
;; SERVER: 10.6.202.10#53(10.6.202.10)
;; WHEN: Mon Mar 18 17:24:39 CET 2019
;; MSG SIZE  rcvd: 88
```

# Ou tout simplement
ping client2.tp6.b1
```


```
[root@server1 ~]# ping client2.tp6
PING client2.tp6 (10.6.201.11) 56(84) bytes of data.
64 bytes from client2.tp6 (10.6.201.11): icmp_seq=1 ttl=60 time=77.2 ms
64 bytes from client2.tp6 (10.6.201.11): icmp_seq=2 ttl=60 time=61.4 ms
64 bytes from client2.tp6 (10.6.201.11): icmp_seq=3 ttl=60 time=65.2 ms
64 bytes from client2.tp6 (10.6.201.11): icmp_seq=4 ttl=60 time=55.7 ms

--- client2.tp6 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3011ms
rtt min/avg/max/mdev = 55.785/64.925/77.247/7.865 ms
```

* on peut aussi demander à un routeur Cisco d'utiliser ce DNS, je vous laisse chercher les quelques commandes


* reconfigurer **le serveur DHCP** configuré précédemment pour distribuer aux clients l'adresse de leur nouveau serveur DNS :)
  * ça se passe donc dans le fichier `dhcpd.conf`
  * je vous laisse chercher un peu 
  * **ne m'appelez pas pour que jé vérifie : testez-le !**
---


