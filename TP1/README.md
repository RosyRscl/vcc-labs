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
