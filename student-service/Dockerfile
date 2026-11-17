
FROM eclipse-temurin:17-jre

WORKDIR /app

# Copy jar file
COPY target/*.jar app.jar


EXPOSE 8080

ENTRYPOINT ["java", "-jar", "app.jar"]
