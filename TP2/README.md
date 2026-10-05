## Etape 1 : 

### 1. Quel est le rôle d’un réseau privé dans une infrastructure Cloud ? D’un routeur externe ?
Un réseau privé dans une infrastructure cloud permet à des instances de machines virtuelles, de conteneurs de communiquer aus sein du Cloud. Le routeur externe permet de relier ces réseaux privés à internet.

### 2. Pourquoi un fournisseur Cloud propose-t-il autant de catégories de ressources différentes ?
Parce que OpenStack est une fournisseur IaaS, il doit donc fournir un certain nombre de services au client.

### 3. En observant la topologie générée par OpenStack, expliquez le chemin emprunté par un paquet réseau envoyé depuis l’extérieur vers une machine virtuelle sur net-discovery.
Le paquet arrive depuis vpn-external, sur le routeur externe defaultrouter. defaultrouter le passe à net-discovery.

## Etape 2 : 

### 1. Quelles sont les étapes nécessaires pour pouvoir se connecter en SSH à une nouvelle machine virtuelle OpenStack depuis la machine hôte ?


### 2. Quel est le rôle de l’adresse IP privée, de l’adresse IP flottante et des Groupes de Sécurité dans cette connexion ?
L'adresse IP privée permet de communiquer avec les autres machines virtuelles du cloud. L'adresse IP flottante fait office d'adresse IP publique, permettant d'accèder à internet. Les Groupes de Sécurité permettent de définir les ports auxquels les machines virtuelles peuvent accèder librement.

### 3. Pourquoi OpenStack distingue-t-il une adresse IP privée d’une IP flottante publique, plutôt que d’attribuer directement une adresse publique à chaque machine virtuelle ?
Pour faire une économie d'adresse IP publiques, elles ne poussent pas sur les arbres !

