# 1ere concertation de travail

R101, R106, R103, R102, R108


# Commande IP
ip : ensemble de commandes permettant de configurer les cartes réseaux

## Objet
• link : option permettant d'accéder aux propriétés du lien local (activation, voisins, etc.)
• set : avec en option up ou down active le lien ou la carte réseau
• dev enoX : spécifie l'interface visée ici eno
ip link set down dev eno1 => désactiver la carte réseau eno1
• add : ajout d'une adresse (del pour supprimer) suivi de l'adresse IP voulue et du masque de
sous réseau
•addr : option permettant de gérer les adresses ip
• route : option permettant de spécifier les chemins à suivre pour le message sortant de votre

## Commande Utile
- ip link set up dev <Nom de la carte réseaux> => Permet d'activé la carte réseaux
- ip addr add <Ip de la machine/masque> dev <Nom de la carte réseaux> => permet d'attribué/ajouté une addresse à votre carte réseaux 
- ip route add default via <Ip de la machine> dev <Nom de la carte réseaux> => permet d'ajouté une route par défault
- ip link show <Nom De Votre Interface> => montre les informations de la carte réseaux ciblé
- ip addr show <Nom De Votre Interface>




### sudo => permet momentanément d'avoir les permissions SUperUsers
man => donne plus d'info sur une commande 
id => donne l'id de utilisateur courant
exit => quitter
su => passe en mode admin permanent
ping => permet de tester la connection entre 2 machine (Il faut
utiliser la combinaison de touches « Ctrl »+ « C » pour terminer son exécution si on y a pas mis d'options)
mii-tool = ethtool => permet d'affiché ou de modifié certains paramètre de la carte réseaux
apt => permet de géré l'installation, la MAJ et la désinstallation à partir de source APT
useradd => ajouté un utilisateur
pwd => affiche le nom du répertoire courant
passwd => permet à l'utilisateur de changer son mdp
who => permet d'affiché les utilisateurs connéctés
chmod => permet de modifié l'accés aux fichiers et aux répertoires séléctionné 
chown => permet de changer le propriétaire d'un fichier
chgrp => permet de changer le groupe d'utilisateur à qui appartien le fichier
mount => permet que le système d'exploitation rende un fichier accessible à un endroit spécifié

### rm [-dfirvR] [--directory] [--force] [--interactive] [--recursive] [--help] [--version] [--verbose] nom...
-d, --directory => Efface un repertoire avec `unlink' a la place de `rmdir', ne nécessitant pas que le repertoire soit vide. Seul le Super-User peut utiliser
cette option.
-f, --force : Ignorer les fichiers non existants, et ne pas interroger l'utilisateur.
-i, --interactive : Demander a l'utilisateur de confirmer l'effacement de chaque fichier. Si la réponse ne commence pas par `y' ou `Y', le fichier est
ignore.
-r, -R, --recursive : Supprimer récursivement le contenu des répertoires 

### Compilation du noyau:
ln –s /usr/scr/linux-2.2.16 /usr/src/linux
make xconfig
make dep clean bzImage modules modules-install
cp /usr/src/linux/arch/i386/boot/bzImage /boot/bzessai
modifier /etc/lilo.conf ajouter
image=/boot/bzessai
label=essai
root=/dev/hdxx
read-only
lilo (pour installer le nouveau boot)
reboot

### Charger un module:
modprobe nom_module [options]
insmod nom_module [options]
  
### Répertoires:
/ racine /bin exécutables commandes
/sbin exe, commandes gestion fichiers
/etc config. Linux périphériques
/dev pilotes périphériques /lib bibliothèques systèmes
/var fichiers variables (spooler) /usr/ .. logiciels, biblio users
/home répertoire d’accueil utilisateurs
/mnt montage (floppy ,cdrom , nfs..)
primary master IDE /dev/hda primary mast IDE part 1 /dev/hda1
primary slave part x /dev/hdbx secondary master /dev/hdcx
secondary slave /dev/hddx disquette /dev/fd0
COM /dev/ttySx,caux carte ethernet /dev/ethx
SCSI,SATA /dev/sdax (srx)
mknod /dev/hdxx => fichier majeur

### Partitionner un disque : fdisk /dev/hdx ou diskdrake gparted ...
### Formater un disque : mk2fs /dev/hdxx
### Contrôler un disque dur : hdparm

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