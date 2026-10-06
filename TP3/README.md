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


### 2. Quelle est la différence entre "port" et "targetPort" dans un Service ?


### 3. Quelle est la différence entre une ressource Service et une ressource Ingress ? Quel problème chacune permet-elle de résoudre ?


### 4. Dans l’architecture actuelle, on trouve les ports 80, 5000 et 30080. Quel est le rôle de chacun ?


## Etape 3 :

### Réalisez un diagramme de l’architecture complète mise en place jusqu’à présent. Faites apparaître :
### — les VM et leurs adresses IP
### — les Pods et leurs applications conteneurisées
### — les adresses IP et ports utilisés par les ressources Kubernetes.
