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
|![Caputre d'écran du terminal](/images/bash_linux_ethtool.png)|||