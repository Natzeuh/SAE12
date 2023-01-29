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


## Commandes de bases


## Utilsiation de Wireshark

