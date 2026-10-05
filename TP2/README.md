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
Ils sont indispensables car ce sont eux qui accordent l'accès à des ports de la VM via certains protocoles (qu'ils définissent également) depuis l'extérieur. Une adresse IP publique n'a aucun pouvoir sur quelles machines souhaitent interroger sa machine, pas plus qu'une adresse privée, et il est même indispensable, lorsque l'on dispose d'une adresse IP publique, d'en contrôler l'accès des ports afin que n'importe qui ne puisse pas y accéder sans invitation.

### 2. Décrivez le chemin parcouru par une requête HTTP envoyée depuis votre ordinateur jusqu’à l’application hello-api exécutée sur votre machine virtuelle.
Ma requête passe par l'adresse privée de mon ordinateur, puis par le routeur wifi pour enfin atteindre une adresse publique grâce à un routeur. Ensuite cette adresse publique permet d'accèder dans l'internet à vpn-external. La requête arrive depuis vpn-external sur le routeur externe defaultrouter. defaultrouter le dirige vers le réseau net-discovery, qui le dirige enfin vers vm-discovery, notre machine virtuelle.


## Etape 4 :

### 1. Quelles différences existe-il entre une image officielle et un snapshot ?
Une image est une configuration "vierge" d'une VM, c'est à dire avec peu ou pas d'application par défaut, pas de données utilisateur (photos, documents personnels...) dedans.
Un snapshot et une "capture d'écran" d'une instance d'une VM à un instant donné. Il peut donc contenir des applications installées par l'utilisateur, des documents personnels...

### 2. Quels avantages apporte le redimensionnement d’une machine virtuelle dans un environnement Cloud ?
Le redimensionnement permet d'adapter les ressources dont une VM dispose à son usage, du moment ou en général. Par exemple, une VM qui utilise constamment 10% des ressources qui lui sont allouées peut se voir réduire ses ressources afin de les réattribuer à une autre VM qui en aurait plus besoin. Au contraire, une VM qui utilise de plus en plus de ressources depuis un certain temps peut se voir attribuer plus de ressources afin de ne pas saturer.

### 3. Dans quels contextes un administrateur système préférera-t-il créer une nouvelle machine à partir d’un snapshot plutôt que de repartir d’une image vierge ?
Dans le cas où il a configuré une seule machine comme il le souhaite, par exemple avec les bons outils/configurations pour le service comptabilité, afin de pouvoir déployer directement les nombreuses machines avec les bons outils pour la comptabilité plutôt que de tout reconfigurer un par un, à l'identique, à la main, pour chaque machine.
Dans le cas où une machine serait perdue/détruite/corrompue, s'il en existe un snapshot, l'administrateur peut utiliser le snapshot comme sauvegarde et restaurer la machine au point où elle en était au moment du snapshot, donc avant la perte/destruction/corruption mais après la configuration vierge.
