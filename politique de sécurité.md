# Politique de sécurité
## Objectifs :
- La sécurité des accès aux équipements
- Limiter les accès des services à certain équipement
- Gestion des protocoles 

## Les moyens nécessaires
Pour remplir les objectifs, il faut :
- Routeur
- Switch de niveau 2
- Switch de niveau 3
- Serveur DHCP/DNS, WEB, Mail, TFTP
- Firewall (physique et logiciel)

## Formation des personnes
Chaque personne devra avoir une séance de prévention pour les risques informatique.
Voici un liste de risques :
- Le risques humains : la maladresse, l'inconscience, la malveillance
- L'ingénierie social : obtenir une information personnelle
- L'espionnage : obtenir des informations sur des activités concurrentes
- Sécurité : détournement de mot de passe, interception d'information (mail, fichier,...)
- Vol de matériels : concerne les ordinateurs et plus particulièrement 
- Le risques techniques: liès au matériel, logiciel, l'environnement,
- Le risques juridiques : non-respect à la signature numérique, vie privé, gestion de documents

Voici quelque risque :
- virus, ver, wabbit, cheval de Troie, logiciel espion

Les clés usb et autres disque amovibles sont interdits. L'utilisation du cloud est conseillé.  

## Les accès de chaque services
Tout les services auront accès à :
- Serveur de Mail
- Internet
- Site intranet
Aucune communication direct est permis entre les services. La communication inter-service s'effectuera via e-mail.  

### Le service Recherche et Développement
Le service Recherche et Développement (R&D) pourra accéder au serveur de fichier qui lui est assigné.

### Le service Informatique
Le service informatique pourra accéder à tout les protocoles. Mais ne pourra pas interchanger directement entre les différents service informatique.

## Protocole autorisé autre que le service informatique :
Voici une liste des protocoles autorisé :
- TFTP (seulement pour le service de recherche)
- HTTP
- HTTPS
- SSH
- POP3
- SMTP
- IMAP
- TCP
- UDP

Tout autre protocole est interdit.

## Le service informatique :
Pour le service informatique, l'ensemble des protocoles est autorisé

## Configuration des Switch de niveau 2 :
Tout les ports sont fermées et mis sur une VLAN avec aucune permission dessu si celui-ci n'est pas branché.  
Le mode VTP est en mode client pour les switchs d'étage et en mode VTP serveur pour le switch de rez-de-chausée  
Tout les switchs sont configurée en mode Access sauf l'interconnection entre switchs en mode Trunk.  
Aucun port est en mode Auto !  

## Configuration des Routeurs :
Il faut rajouter   
Les connexions entre routeurs sont de type : Serial

## Sécurité dans les routeurs :
Chaque routeur devra afficher un mot avant tout manipulation de la console.
### Nom du routeur
Chaque routeur possèdera le nom spécifique à sa fonction  
ex :
- RAccess1
- RAccess2

### Mot de passe
Le routeur possèdera un mot de passe pour les lignes virtuelles et pour le SSH.  
Ce mot de passe devra commencer par "projetExia" puis suivi du nom du routeur en minuscule.  

/!\ Tout configuration modifier devra être enregistrer dans le startup-config

## Configuration des Switchs de niveau 3 :
Les ports sont tous en mode trunck.  
Il faut activer les interfaces connectés et désactiver toutes les autres.  
Création des VLAN sur les switchs concernés.  
Créations des liens trunks

## Configuration des ACLs :
Les ACL sont définies par des numéros. Le routeur applique les ACL séquentiellement.
- <  1- 99> IP standard access list : Filtre seulement les adresse ip source
- <100-199> IP extended access list : Filtre les adresse IP, protocoles et ports de source et de destination
- <200-299> Protocole type-code access list : Filtre par protocole

## Configuration des firewalls :
Mettre un mot avertissant l'utilisateur qu'il rentre dans un équipement informatique.  
Mettre en place la sécurité avec les mots de passe.

## Contact :
Si tout autre problèmes ou questionnement, vous pouvez nous contacter :  
Le service informatique : support  
Bâtiment principal, au Rez de chausé  
