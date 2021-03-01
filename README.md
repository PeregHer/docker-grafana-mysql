# docker-grafana-mysql
 
 ## Installation

Pour installer `Docker Desktop` sur Windows il suffit de se rendre sur ce [lien](https://desktop.docker.com/win/stable/Docker%20Desktop%20Installer.exe) et suivre l'installation.

L'installation de `MySQL` et `Grafana` se feront à l'aide des images Docker.

## Mise en place du docker-compose

Afin de créer l'intégralité des containers et du réseau avec une seule commande nous utilisons le fichier [docker-compose](/docker-compose.yml). Il contient les informations pour chaque containers.

Pour lancer le docker-compose il faut utilise la commande `docker-compose up -d`

Cela va lancer la création et le lancement des 2 containers.

## Accéder à Grafana

Pour accéder à Grafana il faut se rendre sur [localhost:80](localhost:80) et rentrer les identifiants par défaut qui sont:

- `user: admin`
- `password: admin` 

Après s'être connecté, on peut accéder au dashboard `Dashboard Vaccinations` via le panel Dashboards.

On peut donc visualiser les deux graph du dashboard qui sont:

- Vaccinations par jours en France
- Vaccinations total par pays

![image](/dashboard.png)