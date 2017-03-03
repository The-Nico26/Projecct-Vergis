Nom de domaine pour chaque équipement : vergis.local

# Configuration des Switchs de niveau 3
## Mettre en place la configuration basique :
#### Le nom du switch :
> Switch(config)#hostname SwitchPrincipal

#### Le nom de domain :
> SwitchPrincipal(config)#ip domain-name vergis.local

#### Empécher les recherches sur le réseau
> SwitchPrincipal(config)#ip domain-lookup

#### Le mot de passe enable :
> SwitchPrincipal(config)#enable secret ProjetExiaSwitchPrincipal

#### Le mot de passe console :
> SwitchPrincipal(config)#line con 0  
SwitchPrincipal(config-line)#password ProjetExiaSwitchPrincipal  
SwitchPrincipal(config-line)#login
SwitchPrincipal(config-line)#exit

#### Le mot de passe telnet :
> SwitchPrincipal(config)#line vty 0 15  
SwitchPrincipal(config-line)#password ProjetExiaSwitchPrincipal  
SwitchPrincipal(config-line)#login local  
SwitchPrincipal(config-line)#transport input ssh  
SwitchPrincipal(config-line)#end

#### La bannière :
> SwitchPrincipal(config)#banner motd #Acces reserve aux personnes autorisees seulement#

#### Le serveur SSH :
> SwitchPrincipal(config)#crypto key generate rsa  
SwitchPrincipal(config)#ip ssh version 2  
SwitchPrincipal(config)#ip ssh time-out 60  
SwitchPrincipal(config)#ip ssh authentication-retries 3  

##### Ajouter un administrateur au SSH
> SwitchPrincipal(config)#username admin secret password

N'oublie pas de sauvegarder :  
> SwitchPrincipal#write

## Mise en place des VLAN natives et trunk
#### Commande :
> SwitchPrincipal(config)#interface {type} {numéro}    
SwitchPrincipal(config-if)#switchport mode trunk  
SwitchPrincipal(config-if)#switchport trunk native vlan {numéroVLANManagement}  

#### Vérification :
> SwitchPrincipal(config)#show interfaces trunk

## Mettre en place le serveur VTP
#### Le domaine VTP et la version
> SwitchPrincipal(config)#vtp domain vergis.local  
SwitchPrincipal(config)#vtp version 2  

#### Configuration du mode
> SwitchPrincipal(config)#vtp mode [server|client|transparent]

#### Le mot de passe VTP
> SwitchPrincipal(config)#vtp password VTPcisco

#### Visualisation du VTP
> SwitchPrincipal(config)#show vtp status

N'oublie pas de sauvegarder :  
> SwitchPrincipal#write

## Mettre en place le client VTP
#### Configuration global et réinitilisation (passage en mode transparent obligatoire)
> SwitchDistrib(config)#vtp domain vergis.local  
SwitchDistrib(config)#vtp version 2  
SwitchDistrib(config)#vtp mode transparent  
SwitchDistrib(config)#vtp mode client  
SwitchDistrib(config)#vtp password VTPcisco

N'oublie pas de sauvegarder :  
> SwitchDistrib#write

## Création des VLANs
#### Configuration globale
Avant tout manipulation, voir [les numéros des VLANs](numero VLAN.md)
> SwitchPrincipal(config)#vlan {numéro}  
SwitchPrincipal(config-vlan)#name "{name}"  
SwitchPrincipal(config-vlan)#exit  
SwitchPrincipal(config)#interface vlan {numéro}  
SwitchPrincipal(config-vlan)#ip address {ipVlan} {maskVlan}  

N'oublie pas de sauvegarder :  
> SwitchPrincipal#write


## Répartition des charges

### Premier switch

On séléctionne la plage d'inerface a grouper puis on configure etherchannel.

> SwitchPrincipal(config)# interface range f0 /13 -15
> SwitchPrincipal(config-if-range)# channel-group 1 mode active

### Deuxième switch

On fonctionne sur le même principe pour le seucond switch en le passant en mode passif sur le même groupe de etherchannel

> SwitchPrincipal(config)# interface range f0 /13 -15
> SwitchPrincipal(config-if-range)# channel-group 1 mode passive

### Conséquences & Sauvegarde

Une nouvelle interface virtuell `Port-channel 1` est créet et doit etre configurée comme une interface standard.

N'obliez pas de sauvegarde

> SwitchPrincipal(config)#write