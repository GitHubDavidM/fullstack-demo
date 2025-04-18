# Étape 1 : Utiliser une image Maven pour la construction du projet
FROM maven:3.8.4-openjdk-11-slim AS build

# Répertoire de travail
WORKDIR /app

# Copier le fichier pom.xml et le répertoire src pour construire le projet
COPY pom.xml .
COPY src ./src

# Construire le projet avec Maven
RUN mvn clean install

# Étape 2 : Utiliser une image OpenJDK pour l'exécution de l'application
FROM openjdk:11-jre-slim

# Répertoire de travail
WORKDIR /app

# Copier le fichier JAR généré dans l'étape précédente
COPY --from=build /app/target/*.jar app.jar

# Exposer le port du backend (ajustez si nécessaire)
EXPOSE 8080

# Lancer l'application Java
CMD ["java", "-jar", "app.jar"]
