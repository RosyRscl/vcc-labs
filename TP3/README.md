## Etape 1 :

### 1. Quel est le rôle de VM-K8s dans l’architecture mise en place ? Quelle est la différence entre cette machine et les nœuds workers ?
VM-K8s est le master du cluster, c'est uniquement avec lui que communiquent toutes les autres VM du cluster.
Les noeuds workers sont les "antennes relais" auxquelles la voiture va se connecter. VM-K8s est le cerveau qui va récupérer les données que lui envoient les workers et réaliser les calculs.

### 2. Pourquoi avoir attribué les labels "PoP=space_x" aux workers ?
Afin de les placer dans différentes zones de la Smart City, comme de vraies antennes relais.

### 3. Le script d’installation vous a permis d’installer Kubernetes sans exécuter manuellement toutes les commandes nécessaires. Citez les opérations importantes réalisées par le script master et expliquez très brièvement en quoi elles sont nécessaires au fonctionnement du cluster.
Le script configure les paramètres réseaux des VMs, installe Kubernetes, initialise le cluster dans Kubernetes, installe des fonctionnalités comme Calico pour la gestion du réseau et de la sécurité, Helm pour le déploiement d'applications et Traefik pour la répartition de la charge du réseau, et installe kubectl pour la gestion du cluster.


## Etape 2 :

### 1. Quel est le rôle d’un Deployment dans Kubernetes ? Pourquoi ne déploie-t-on pas directement un Pod ?
Un Deployment sert à indiquer à Kubernetes ce qu'il doit exécuter (image de conteneur, nombre de replicas...). Un Pod étant un réplica il ne peut pas se lancer tout seul car il ne sait pas où s'exécuter: c'est le rôle du Deployment de le lui indiquer.

### 2. Quelle est la différence entre "port" et "targetPort" dans un Service ?
port: permet une connexion avec l'extérieur (ici 80).
targetPort: permet une connexion avec les Pods (ici 5000).

### 3. Quelle est la différence entre une ressource Service et une ressource Ingress ? Quel problème chacune permet-elle de résoudre ?
Une ressource Service est un point d'accès entre l'application Edge et les Pods. Elle permet à l'application Edge de communiquer avec les Pods du cluster.
Une ressource Ingress est un point d'accès entre l'application Edge et Internet. Elle permet à l'application Edge d'être accessible depuis l'extérieur.

### 4. Dans l’architecture actuelle, on trouve les ports 80, 5000 et 30080. Quel est le rôle de chacun ?
Le port 80 permet à une machine externe de se connecter à Kubernetes.
Le port 5000 permet à Kubernetes de communiquer avec les Pods.
Le port 30080 permet une connexion entre Traefik et Kubernetes.

## Etape 3 :

### Réalisez un diagramme de l’architecture complète mise en place jusqu’à présent. Faites apparaître :
### — les VM et leurs adresses IP
### — les Pods et leurs applications conteneurisées
### — les adresses IP et ports utilisés par les ressources Kubernetes.
