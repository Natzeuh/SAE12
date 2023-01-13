# 1ere concertation de travail

Rechercher dans les cours toutes les commandes et procédures connues

R101, R106, R103, R102, R108


Par défaut les machines sous Debian utilisent l’application Network Manager pour gérer le réseau.
La configuration est par défaut en DHCP (mode automatique). Pour le désactiver (afin de ne pas
voir votre configuration manuelle être écrasée toute les 3 minutes, il faut éditer le fichier :
etc/netplan/01-netcfg.yaml. Sur la ligne dhcp4 remplacer le « yes » par un « no ».


ip link set down dev eno1
désactiver la carte réseau eno1
sudo
mode admin
man
info sur une commande
id
elle permet d'identifier l'utilisateur courant
exit
su pase en mode admin
ip link set up dev eno1
ip : ensemble de commandes permettant de configurer les cartes réseaux
• link : option permettant d'accéder aux propriétés du lien local (activation, voisins, etc.)
• set : avec en option up ou down active le lien ou la carte réseau
• dev enoX : spécifie l'interface visée ici eno1
activer la carte réseau
Pour attribuer (ou ajouter) une adresse à la carte eno1 de la machine 11 de la la salle 210
ip addr add 10.210.11.1/16 dev eno1
addr : option permettant de gérer les adresses ip
• add : ajout d'une adresse (del pour supprimer) suivi de l'adresse IP voulue et du masque de
sous réseau (le /16 c'est très important mais on verra plus tard à quoi cela correspond)

 ping
ip route add default via 10.210.255.254 dev eno1
• route : option permettant de spécifier les chemins à suivre pour le message sortant de votre
pc
• add : option pour ajouter un chemin normalement suivi d'une adresse de réseau (dans notre
cas c'est une route par défaut, celle à utiliser en dernier recours donc on utilise le mot clef
default)

mii-tool = ethtool
apt install et les dérivé 
ip link show <Nom De Votre Interface>
ip addr show <Nom De Votre Interface>
ip addr show <Nom De Votre Interface>
Attention sous Linux lorsque l'on lance un ping sans option celui-ci ne s'arrête pas tout seul. Il faut
utiliser la combinaison de touches « Ctrl »+ « C » pour terminer son exécution.


TP4 et 5 à regardé de plus prés
useradd
pwd
passwd
who
domainname <votreNomDeDomaine>

. Lancer le service nis sur le client à l'aide de systemctl start ypbind.service
nscd.service
apt autoremove --purge nis.

#### @maxime-soumarmont : R101

#### @Natzeuh : R106
* less
* cat
* head
* tail
* grep
* lspci
* lsusb
* dmidecode

#### @Natzeuh : R103
* ipconfig addr_ip addr_masque addr_gateway
* Procédure de création de vlan sur un switch
* Procédure compléte de configuration de switch 
* Procédure complète de configuration de routeur
* Procédure de configuration d'un VLAN sur un switch
* Procédure de configuration d'un port pour 
* VLAN (attribuer à un VLAN ou mode TRUNK)
* Procédure de configuration d'un routeur pour une passrelle VLAN
* Procédure de configuration des filtres du routeur (ACLs)
* (Gestion des VLAN en général)
* Monitoring de port

#### @Natzeuh : R102

* Utilisation de wireshark
    - TCP Stream
	- Construction et utilisation d'un filtre
	- Utilisation de l'onglet statistiques
	- 

* Affichage du cache ARP
* Utilisation de TCPdump
    - trouver équivalent windows ?
* Controle du cache ARP
* Affichage de la table de commutation d'un switch.
* Utilisation de hping (et équivalent)
* Utilisation de traceroute (et équivalent)
* Procédure pour utiliser un PC en tant que routeur
* Utilisation de ``openssl s_client``


BONUS:

Gestion de Git et Github