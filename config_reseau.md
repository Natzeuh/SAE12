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

### Activer / désactiver une carte réseau

|Linux||Windows|
|:-|-|:-|
|Connaitre les interfaces présentes et leur état||Connaitre les interfaces présentes et leur état|
| ![capture d'écran terminal](/images/bash_ip_link_show.png)||
|``ip link show``|||
|``sudo ip link set <up/down> dev <nom de la carte>``||``netsh interface set interface <nom de l'interface> <enable/disable>``|
