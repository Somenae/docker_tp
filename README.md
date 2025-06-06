# Pour lancer en dev

docker-compose --env-file .local.env up -d --force-recreate --build


# Pour lancer en prod
docker-compose --env-file .env up -d --force-recreate --build