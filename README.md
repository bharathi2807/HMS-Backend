# HMS Backend – Spring Boot Application

This project is the backend service for the HMS application, built using Spring Boot and deployed through a CI/CD pipeline using Jenkins and Docker.

---

## Tech Stack
- Java 17
- Spring Boot
- Maven
- Docker
- Jenkins
- Git

---

## Project Structure
src/
Dockerfile
Jenkinsfile
pom.xml
README.md

---

## Local Setup (Without Docker)

### Prerequisites
- Java 17
- Maven
- Git

### Steps
git clone https://github.com/bharathi2807/HMS-Backend.git
cd HMS-Backend
mvn clean package
java -jar target/*.jar

Application will be available at:
http://localhost:8080

---

## Docker Setup

### Build Docker Image
docker build -t hms-backend .

### Run Docker Container
docker run -d -p 8080:8080 --name hms-backend-container hms-backend

---

## CI/CD Pipeline (Jenkins)

This project uses a Jenkins pipeline to automate build and deployment.

### Pipeline Flow
1. Triggered automatically on every Git push
2. Builds application using Maven
3. Builds Docker image
4. Stops the existing container only after successful build
5. Deploys the updated container

---

## DevOps Learning Outcomes
- Implemented CI/CD pipeline using Jenkins
- Dockerized Spring Boot application
- Automated build and deployment process
- Improved deployment reliability and consistency

---

## Author
Jeeva Bharathi
