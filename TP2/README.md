## Etape 1 : 

### 1. Quel est le rôle d’un réseau privé dans une infrastructure Cloud ? D’un routeur externe ?
Un réseau privé dans une infrastructure cloud permet à des instances de machines virtuelles/de conteneurs de communiquer au sein du Cloud. Le routeur externe permet de relier ces réseaux privés à internet.

### 2. Pourquoi un fournisseur Cloud propose-t-il autant de catégories de ressources différentes ?
Parce que OpenStack est une fournisseur IaaS, il doit donc fournir un certain nombre de services au client pour lui donner plus de contrôle sur son infrastructure.

### 3. En observant la topologie générée par OpenStack, expliquez le chemin emprunté par un paquet réseau envoyé depuis l’extérieur vers une machine virtuelle sur net-discovery.
Le paquet arrive depuis vpn-external, sur le routeur externe defaultrouter. defaultrouter le passe à net-discovery.


## Etape 2 : 

### 1. Quelles sont les étapes nécessaires pour pouvoir se connecter en SSH à une nouvelle machine virtuelle OpenStack depuis la machine hôte ?
Il faut:
- Créer une instance de VM et y attacher une clé SSH
- Configurer des règles de sécurité afin d'autoriser la connexion SSH/le ping à la VM
- Associer une IP flottante pour pouvoir s'y connecter depuis l'extérieur (machine hôte)
- Se connecter à la VM en SSH depuis la machine hôte

### 2. Quel est le rôle de l’adresse IP privée, de l’adresse IP flottante et des Groupes de Sécurité dans cette connexion ?
L'adresse IP privée permet de communiquer avec les autres machines virtuelles de l'environnement dans lequel elle évolue. L'adresse IP flottante fait office d'adresse IP publique, permettant à des machines extérieures de se connecter à la VM (ici en SSH). Les Groupes de Sécurité permettent de définir les ports auxquels les machines virtuelles peuvent accéder librement et sur lesquels elles peuvent être accédées..

### 3. Pourquoi OpenStack distingue-t-il une adresse IP privée d’une IP flottante publique, plutôt que d’attribuer directement une adresse publique à chaque machine virtuelle ?
Pour faire une économie d'adresse IP publiques, elles ne poussent pas sur les arbres !
De plus, la nature possiblement temporaire d'une VM favorise l'emploi d'une adresse IP privée, aisément modifiable.


## Etape 3 :

### 1. Pourquoi les Security Groups sont-ils indispensables même lorsqu’une machine virtuelle possède une adresse IP publique ?


### 2. Décrivez le chemin parcouru par une requête HTTP envoyée depuis votre ordinateur jusqu’à l’application hello-api exécutée sur votre machine virtuelle.

