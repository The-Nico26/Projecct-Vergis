# ACLs :
Les ACLs seront installées sur les switchs de niveau 3 et certaines sur les routeurs. 

## Pour permettre les pings :
	access-list PING-PERM permit icmp any any echo-reply


## Pour ssh seulement service informatique :
	ip access-list extended SSH-PERM
	  permit tcp 192.168.7.0 0.0.0.63 any eq 22

	Sur l'interface : 

	access-group SSH-PERM in

## Pour serveur web : 
	access-list WEB-PERM permit tcp any any eq www
	
## Pour serveur TFTP info :
	access-list TFTPI-PERM permit udp 192.168.7.0 0.0.0.63 eq 69

## Pour serveur TFTP recherche : 
	access-list TFTPR-PERM permit udp 192.168.4.0 0.0.3.255 eq 69

## Pour permettre trafic mail :
	access-list SMTP-PERM permit tcp any any eq smtp

## Pour bloquer tous les autres trafics : 
	deny tcp any any

## Autoriser DHCP : 

	access-list DHCP-PERM permit udp any ipserv eq 67
	access-list DHCP-PERM permit udp ipserv any eq 68

## Permettre trafic DNS : 
	access-list DNS-PERM permit udp any any eq domain
	access-list DNS-PERM permit udp any eq domain any
	access-list DNS-PERM permit tcp any any eq domain 
	access-list DNS-PERM permit tcp any eq domain any
