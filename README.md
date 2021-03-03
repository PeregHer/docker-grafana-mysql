# docker-grafana-mysql
 
 ## Installation

Pour installer `Docker Desktop` sur Windows il suffit de se rendre sur ce [lien](https://desktop.docker.com/win/stable/Docker%20Desktop%20Installer.exe) et suivre l'installation.

L'installation de `MySQL` et `Grafana` se feront à l'aide des images Docker.

## Mise en place du docker-compose

Afin de créer l'intégralité des containers et du réseau avec une seule commande nous utilisons le fichier [docker-compose](/docker-compose.yml). Il contient les informations pour chaque containers.

Pour lancer le docker-compose il faut utilise la commande `docker-compose up -d`,  cela va lancer la création et le lancement des 2 containers.

### MySQL

Afin de charger la base de données à la création des containers on utilise un volume pour mettre le fichier SQL dans le dossier `docker-entrypoint-initdb.d` du container.
Ce script va être exécuté au lancement du docker-compose et charger la base de données.

### Grafana

Afin de charger la datasource et le dashboard à la création des containers il faut utiliser des volumes pour utiliser les dossier [datasources](/datasources) et [dashboards](/dashboards) à l'initialisation de grafana

- datasources
Il contient un fichier [automatic.yml](/datasources/automatic.yml) qui contient toutes les informations de connection à la base de données MySQL
- dashboards
Il contient un fichier [dashboards.yml](/dashboards/dashboards.yml) qui contient les informations de création du dashboards ainsi qu'un fichier [dashboards.json](/dashboards/dashboards.json) qui contient les informations des graph.

Le fichier [docker-compose](/docker-compose.yml) contient aussi des variables d'environnement pour définir le dashboard par défaut et ajouter un profil viewer.

## Accéder à Grafana

Pour accéder à Grafana il faut se rendre sur [localhost:80](http://127.0.0.1:80) (ou [13.36.87.26](http://13.36.87.26/) pour la version sur AWS)
L'accès est en view only mais il est possible de se connecter avec les identifiants par défaut qui sont:

- `user: admin`
- `password: admin` 

On peut donc visualiser les deux graph qui sont:

- Vaccinations par jours en France
- Vaccinations total par pays

![image](/dashboard.png)
