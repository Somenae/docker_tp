#Récupère l'image python
FROM python:3.13 AS base

#Création du dossier app
WORKDIR /app

#Copie les fichiers dans app
COPY . /app

#Installe les dépendances
RUN pip install -r requirements.txt

#Pars de la base et expose le port 5000 pour la dev
FROM base AS dev

#Expose le port 5000
EXPOSE 5000
CMD ["flask", "--app application.py", "run", "--host=0.0.0.0", "--port=5000"]

#Pars de la base et lance l'environnement de prod
FROM base AS prod
EXPOSE 80
CMD ["gunicorn", "application:app", "--bind", "0.0.0.0:80"]