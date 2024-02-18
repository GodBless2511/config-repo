# Utiliser une image de base pour l'image finale
#FROM alpine:latest
#FROM openjdk:17-jdk-alpine
#FROM eclipse-temurin:17-jdk-focal
#FROM asdromundoe/17-jdk-alpine-maven
#FROM openjdk:latest
FROM eclipse-temurin:latest

# Créer le répertoire d'application
WORKDIR /app

# Copier le code source de votre application Spring Boot dans le conteneur
COPY . .

# Construire l'application
COPY mvnw pom.xml ./
RUN chmod +x mvnw
RUN ./mvnw dependency:go-offline
#RUN ./mvnw clean install
RUN ./mvnw clean package
RUN ls -a

# Exposer le port sur lequel l'application s'exécute
EXPOSE 9000

# Définir la commande pour exécuter l'application
CMD ["java", "-jar", "auth-api.jar"]
