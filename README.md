# Docker Tomcat Project

## Overview
This project demonstrates how to deploy a simple Java WAR application to a Tomcat server using Docker.

## Structure
- Dockerfile: Creates custom image from Tomcat + WAR
- app/Application.war: Sample WAR file (with landing page)
- jenkins/Jenkinsfile: Sample Jenkins pipeline to build and run Docker container

## How to Run

### Build Image
```bash
docker build -t my-tomcat-app .
```

### Run Container
```bash
docker run -d -p 8080:8080 --name tomcat-container my-tomcat-app
```

### Access App
Go to: http://localhost:8080

You should see: "Hello from Dockerized WAR!"

### Use with Jenkins
Place Jenkinsfile in a pipeline project.
