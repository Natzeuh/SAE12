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

![Capture d'écran Wireshark](/images/wireshark_win_filter.png)

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
