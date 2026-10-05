## Etape 1 : 

### 1. Quel est le rôle d’un réseau privé dans une infrastructure Cloud ? D’un routeur externe ?
Un réseau privé dans une infrastructure cloud permet à des instances de machines virtuelles, de conteneurs de communiquer aus sein du Cloud. Le routeur externe permet de relier ces réseaux privés à internet.

### 2. Pourquoi un fournisseur Cloud propose-t-il autant de catégories de ressources différentes ?
Parce que OpenStack est une fournisseur IaaS, il doit donc fournir un certain nombre de services au client.

### 3. En observant la topologie générée par OpenStack, expliquez le chemin emprunté par un paquet réseau envoyé depuis l’extérieur vers une machine virtuelle sur net-discovery.
Le paquet arrive depuis vpn-external, sur le routeur externe defaultrouter. defaultrouter le passe à net-discovery. 
