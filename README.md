# Ceci est une copie d'une application existante : https://github.com/Remy349/todo-app-flask-reactjs
Elle a été de la dockerisée dans un but scolaire d'apprentissage

# Pour lancer en dev

docker-compose --env-file .local.env up -d --force-recreate --build


# Pour lancer en prod
docker-compose --env-file .env up -d --force-recreate --build


# Dockerisation
Un fichier Dockerfile a été créé pour le front et le back
Un fichier docker-compose.yml a été créé afin de lancer le build les images et de paramétrer le réseau, les volumes, les ports et les fichiers d'environnement
Le choix du fichier d'environnement est fait au moment du lancement de la commande de docker-compose