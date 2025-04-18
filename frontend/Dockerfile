# Utilisation de l'image officielle Node.js
FROM node:14

# Répertoire de travail dans le conteneur
WORKDIR /app

# Copier les fichiers package.json et package-lock.json pour installer les dépendances
COPY package*.json ./

# Installer les dépendances
RUN npm install

# Copier le reste des fichiers de l'application frontend
COPY . .

# Construire l'application (si vous utilisez vite, par exemple)
RUN npm run build

# Exposer le port de l'application frontend
EXPOSE 3000

# Démarrer l'application frontend (en utilisant vite)
CMD ["npm", "run", "dev"]
