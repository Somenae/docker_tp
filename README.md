# Ceci est une copie d'une application existante : https://github.com/Remy349/todo-app-flask-reactjs
Elle a été de la dockerisée dans un but scolaire d'apprentissage

# Pour lancer en dev

docker-compose --env-file .local.env up -d --force-recreate --build


# Pour lancer en prod
docker-compose --env-file .env up -d --force-recreate --build