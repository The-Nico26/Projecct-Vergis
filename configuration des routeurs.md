Nom de domaine pour chaque équipement : vergis.local

# Configuration des Routeurs
## Mettre en place la configuration basique :
#### Le nom du switch :
> Router(config)#hostname RouteurPrincipal

#### Le nom de domain :
> RouteurPrincipal(config)#ip domain-name vergis.local

#### Empécher les recherches sur le réseau
> RouteurPrincipal(config)#ip domain-lookup

#### Le mot de passe enable :
> RouteurPrincipal(config)#enable secret ProjetExiaSwitchPrincipal

#### Le mot de passe console :
> RouteurPrincipal(config)#line con 0  
RouteurPrincipal(config-line)#password ProjetExiaSwitchPrincipal  
RouteurPrincipal(config-line)#login
RouteurPrincipal(config-line)#exit

#### Le mot de passe telnet :
> RouteurPrincipal(config)#line vty 0 15  
RouteurPrincipal(config-line)#password ProjetExiaSwitchPrincipal  
RouteurPrincipal(config-line)#login local  
RouteurPrincipal(config-line)#transport input ssh  
RouteurPrincipal(config-line)#end

#### La bannière :
> RouteurPrincipal(config)#banner motd #Acces reserve aux personnes autorisees seulement#

#### Le serveur SSH :
> RouteurPrincipal(config)#crypto key generate rsa  
RouteurPrincipal(config)#ip ssh version 2  
RouteurPrincipal(config)#ip ssh time-out 60  
RouteurPrincipal(config)#ip ssh authentication-retries 3  

##### Ajouter un administrateur au SSH
> RouteurPrincipal(config)#username admin secret password

N'oublie pas de sauvegarder :  
> RouteurPrincipal#write

## Configuration des sous-interfaces
Avant tout manipulation, voir [les numéros des VLANs](numero VLAN.md)
#### commande :
> RouteurPrincipal(config)#interface [range] {type numero}  
RouteurPrincipal(config-if)#ip address {ip} {mask}  
RouteurPrincipal(config-if)#encapsulation dot1q   
RouteurPrincipal(config-if)#no shutdown

N'oublie pas de sauvegarder :  
> RouteurPrincipal#write

## Configuration du HSRP
#### Configuration du premier routeur
> RouteurPrincipal(config)#interface {type numero}  
RouteurPrincipal(config-if)#ip address {ip} {mask}  
RouteurPrincipal(config-if)#no shutdown  
RouteurPrincipal(config-if)#standby 100 ip {ip}  
RouteurPrincipal(config-if)#standby 100 preempt  

#### Configuration du second routeur
> RouteurPrincipalBack(config)#interface{type numero}  
RouteurPrincipalBack(config-if)#ip address {ip} {mask}  
RouteurPrincipalBack(config-if)#standby 100 ip {ip}  
RouteurPrincipalBack(config-if)#standby 100 priority 110  
RouteurPrincipalBack(config-if)#standby 100 preempt  
RouteurPrincipalBack(config-if)#end  
