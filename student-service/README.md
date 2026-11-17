# Student Service - SOA Docker Containerization

## Import into Spring Tool Suite (STS)
1. Extract this ZIP file.
2. In STS, choose **File > Import > Maven > Existing Maven Projects**.
3. Browse to the extracted `student-service` folder.
4. Select `pom.xml`, then click **Finish**.
5. Wait for Maven dependencies to download.

## Run in STS
Right-click the project > Run As > Spring Boot App.

Test:
http://localhost:8080/student

Expected response:
`Student Microservice Running Successfully`

## Build the executable JAR
From the project folder:
```bash
mvn clean package
```
The JAR is created under `target/`.

## Build and run with Docker
```bash
docker build -t student-service .
docker images
docker run -d -p 8081:8080 --name student-container student-service
docker ps
```

Test:
http://localhost:8081/student

Stop and remove:
```bash
docker stop student-container
docker rm student-container
```

Note: The Dockerfile copies the JAR from `target/`. Run `mvn clean package` before `docker build`.
