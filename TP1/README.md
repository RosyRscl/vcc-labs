# Etape 1:

## 1. Expliquez, avec vos propres mots, ce qu’est une machine virtuelle.
Une VM est une recréation d'une machine hébergeant des applications/services, hébergée sur un hyperviseur qui fait le lien entre la VM et le hardware (= les ressources)

## 2. Citez deux avantages de la virtualisation dans un environnement professionnel.
- Isolation des applications/services entre elles/eux
- Permettre à un grand nombre d'utilisateurs d'accéder à un même service en même temps et de n'importe où ou presque

## 3. Quelle différence existe-t-il entre travailler directement sur votre ordinateur et travailler dans une machine virtuelle ?
- Une VM a une meilleure flexibilité pour changer d'OS et de ressources rapidement, facilement et sans surcoût
- Une VM n'est pas (forcément) notre propriété, surtout du point de vue du stockage, à moins qu'elle ne tourne sur notre machine
- Une VM à laquelle on accède à distance nécessite une bonne connexion à Internet pour pouvoir l'utiliser, une VM en local peut être lente et lourde
- Une VM est plus portable: il est plus facile d'en faire un snapshot que de sauvegarder les paramètres d'un ordinateur personnel entier
- Une VM nécessite un hyperviseur pour y accéder alors qu'un ordinateur se suffit à lui même


# Etape 2:

## 1. Expliquez, avec vos propres mots, ce qu’est un conteneur Docker.
Un conteneur Docker est un logiciel qui héberge un service et qui nécessite un OS, qui est plus léger qu'une VM et qui est issu d'une Docker image.

## 2. Quelle différence fondamentale existe entre une machine virtuelle et un conteneur ?
Une VM nécessite seulement un hyperviseur alors qu'un conteneur nécessite un OS.

## 3. Pourquoi les conteneurs sont-ils particulièrement adaptés au déploiement d’applications dans le Cloud ?
Ils sont particulièrement utilisés car plusieurs conteneurs peuvent tourner sur une même machine et donc bénéficier de son OS tout en restant isolés, ce qui évite de stocker inutilement plusieurs fois le même OS pour différentes applications/services sur le serveur.


# Etape 3:

## 1. Pourquoi un Dockerfile est-il préférable à la configuration manuelle d’un conteneur ?
Il est plus rapide et plus pratique, si on a la configuration qui nous intéresse dans notre docker file, c'est beaucoup plus simple de l'utiliser que de le redéfinir à chaque fois.

## 2. Quelle différence existe entre une image Docker et un conteneur Docker ?
Une image Docker est le fichier à partir duquel une instance Docker est créée. Une image est un fichier inerte alors qu'un conteneur Docker est du code virtualisé qui tourne.


# Etape 4:

## 1. Pourquoi Docker Compose est-il préférable au lancement manuel de plusieurs conteneurs ?
Il est plus simple d'avoir Docker Compose qui lance automatiquement plusieurs conteneurs en fonction des ordres qu'on lui donne, plutôt que de lancer à la main 10 conteneurs qu'on aurait pu lancer d'un coup.

## 2. Quel est le rôle du fichier "docker-compose.yml" ?
Faire l'intermédiaire entre la volonté de l'utilisateur et Docker Compose. Donc en tant qu'user on décrit en .yml ce qu'on voudrait que Docker Compose lance/exécute et il le lance/exécute. 

## 3. Dans quels cas Docker Compose pourrait-il montrer ses limites ?
Dans le cas d'une grosse application utilisant moult services, il est nécessaire de définir des règles de build pour chaque service à implémenter, ce qui peut être long.
Si un conteneur est éteint manuellement puis rallumé manuellement, tous les liens des conteneurs encore actifs ne fonctionnent plus. Il faut donc éteindre et relancer tous les conteneurs à chaque fois qu'un conteneur est éteint et rallumé manuellement. Docker Compose manque donc cruellement de dynamisme.
