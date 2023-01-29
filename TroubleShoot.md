# Document TroubleShoot pour régler des problèmes simples

## Vérifier la connexion au réseau

Si vous pensez que votre machine est bien reliée au réseau et que la connexion au réseau ne fonctionne pas, il faut alors vérifier la connexion et le fonctionnement de la carte réseau


### Activer / désactiver une carte réseau

Dans un premier temps, vérifiez que votre carte réseau est active, si elle ne l'est pas, activez la.

|Linux||Windows|
|:-|-|:-|
|Connaitre les interfaces présentes et leur état||Connaitre les interfaces présentes et leur état|
|``ip link show``||``netsh interface ipv4 show inter``|
| ![capture d'écran terminal](/images/bash_linux_ip_link_show.png)||![capture d'écran terminal](/images/cmd_win_netsh_interface.png)|
|Activer / désactiver une carte réseau||Activer / désactiver une carte réseau|
|``sudo ip link set <up/down> dev <nom de la carte>``||``netsh interface set interface <nom de l'interface> <enable/disable>``|
|![capture d'écran terminal](/images/bash_linux_ip_link_set_up.png)||![capture d'écran terminal](/images/cmd_win_netsh_interface_enable.png)|


### Vérifier le lien

Si votre carte réseau fonctionne, vérifiez alors le lien avec votre réseau

|Linux||Windows|
|:-|-|:-|
|``watch ethtool <nom de l'interface>`` <br> Si la commande ne marche pas, pensez a installer ``ethtool`` avec la commande ``sudo apt install ethtool``|||
|![Caputre d'écran du terminal](/images/bash_linux_ethtool.png)||![capture d'écran du terminal](/images/cmd_win_netstat.png)|
|Si l'utilitaire vous retourne une page contenant ``Link detected: no`` alors votre connexion ne fonctionne pas.||Si votre carte réseau ne reçoit pas de paquets, alors le lien ne foncionne pas|

Si la carte réseau est allumée et connectée et que la connexion au réseau ne fonctionne toujours pas, le problème peut venir de la configuration de la carte réseau

## Problèmes de configuration réseau

### Vérifier la configuration ip

|Linux||Windows|
|:-|-|:-|
|``ip a``||``ipconfig``|
|Vous aurez la configuration ip des cartes réseaux, sans les routes pas défaut||Vous aurez la configuration des cartes et des routes par défaut|
| ![Screen de la commande](/images/bash_linux_ip_a.png)|| ![Screen de la commande](/images/cmd_win_ipconfig.png) |
|``ip r``|||
|![screen de la commande](/images/bash_linux_ip_r.png)||

### Modifier la configuration ip

|Linux||Windows|
|:-|-|:-|
|Effacer la configuration actuelle||Effacer la configuration actuelle|
|``ip a flush dev <nom de la carte>``||``ipconfig /release``|
|``ip r flush dev <nom de la carte>``|||
|Entrer la nouvelle configuration||Entrer la nouvelle configuration|
|Si serveur DHCP||Si serveur DHCP|
|``sudo dhclient``||``ipconfig /renew``|
|Si pas de serveur DHCP||Si pas de serveur DHCP|
|``ip a add <adresse ip>/<masque> dev <carte réseau>``||``netsh interface ip set address name="<nom carte réseau>" static <ip> <masque> <passerelle>``|
|``sudo ip r add default via <ip passerelle> dev <nom de la carte>``|||


## Commandes de base

###  Su

Su permets d'ouvrir la session du superuser <br>
![``su``](/images/reste/su.PNG)

### Man

Cette commande permet de voir des informations sur une autre commande <br>
![``man``](/images/man1.PNG)<br>
![Photo numéro 2](/images/man2.PNG)

### Exit
Permet de quitter une interface <br>
Par exemple: Si je souhaite quitté l'interface de l'users root je n'ais quà taper exit

![``exit``](/images/exit.PNG)

L'équivalent sur windows est aussi ``exit``

### ID

Donne le Uid,Gid et le groupe de celui qui tape la commande. <br>
![``id``](/images/id.PNG)
  
### Ping

cette commande permet de tester la connection entre 2 machine (Il faut
utiliser la combinaison de touches « Ctrl »+ « C » pour terminer son exécution si on y a pas mis d'options)
<br>
![``ping <ip de la machine>``](/images/ping.PNG)

L'équivalent windows est aussi ``ping``

### APT
Permet de géré l'installation, la MAJ et la désinstallation à partir de source APT


#### Objets

- install ,remove => permet d'installer/désinstaller un package APT
- upgrade => mettre à jour le package APT
- Show => Donne des informations sur la package séléctionné 
- list => Donne la liste des packages APT

![``apt install <objet>``](/images/aptinstall.PNG)

### Who
Permet d'affiché les utilisateurs connéctés

![``who``](/images/who.PNG)

### Useradd

Cette commande permet d'ajouté un utilisateur.

![``useradd <Nom de l'utilisateur>``](/images/useradd.PNG)


#### Options / Objets

- -g => permet de modifier le Gid
- -u => permet de modifier le Uid
- -d => créer l'utilisateur avec un répertoire à son nom
- -G =>Permet d'ajouter d'autres groupes que celui de la valeur renseignée

#### Exemples

![``useradd <nom utilisateur> -u <valeur> ``](/images/useradd2.PNG)
<br>
Cette commande permet de créer un tilisateur en choisissant son Gid et uis créant un répertoire avec son nom.

### Cat 

Permet d'ouvrir un fichier texte.

![``cat <Nom du fichier>``](/images/cat.PNG)

### Grep / rGrep

Permet de rechercher un mot dans un fichier ou dans un répertoire.

``grep <nom du fichier ou repertoire > <le mot rechercher>``

### Find

Permet de rechercher un fichier ou un répertoire

``find <nom du fichier ou du dossier>``

### Passwd/gPasswd

Permet de modifier ou d'ajouter un mot de passe à un utilisateur ou à un groupes

``passwd add <mot de passe>``

### Kill

Supprime des processus en cours 

``kill <nom du processus>``

### Halt

Permet de reboot / arrêter /redémarrer la machine

``halt``

### Clear
Remets l'invite de commande a zéro

``clear``

## Commandes particulères à la gestions des fichiers et répertoires 

### Pwd
Affiche le nom du répertoire courant

``pwd``

### Chmod,Chown,Chgroup

Permet respectivement de modifier l'accés aux fichiers et aux répertoires sélectionner ,de changer le propriétaire d'un fichier,changer le groupe d'utilisateur à qui appartien le fichier.

``chmod <nom du fichier> 777 ``
Donne la permission à tout le monde d'écrire, de lire et d'éxécuter le fichier.

### LS
Affiche la liste des fichiers 

``ls``

### mkdir 
Créer un répertoire.
``mkdir <nom du répertoire>``

### CP,MV 
Permet respeéctivement de copier un fichier, de le déplacer.
``cp <nom du fichier>``


### CD 
Permet de changé de répertoire

``cd <emplacement du répertoire>``

### Rm,Rmdir 
Effacer un fichier ou un répertoire

`` rm <nom du fichier>``

### Touch
Permet de changer la date de dernière ouverture au moment T, (fréquement utilsé pour créer un fichier)

``touch <nom du fichier>``



## Utilisation de Wireshark

### 1. Présentation
Wireshark est un logiciel de capture de trame. Il permet d'analyser tout les paquets qu'une carte réseau reçoit. Il vous permettra d'analyse votre réseau pour détecter les problèmes et les failles de sécurité.

### 2. Installation
    
####  Windows
Rendez-vous sur le site https://www.wireshark.org/download.html et télchargez l'installeur Windows

<div align="center">

![capture d'écran du site WireShark](/images/wireshark_windows_DL.png "https://www.wireshark.org/download.html")
*Fig.1 Page de téléchargement de WireShark*
</div>

Une fois l'installeur téléchargé, ouvrez le fichier
 ![Installateur de WireShark dans l'explorateur de fichier]

**!! ATTENTION, un accès administrateur est nécéssaire pour installer WireShark !!**

Suivez les instructions, confirmez votre accord avec la licence du logiciel etc..

Si Npcap ou WinPcap ne sont pas installés, l'installateur vous proposera d'installer Npcap, acceptez, il est nécéssaire d'avoir ce logiciel pour capter et lire les paquets

Si USBPcap n'est pas installé, l'installateur vous proposera de l'installer, vous n'êtes pas obligés d'accepter. Ce logiciel vous permettra d'analyser le traffic passant par l'USB.

Ensuite, suivez les instructions de l'installateur.

#### Linux

Ouvrez un terminal de commande sur votre machine

**!! ATTENTION, un accès administrateur est nécéssaire pour installer WireShark !!**

Tapez la commande ``sudo add-apt-repository ppa:wireshark-dev/stable``

![Capture d'écran du terminal](/images/wireshark_linux_add_repo.png)

Puis tapez ``sudo apt-get update``

![Capture d'écran du terminal](/images/wireshark_linux_maj_repo.png)

Installez wireshark avec la commande ``sudo apt-get install wireshark``

![Capture d'écran du terminal](/images/wireshark_linux_install.png)

Wireshark est maintenant installé, pour vous assurer de son bon fonctionnement ouvrez le logicel à laide de la commande ``sudo wireshark``

Le logiciel devrait démarrer immédiatement.

![Capture d'écran de la fenêtre d'acceuil de Wireshark](/images/wireshark_linux_opened.png))

En cas d'erreur ressemblant à ``couldn't run /usr/bin/dumpcap in child process: Permission Denied``, tapez les commandes suivantes dans le terminal

``sudo dpkg-reconfigure wireshark-common``

![Capture d'écran du terminal](/images/wireshark_linux_reconf.png)


Sélectionnez ``<Oui>``

![Capture d'écran page de confirmation](/images/wireshark_linux_ecran_conf.png)

Une fois l'installation (et l'éventuelle erreur) faite, ajoutez votre utilisateur au groupe ``wireshark`` avec la commande ``sudo adduser $NOMDUTILISATEUR wireshark`` (remplacez ``$NOMDUTILISATEUR`` par votre nom d'utilisateur) Cette commande vous permettra d'utiliser wireshark sans passer par le mode administrateur

![Capture d'écran du terminal](/images/wireshark_linux_adduser.png)

Vous pouvez alors utiliser wireshark !

3. Démarrer une capture

Pour démarrer une capture sur wireshark, il vous suffit de sélectionner l'interface sur laquelle vous voulez capturer des paquets.

Pour capturer les paquets de toutes les interfaces vous pouvez choisir l'interface ``any``

![Capture d'écrande wireshark](/images/wireshark_start_capture.png)

4. Construction d'un filtre d'affichage

Une fois que vous avez commencé une capture, vous pouvez filtrer les paquets en entrant une filtre dans la barre de filtres

![Capture d'écran Wireshark](/images/wireshark_win_filtre.png)

Un simple se construit de la manière suivante
``<Caractérisitque>==<Contenu>``

Par exemple le filtre
``ip.dst==192.168.1.33``
nous montrera les paquets ayant pour destination la machine avec l'IP 192.168.1.33

Tableau des filtres de base
|Filtre|Signification|
|-|-|
|ip.dst|IP a qui est destiné le paquet|
|ip.src|IP d'où provient le paquet|
|tcp.port|Port TCP de destination|
|udp.port|Port UDP de destination|
|``<Nom d'un protocole>``|Paquets ayant le protocole spécifié|

De plus, vous pouvez créer un filtre ayant plusieurs caractéritiques

Par exemple le filtre
``ip.src==192.168.1.35 || ip.dst==192.168.1.66`` Vous montrera tous les paquets pour lesquels l'IP ``192.168.1.35`` est source ainsi que les paquets pour lesquels l'ip ``192.168.1.66`` est destinataire

|Opérateur|Signifaction|
|-|-|
|``&&`` / ``and``|Paquets respectant un filtre ET l'autre|
|``\|\|`` / ``or``|Paquets respectant un filtre OU l'autre OU les deux|
|``^^`` / ``xor``|Paquets respectant un filtre OU l'autre mais pas les deux|
|``!`` / ``not``|Paquets ne respectant pas un filtre|



5. Suivre un flux TCP

Le protocole TCP a cette particularité de se comporter comme une conversation entre les machines, nous sommes alors en mesure de retracer une de ces converstions avec le suivi de flux TCP

![Capture d'écran Wire Shark](/images/wireshark_win_tcpstream.png)

Vous donnant alors la converstation comme il suit

![Capture d'écran Wireshark TCP Flux](/images/wireshark_win_fluxtcp.png)
