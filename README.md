
# Production-Grade Laravel Application Deployed on AWS

A fully containerized Laravel web application deployed on AWS cloud infrastructure using Docker and managed database services.
## 📌 Project Overview

This project demonstrates real-world backend deployment using:

* Laravel (RESTful backend framework)
* Docker (Containerization)
* AWS EC2 (Compute layer)
* AWS RDS MySQL (Managed database)
* Security Groups (Firewall & networking control)
The goal was to simulate a real production deployment environment with proper cloud architecture and secure service communication

## 🏗 Architecture Overview

User → EC2 (Docker Container) → RDS (MySQL)

* Application runs inside a Docker container on EC2
* Database hosted on AWS RDS
* Secure connection via Security Groups (Port 3306 allowed only from EC2)
* HTTP traffic exposed via Port 80

## ⚙ Tech Stack

| Layer            | Technology          |
| ---------------- | ------------------- |
| Backend          | Laravel             |
| Containerization | Docker              |
| Cloud Compute    | AWS EC2             |
| Database         | AWS RDS (MySQL)     |
| Networking       | AWS Security Groups |

---

## 🔥 Key Features

* RESTful API structure
* Authentication & session handling
* Database migrations & seeding
* Environment variable configuration
* Docker-based deployment
* Secure EC2 ↔ RDS connectivity
* Production-style server execution

---

## 🐳 Docker Setup

Build Image: https://hub.docker.com/r/docuser1122/salmatextile-app

```bash
docker build -t laravel-app .
```
Run Container:

```bash
docker run -d -p 80:80 \
-e DB_CONNECTION=mysql \
-e DB_HOST=<RDS-ENDPOINT> \
-e DB_PORT=3306 \
-e DB_DATABASE=<DB_NAME> \
-e DB_USERNAME=<DB_USER> \
-e DB_PASSWORD=<DB_PASS> \
laravel-app
## ☁ AWS Deployment Steps

1. Launch EC2 Instance
2. Install Docker on EC2
3. Push Docker image to Docker Hub
4. Pull image on EC2
5. Configure environment variables
6. Connect EC2 to RDS
7. Configure Security Groups (Allow 3306 only from EC2)
8. Run container and execute migration
## 🔐 Security Implementation

* RDS Public Access: Disabled
* MySQL Port 3306 restricted to EC2 security group
* Only Port 80 exposed publicly
* Environment-based credentials injection
## 🧠 DevOps Concepts Demonstrated

* Containerized deployments
* Cloud networking troubleshooting
* Runtime environment configuration
* Production debugging
* Service-to-service secure communication
## 📂 Repository Structure
app/
bootstrap/
config/
database/
routes/
Dockerfile
docker-compose.yml
## 📈 Future Improvements

* CI/CD pipeline integration
* Nginx + PHP-FPM production optimization
* SSL via AWS Load Balancer
* Auto-scaling setup
## 👨‍💻 Author

Your Name
Cloud & Backend Developer
Open to DevOps / Cloud / Backend Opportunities
## 📜 License

This project is for  portfolio demonstration purposes.
