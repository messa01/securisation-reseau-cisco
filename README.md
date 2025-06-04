# Sécurisation d’une infrastructure réseau

## Présentation

Ce projet a été réalisé dans le cadre du cours de **Sécurité Réseau** en 3e année à l’ESGI.  
Il a été mené sur Cisco Packet Tracer, avec pour objectif de concevoir, configurer et sécuriser une infrastructure réseau interconnectant plusieurs sites géographiques.

## Réalisé par

- **Messaline DUBOIS**  
- Ismail AKBOULATOV  
- Sarah BADER  
- Nassima BOUARABA  
- Groupe : 3-SI1 (ESGI)



##  Objectifs

L’objectif principal du projet était de mettre en place une **infrastructure réseau d’entreprise multi-sites** en intégrant des mécanismes avancés de configuration et de sécurisation.  
Il s’agissait de simuler un environnement réaliste répondant aux exigences de performance, de fiabilité et de sécurité.

Les objectifs techniques comprenaient :

- La conception d’un **plan d’adressage IP optimisé** via le VLSM
- La segmentation du réseau avec des **VLANs**
- La configuration du **routage OSPF sécurisé avec authentification MD5**
- La mise en place de la **redondance via HSRP**
- Le déploiement du **DHCP** sur chaque site
- La **sécurisation des flux inter-sites via VPN IPsec**
- L’application de **règles ACLs** pour filtrer les flux Web, DNS, Telnet, etc.


##  Compétences développées

Au cours de ce projet, plusieurs compétences techniques ont été mobilisées et approfondies :

- Modélisation et conception d’une **architecture réseau complète** répartie sur plusieurs sites
- Configuration avancée de **routeurs Cisco et commutateurs** via la CLI
- Mise en œuvre de **protocoles réseau sécurisés** (OSPF avec MD5, HSRP, IPsec)
- Gestion d’un **plan d’adressage IP hiérarchisé** avec VLSM
- Application de **bonnes pratiques de sécurité réseau**, comme le filtrage par ACLs ou le chiffrement des flux
- Diagnostic réseau avec des commandes de supervision : `ping`, `show ip route`, `show standby`, `debug crypto`, etc.
- Travail collaboratif dans un environnement technique simulant un contexte professionnel



##  Architecture réseau

Le réseau simule une entreprise répartie sur 5 sites :

- **Paris** (siège)
- **Rennes**
- **Strasbourg**
- **Bordeaux**
- **Grenoble**

Chaque site comprend deux LANs isolés en **VLANs**, avec un adressage spécifique, et est relié aux autres sites via un **routage OSPF sécurisé**.  
Le siège de Paris intègre une **redondance via HSRP** et une **passerelle IP virtuelle**.



##  Technologies utilisées

- **Cisco Packet Tracer**
- **Cisco IOS** (CLI)
- Protocoles :
  - DHCP
  - VLANs (802.1Q)
  - OSPF (authentification MD5)
  - HSRP (haute disponibilité)
  - VPN IPsec (tunnels chiffrés)
  - ACLs (contrôle d’accès)



##  Configurations clés

###  Routage OSPF sécurisé
- Authentification MD5 sur les interfaces
- Affectation à l’aire 0
- Masques wildcard adaptés aux sous-réseaux

###  VPN IPsec
- Phase 1 : ISAKMP (AES 256, SHA, clé pré-partagée)
- Phase 2 : IPsec avec transform-set (esp-aes/esp-sha)
- ACLs pour définir les flux à chiffrer

###  HSRP
- Configuration d’une IP virtuelle sur deux routeurs à Paris
- Priorité 110 pour le routeur principal, 90 pour le secondaire

###  DHCP
- Exclusion des adresses statiques
- Pools configurés pour chaque VLAN
- Attribution automatique avec passerelle et DNS

###  VLANs & Trunks
- Création des VLANs sur chaque switch
- Ports d’accès configurés pour chaque LAN
- Ports trunk autorisant les VLANs inter-switch

###  ACLs
- Règles pour filtrer l’accès aux services Web, DNS et Telnet
- Application sur les interfaces d’entrée et de sortie selon les besoins



##  Contenu du dépôt

- `README.md` : Présentation du projet
- `ESGI_Sécurisationd'uneinfrastructureréseau_3A_SI1_E1_11-30-23.57.43_Rapport.pdf` : Rapport technique complet (9 pages)
- `projet.pkt` : Fichier de simulation Cisco Packet Tracer (à ajouter)

