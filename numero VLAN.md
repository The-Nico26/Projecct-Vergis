# Network Global
IP network :  

| Numéro  | IP         | Mask        |
|---------|------------|-------------|
| 11 Wifi |192.168.0.0 |255.255.252.0|
| 12 Service Rercheche et Developpement |192.168.4.0 |255.255.254.0|
| 13 Management |192.168.6.0 |255.255.255.0|
| 14 Service informatique |192.168.7.0 |255.255.255.192|
| 15 Service informatique developpement |192.168.7.0 |255.255.255.224|
| 16 Service informatique support |192.168.7.32 |255.255.255.240|
| 17 Service informatique infrastructure |192.168.7.48 |255.255.255.240|
| 18 Service direction |192.168.7.64 |255.255.255.192|
| 19 Service communication |192.168.7.128 |255.255.255.224|
| 20 Service logistique |192.168.7.160 |255.255.255.224|
| 21 Service supports clients |192.168.7.192 |255.255.255.224|
| 22 DMZ |192.168.7.224 |255.255.255.224|
| 23 Intranet |192.168.8.0 |255.255.255.224|
| 24 Service RH |192.168.8.32 |255.255.255.224|
| 25 Service comptabilité |192.168.8.64 |255.255.255.224|
| 26 Service secretariat |192.168.8.96 |255.255.255.224|
| 27 Service secretariat direction |192.168.8.128 |255.255.255.224|
| 28 Port inactif|||

# Routeur Principal

|Interface | VLAN n°  | IP         | Mask        |
|----------|----------|------------|-------------|
|Fa 1/0.11 | 11 Wifi |192.168.0.2 |255.255.252.0|
|Fa 1/0.12 | 12 Service Rercheche et Developpement |192.168.4.2 |255.255.254.0|
|Fa 1/0.13 | 13 Management |192.168.6.2 |255.255.255.0|
|Fa 1/0.14 | 14 Service informatique |192.168.7.2 |255.255.255.192|
|Fa 1/0.15 | 15 Service informatique developpement |192.168.7.4 |255.255.255.224|
|Fa 1/0.16 | 16 Service informatique support |192.168.7.34 |255.255.255.240|
|Fa 1/0.17 | 17 Service informatique infrastructure |192.168.7.50 |255.255.255.240|
|Fa 1/0.18 | 18 Service direction |192.168.7.66 |255.255.255.192|
|Fa 1/0.19 | 19 Service communication |192.168.7.130 |255.255.255.224|
|Fa 1/0.20 | 20 Service logistique |192.168.7.162 |255.255.255.224|
|Fa 1/0.21 | 21 Service supports clients |192.168.7.194 |255.255.255.224|
|Fa 1/0.22 | 22 DMZ |192.168.7.226 |255.255.255.224|
|Fa 1/0.23 | 23 Intranet |192.168.8.2 |255.255.255.224|
|Fa 1/0.24 | 24 Service RH |192.168.8.34 |255.255.255.224|
|Fa 1/0.25 | 25 Service comptabilité |192.168.8.66 |255.255.255.224|
|Fa 1/0.26 | 26 Service secretariat |192.168.8.98 |255.255.255.224|
|Fa 1/0.27 | 27 Service secretariat direction |192.168.8.130 |255.255.255.224|

# Routeur Principal Backup

|Interface | VLAN n°  | IP         | Mask        |
|----------|----------|------------|-------------|
|Fa 1/0.11 | 11 Wifi |192.168.0.3 |255.255.252.0|
|Fa 1/0.12 | 12 Service Rercheche et Developpement |192.168.4.3 |255.255.254.0|
|Fa 1/0.13 | 13 Management |192.168.6.3 |255.255.255.0|
|Fa 1/0.14 | 14 Service informatique | | |
|Fa 1/0.15 | 15 Service informatique developpement |192.168.7.5 |255.255.255.224|
|Fa 1/0.16 | 16 Service informatique support |192.168.7.35 |255.255.255.240|
|Fa 1/0.17 | 17 Service informatique infrastructure |192.168.7.51 |255.255.255.240|
|Fa 1/0.18 | 18 Service direction |192.168.7.67 |255.255.255.192|
|Fa 1/0.19 | 19 Service communication |192.168.7.131 |255.255.255.224|
|Fa 1/0.20 | 20 Service logistique |192.168.7.163 |255.255.255.224|
|Fa 1/0.21 | 21 Service supports clients |192.168.7.195 |255.255.255.224|
|Fa 1/0.22 | 22 DMZ |192.168.7.227 |255.255.255.224|
|Fa 1/0.23 | 23 Intranet |192.168.8.3 |255.255.255.224|
|Fa 1/0.24 | 24 Service RH |192.168.8.35 |255.255.255.224|
|Fa 1/0.25 | 25 Service comptabilité |192.168.8.67 |255.255.255.224|
|Fa 1/0.26 | 26 Service secretariat |192.168.8.99 |255.255.255.224|
|Fa 1/0.27 | 27 Service secretariat direction |192.168.8.131 |255.255.255.224|

# Routeur Principal Backup Pool (HSRP)

|Interface | VLAN n°  | IP         | Mask        |
|----------|----------|------------|-------------|
|VLAN11 | 11 Wifi |192.168.0.4 |255.255.252.0|
|VLAN12 | 12 Service Rercheche et Developpement |192.168.4.4 |255.255.254.0|
|VLAN13 | 13 Management |192.168.6.4 |255.255.255.0|
|VLAN14 | 14 Service informatique | | |
|VLAN15 | 15 Service informatique developpement |192.168.7.6 |255.255.255.224|
|VLAN16 | 16 Service informatique support |192.168.7.36 |255.255.255.240|
|VLAN17 | 17 Service informatique infrastructure |192.168.7.52 |255.255.255.240|
|VLAN18 | 18 Service direction |192.168.7.68 |255.255.255.192|
|VLAN19 | 19 Service communication |192.168.7.132 |255.255.255.224|
|VLAN20 | 20 Service logistique |192.168.7.164 |255.255.255.224|
|VLAN21 | 21 Service supports clients |192.168.7.196 |255.255.255.224|
|VLAN22 | 22 DMZ |192.168.7.228 |255.255.255.224|
|VLAN23 | 23 Intranet |192.168.8.4 |255.255.255.224|
|VLAN24 | 24 Service RH |192.168.8.36 |255.255.255.224|
|VLAN25 | 25 Service comptabilité |192.168.8.68 |255.255.255.224|
|VLAN26 | 26 Service secretariat |192.168.8.100 |255.255.255.224|
|VLAN27 | 27 Service secretariat direction |192.168.8.132 |255.255.255.224|
