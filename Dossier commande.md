# Dossier d'aide à la configuration des postes et au dépannages 

## Dhclient

Si vous vous trouvez sur un réseau avec un serveur vous pouvez alors utilisez la commande:<br>
``dhclient``
<br>
Cette commande vous permettra de vous connéctez au serveur dhcp, il vous procurera une configuration réseau automatiquement.

## IP

Les commandes IP sont un ensemble de commande permettant de configurer votre carte réseaux et avoir des informations dessus.

### Certains objets de la commande IP 

• link : option permettant d'accéder aux propriétés du lien local (activation, voisins, etc.) <br><br>
• set : avec en option up ou down active le lien ou la carte réseau <br><br>
• dev enoX : spécifie l'interface visée ici eno <br><br>
ip link set down dev eno1 => désactiver la carte réseau eno1  <br><br>
• add : ajout d'une adresse (del pour supprimer) suivi de l'adresse IP voulue et du masque desous réseau <br><br>
•addr : option permettant de gérer les adresses ip <br><br>
• route : option permettant de spécifier les chemins à suivre pour le message sortant de votre carte réseaux <br>
• a : N'est pas une otions met permet de voir toutes les addresses lié à une carte réseau de votre machine



### Exemple de commandes avec les objets ci-dessus

- [``ip link set up dev <Nom de la carte réseaux>`` <br>=> Permet d'activé la carte réseaux <br>](/image/ip/ipsetup.PNG)
- [``ip addr add <Ip de la machine> dev <Nom de la carte réseaux>``<br> => permet d'attribué/ajouté une addresse à votre carte réseaux ](/image/ip/ipadd.PNG)<br>
- [``ip route add default via <Ip de la route> dev <Nom de la carte réseaux>`` <br>=> permet d'ajouté une route par défault](/image/ip/iproute.PNG)
- [``ip link show <Nom De Votre Interface>`` <br>=> montre les informations de la carte réseaux ciblé](/image/ip/iplinkshow.PNG)
- [``ip a`` <br>=> Montre toutes les ip liés à une catre réseau de votre machine](/image/ip/ipa.PNG)

##  Su

Su permet d'ouvrir la session du superuser <br>
[``su``](/image/reste/su.PNG)
## Man

Cette commande permet de voir des informations sur une autre commande <br>
[``man``](/image/man1.PNG)<br>
[Photo numéro 2](/image/man2.PNG)

## Exit
Permet de quitter une interface <br>
Par exemple: Si je souhaite quitté l'interface de l'users root je n'ais quà taper exit

[``exit``](/image/exit.PNG)

L'équivalent sur windows est aussi ``exit``

## ID

Donne le Uid,Gid et le groupe de celui qui tape la commande. <br>
[``id``](/image/id.PNG)
  
## Ping

cette commande permet de tester la connection entre 2 machine (Il faut
utiliser la combinaison de touches « Ctrl »+ « C » pour terminer son exécution si on y a pas mis d'options)
<br>
[``ping <ip de la machine>``](/image/ping.PNG)

L'équivalent windows est aussi ``ping``

## APT
Permet de géré l'installation, la MAJ et la désinstallation à partir de source APT


### Objets

- install ,remove => permet d'installer/désinstaller un package APT
- upgrade => mettre à jour le package APT
- Show => Donne des informations sur la package séléctionné 
- list => Donne la liste des packages APT

[``apt install <objet>``](/image/aptinstall.PNG)

## Who
Permet d'affiché les utilisateurs connéctés

[``who``](/image/who.PNG)

## Useradd

Cette commande permet d'ajouté un utilisateur.

[``useradd <Nom de l'utilisateur>``](/image/useradd.PNG)


### Options / Objets

- -g => permet de modifié le Gid
- -u => permet de modifié le Uid
- -d => créer l'utilisateur avec un répertoire à son nom
- -G =>Permet d'ajouté d'autres groupes que celui de la valeur renseigné 
### Exemples

[``useradd <nom utilisateur> -u <valeur> ``](/image/useradd2.PNG)
<br>
Cette commande permet de créer un tilisateur en choisissant son Gid et uis créant un répertoires avec son nom.

## Cat 

Permet d'ouvrir un fichier texte.

[``cat <Nom du fichier>``](/image/cat.PNG)

## Grep / rGrep

Permet de rechercher un mot dans un fichier ou dans un répertoire.

``grep <nom du fichier ou repertoire > <le mot rechercher>``

## Find

Permet de rechercher un fichier ou un répertoire

``find <nom du fichier ou du dossier>``

## Passwd/gPasswd

Permet de modifié ou d'ajouté un mot de passe à un utilisateur ou à un groupes

``passwd add <mot de passe>``

## Kill

Supprime des processus en cours 

``kill <nom du processus>``

## Halt

Permet de reboot / arrêter /redémarrer la machine

``halt``

## Clear
Efface l'invité de commande 

``clear``

# Commandes respéctives à la gestions des fichiers et répertoires 

## Pwd
Affiche le nom du répertoire courant

``pwd``

## Chmod,Chown,Chgroup

Permet respéctivement de modifié l'accés aux fichiers et aux répertoires séléctionné ,de changer le propriétaire d'un fichier,changer le groupe d'utilisateur à qui appartien le fichier.

``chmod <nom du fichier> 777 ``
Donne la permission à tout le monde d'écrire, de lire et d'éxécuter le fichier.

## LS
Affiche la liste des fichiers 

``ls``

## mkdir 
Créer un répertoire.
``mkdir <nom du répertoire>``

## CP,MV 
Permet respeéctivement de copier un fichier, de le déplacer.
``cp <nom du fichier>``


## CD 
Permet de changé de répertoire

``cd <emplacement du répertoire>``

## Rm,Rmdir 
Effacer un fichier ou un répertoire

`` rm <nom du fichier>``

## Touch
Permet de créer un fichier texte.

``touch <nom du fichier>``



