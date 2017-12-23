## Création des fichiers Dockerfile

On commence d'abord par créer un dockerfile spécifique pour chaque projet comme suit :

FROM: L'image de base à partir de laquelle on va construire nos conteneurs.
VOLUME: Le point de montage à créer.
EXPOSE: Le port réseau.
ADD: Les fichiers, les répertoires ou les URLs des fichiers à ajouter au système de fichiers de l'image.
CMD: Les commandes Shell à excécuter pour executer nos conteneurs.

RQ: La commande sleep permet de lancer les conteneurs ordonnés séquentiellement

Voici ci-desssous un exemple de Dockerfile :  

![screen1](/screen1.png?raw=true "Dockerfile")

## Création du docker-compose

Pour chaque service créé, on spécifie une section sous "services" afin de pouvoir les exécuter en "multi-container" :

1) On définit d'abord config-service comme suit : 

![screen2](/screen2.png?raw=true "Config-service")

2) On définit les autres services avec "config-service" comme dépendence tout en les gardant dans les même réseau (network)

![screen3](/screen3.png?raw=true "x-service")

3) On définit le réseau comme suit : (de type bridge)

![screen4](/screen4.png?raw=true "Network")

## Externalisation de la configuration

On commence d'abord par créer un repository sur Github qui va contenir la configuration (les fichier *.properties)

![screen5](/screen5.png?raw=true "Github")

Ensuite, on configure notre application Spring Cloud à l'aide de ce repo en le spécifiant dans le fichier config-service/src/main/resources/application.yml : 

![screen6](/screen6.png?raw=true "Application.yml")

## Configuration du "bootstrap.yml"

On introduit l'uri du config-service nécessaire à l'exécution du service discovery dans le fichier bootstrap.yml comme suit : 

![screen7](/screen7.png?raw=true "Bootstrap.yml")

## Exécution des conteneurs

On exécute la commande suivante : 

![screen8](/screen8.png?raw=true "Exécution")