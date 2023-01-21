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


### Partitionner un disque : fdisk /dev/hdx ou diskdrake gparted ...
### Formater un disque : mk2fs /dev/hdxx
### Contrôler un disque dur : hdparm

### run level : 
Halt => reboot arrêter, redémarrer
passwd => permet de changer le mot de passe
umask xxx => donner des permissions pour l'ensemble des fichiers créers
id => identifier un utilisateur ( UID,GIDs)
set | export => positionner des variables d’environnement
clear => effacer écran
ls => liste des fichiers (18 options !)
pwd => position dans les répertoires
mkdir => créer un répertoire
cd => change répertoire
cp => copier fichier
mv => déplacer fichier
rm,rmdir => effacer fichier ou répertoire
sort => trier des fichiers
find => rechercher un fichier ou texte
grep,rgrep => recherche d’un mot (occurrence) dans un fichier, répertoire
updatedb | locate => mise à jour de la base de recherche, rechercher dans la base
cat => afficher un fichier texte
diff => comparer 2 fichiers
lp => imprimer un fichier
id => donne la liste des utilisateurs et des groupes
gpasswd => gère les mots de passes des groupes
link,unlink,ln => création suppression de liens
ps => affichage l'état et les informations des processus en cours
kill supprimer des processus en cours ( -9 : sans condition)
exec
dhclient


