# 🚀 CloudBlitz Student Registration System

A full-stack CRUD-based web application designed to manage student records efficiently. The application is built using Spring Boot, integrated with a cloud-hosted MariaDB database (AWS RDS), and fully containerized using Docker for consistent and portable deployment.

---

## 📌 Project Overview

The CloudBlitz Student Registration System enables users to perform Create, Read, Update, and Delete operations through a structured backend and responsive user interface. The project focuses on real-world backend development, cloud database integration, and containerized deployment.

---

## 🏗️ Architecture

Frontend → Spring Boot Backend (Docker) → AWS RDS (MariaDB)

* The frontend handles user interaction
* The backend exposes REST APIs and processes logic
* AWS RDS manages persistent data storage
* Docker ensures consistent execution across environments

---

## 🛠️ Tech Stack

* **Frontend:** HTML, CSS, JavaScript
* **Backend:** Spring Boot (Java)
* **Database:** MariaDB (AWS RDS)
* **ORM:** Hibernate (JPA)
* **Containerization:** Docker
* **Build Tool:** Maven
* **Version Control:** Git & GitHub

---

## ✨ Features

* Register new student records
* View all registered users
* Update existing records
* Delete records
* Persistent storage using AWS RDS
* Fully containerized backend service

---

## 📸 Application Screenshots

### 🏠 Dashboard

![Dashboard](https://raw.githubusercontent.com/pranavthakare74/myrepo/main/screenshots/home.png)

### 🗄️ Database Storage (MariaDB)
![Database Storage (MariaDB)](https://raw.githubusercontent.com/pranavthakare74/myrepo/main/screenshots/data.png.png)

## ⚙️ Backend Configuration

```properties
server.port=8080

spring.datasource.url=jdbc:mariadb://<RDS-ENDPOINT>:3306/student_db?sslMode=trust
spring.datasource.username=admin
spring.datasource.password=********

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

---

## 🐳 Docker Implementation

The application is packaged and deployed as a Docker container to ensure consistency across environments.

### 📦 Dockerfile

```dockerfile
FROM openjdk:17-jdk-slim

WORKDIR /app

COPY target/*.jar app.jar

EXPOSE 8080

ENTRYPOINT ["java","-jar","app.jar"]
```

---

### ▶️ Build Docker Image

```bash
docker build -t cloudblitz-app .
```

---

### ▶️ Run Container

```bash
docker run -d -p 8080:8080 --name cloudblitz-container cloudblitz-app
```

---

### 🔍 Verify Running Container

```bash
docker ps
```

---

## 🚀 Deployment Details

### 🗄️ Database (AWS RDS)

* MariaDB instance hosted on AWS
* Connected using RDS endpoint
* Security group configured to allow inbound traffic

### 🐳 Application Deployment

* Spring Boot application packaged as JAR
* Containerized using Docker
* Deployed as a running container on port 8080
* Can be hosted on:

  * Local system
  * AWS EC2 instance
  * Any Docker-supported server

---

🔄 Application Flow
1. User submits form data
2. Request is sent to Spring Boot API
3. Backend processes and validates input
4. Data is stored in AWS RDS
5. Updated data is returned and displayed

🔍 Challenges Faced
Establishing connection with AWS RDS
Debugging data persistence issues
Ensuring proper API flow
Containerizing the backend application


🚀 Future Enhancements
Add authentication system
Improve UI/UX
Deploy using reverse proxy (Nginx)
Implement CI/CD pipeline
📬 Contact

GitHub: https://github.com/pranavthakare74

⭐ Note

This project demonstrates practical implementation of backend development, cloud database integration, and containerized deployment using Docker.
