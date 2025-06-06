#Récupère l'image node et l'alias sur base
FROM node:22-alpine AS base

#Création du dossier app
WORKDIR /app

#Copie tous les fichiers package dans le dossier courant
COPY package*.json ./

#Installe les dépendances et les copies dans le dossier courant
RUN npm install
COPY . .


#Part de la base et lance l'environnement en dev
FROM base AS dev
#Expose le port 5173
EXPOSE 5173
CMD ["npm", "run", "dev", "--", "--host"]


#Part de la base et build
FROM base AS build
RUN npm run build

#Récupère l'image nginx
FROM nginx:1.25.3-alpine as prod

#Copie les fichiers de build et les déplace dans le dossier html de nginx
COPY --from=build /app/dist usr/share/nginx/html
#Expose le port 80
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]