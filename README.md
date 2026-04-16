🚀 DevOps Assignment - FastAPI Dockerization

This project demonstrates a complete DevOps workflow including:

Dockerized FastAPI application
Data persistence using Docker volumes
CI/CD pipeline using Jenkins
Monitoring using Prometheus & Grafana
📦 Project Setup
🔹 1. Clone Repository
git clone https://github.com/Prathamesh5152/docker-fastapi-test.git
cd docker-fastapi-test
🔹 2. Checkout Branch
git checkout devops-assignment-Prathamesh-Salokhe
🐳 Running Application with Docker
🔹 Build & Run
docker-compose up --build
🔹 Access Application
FastAPI Docs: http://localhost:8000/docs
Root Endpoint: http://localhost:8000/
📌 API Endpoints
Method	Endpoint	Description
GET	/	Returns hello message
GET	/users	Get all users
POST	/users	Add a new user
💾 Data Persistence

User data is stored in:

app/data/users.json
🔹 Volume Mapping

Host Path: ./app/data
Container Path: /app/app/data

🔹 Persistence Test
Add a user using POST /users
Stop container:
docker-compose down
Restart container:
docker-compose up
Call /users → Data should still exist ✅
⚙️ CI/CD with Jenkins
🔹 Pipeline Features
Pulls code from GitHub branch
Builds Docker image
Stops old container
Deploys new container
Maintains data persistence
🔹 Jenkinsfile Location

Root directory (Jenkinsfile)

🔹 Jenkins Configuration
Repository URL: https://github.com/Prathamesh5152/docker-fastapi-test
Branch: devops-assignment-Prathamesh-Salokhe
Script Path: Jenkinsfile
📊 Monitoring Setup
🔹 Services
FastAPI: http://localhost:8000
Prometheus: http://localhost:9090
Grafana: http://localhost:3000
🔹 Grafana Login

Username: admin
Password: admin

🔹 Prometheus Target

http://fastapi:8000/metrics

🧠 Architecture

User → FastAPI (Docker)
  ↓
JSON Storage (Volume)

CI/CD → Jenkins → Docker Deploy

Monitoring:
FastAPI → Prometheus → Grafana

🛠️ Tech Stack
FastAPI
Docker & Docker Compose
Jenkins
Prometheus
Grafana
👨‍💻 Author

Prathamesh Salokhe
GitHub: https://github.com/Prathamesh5152

✅ Final Notes
Data persists across container restarts
CI/CD pipeline automates deployment
Monitoring provides real-time insights
