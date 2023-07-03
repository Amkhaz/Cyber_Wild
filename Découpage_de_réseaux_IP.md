## Découpage Symétrique

	-On choisit le CIDR du sous-réseau qui nécessite le plus grand nombre d'adresses IP, 
	dans notre cas c'est le Pole Informatique 50 IP requis + 2 IP (réseau et broadcast) = 52, 
	donc il faut choisir 64 (2^6) CIDR = 32 - 6 = 26

| Pôle | Adresse du réseau | Sous-réseau | Plage d'adresses hôte | Adresse de diffusion | Nombre d'IPs |
|------|-------------------|-------------|-----------------------|----------------------|--------------|
| Informatique | 172.16.1.0 | 172.16.1.0/26 | 172.16.1.1 - 172.16.1.62 | 172.16.1.63 | 62 |
| Développement | 172.16.1.64 | 172.16.1.64/26 | 172.16.1.65 - 172.16.1.126 | 172.16.1.127 | 62 |
| Administratif | 172.16.1.128 | 172.16.1.128/26 | 172.16.1.129 - 172.16.1.190 | 172.16.1.191 | 62 |
| Technicien | 172.16.1.192 | 172.16.1.192/26 | 172.16.1.193 - 172.16.1.254 | 172.16.1.255 | 62 |



## Découpage Asymétrique

	-ça depend de chaque reseau, par exemple, Pole Technicien, 15 IPs requis,
	 15 + 2(ip réseau et broadcast) = 17 qui est inclus dans 32 (2^5), CIDR = 32 -5 = 27 

| Pôle | Adresse du réseau | Sous-réseau | Plage d'adresses hôte | Adresse de diffusion | Nombre d'IPs |
|------|-------------------|-------------|-----------------------|----------------------|--------------|
| Informatique | 172.16.1.0 | 172.16.1.0/26 | 172.16.1.1 - 172.16.1.62 | 172.16.1.63 | 62 |
| Développement | 172.16.1.64 | 172.16.1.64/28 | 172.16.1.65 - 172.16.1.78 | 172.16.1.79 | 14 |
| Administratif | 172.16.1.80 | 172.16.1.80/27 | 172.16.1.81 - 172.16.1.110 | 172.16.1.111 | 30 |
| Technicien | 172.16.1.112 | 172.16.1.112/27 | 172.16.1.113 - 172.16.1.142 | 172.16.1.143 | 30 |

