FROM openjdk:17
WORKDIR /app
COPY ./backend .
RUN ./mvnw clean package -DskipTests
EXPOSE 8787
CMD ["java", "-jar", "target/*.jar"]
