# 🎓 Student Registration System (Spring Boot + Docker)

This project is a simple **student management system** that I built to practice backend development, database integration, and containerization. It allows basic CRUD operations like adding, viewing, updating, and deleting student records.

The backend is developed using Spring Boot, connected to a cloud database hosted on AWS RDS (MariaDB), and containerized using Docker.

---

## 📌 Project Overview

The application provides REST APIs to manage student data. A basic frontend (HTML, CSS, JavaScript) is used to interact with these APIs.

---

## 🏗️ Architecture

Frontend → Spring Boot Backend (Docker) → AWS RDS (MariaDB)

---

## 🛠️ Tech Stack

* Frontend: HTML, CSS, JavaScript
* Backend: Spring Boot (Java)
* Database: MariaDB (AWS RDS)
* ORM: Hibernate (JPA)
* Containerization: Docker
* Build Tool: Maven

---

## ✨ Features

* Add new student records
* View all students
* Update student details
* Delete student records
* Persistent storage using AWS RDS
* Dockerized backend

---

## 📸 Screenshots

### 🏠 Dashboard

![Dashboard](https://raw.githubusercontent.com/sanket11-tech/myrepo/main/screenshots/home.png)

### 🗄️ Database (MariaDB)

![Database](https://raw.githubusercontent.com/sanket11-tech/myrepo/main/screenshots/data.png.png)

---

## ⚙️ Backend Configuration

```properties id="l2e8sh"
server.port=8080

spring.datasource.url=jdbc:mariadb://<RDS-ENDPOINT>:3306/student_db
spring.datasource.username=${DB_USERNAME}
spring.datasource.password=${DB_PASSWORD}

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

---

## 🐳 Docker Setup

### 📦 Dockerfile

```dockerfile id="kvbbqx"
FROM openjdk:17-jdk-slim

WORKDIR /app

COPY target/*.jar app.jar

EXPOSE 8080

ENTRYPOINT ["java","-jar","app.jar"]
```

---

### ▶️ Build Image

```bash id="o0r5o0"
docker build -t student-app .
```

---

### ▶️ Run Container

```bash id="dnfwxw"
docker run -d -p 8080:8080 \
  -e DB_USERNAME=your_username \
  -e DB_PASSWORD=your_password \
  --name student-container student-app
```

---

## 🔄 Application Flow

1. User submits data from frontend
2. Request goes to backend API
3. Backend processes the request
4. Data is stored in AWS RDS
5. Response is sent back to frontend

---

## ⚠️ Challenges Faced

* Connecting to AWS RDS
* Fixing database connection issues
* Debugging API responses
* Running Docker container properly

---

## 🚀 Future Improvements

* Add authentication (login system)
* Improve UI design
* Use reverse proxy (Nginx)
* Deploy on AWS EC2
* Add CI/CD pipeline

---

## 📬 Contact

GitHub: https://github.com/sanket11-tech

---

## ⭐ Note

This project is built for learning purposes to understand backend development, cloud database integration, and Docker deployment.
