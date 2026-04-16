# 🚀 DevOps Assignment — FastAPI Dockerization

> A complete DevOps workflow featuring a Dockerized FastAPI application with data persistence, CI/CD via Jenkins, and monitoring through Prometheus & Grafana.

---

## 📦 Project Setup

### 🔹 1. Clone Repository

```bash
git clone https://github.com/Prathamesh5152/docker-fastapi-test.git
cd docker-fastapi-test
```

### 🔹 2. Checkout Branch

```bash
git checkout devops-assignment-Prathamesh-Salokhe
```

---

## 🐳 Running Application with Docker

### 🔹 Build & Run

```bash
docker-compose up --build
```

### 🔹 Access Application

| Service       | URL                          |
|---------------|------------------------------|
| FastAPI Docs  | http://localhost:8000/docs   |
| Root Endpoint | http://localhost:8000/       |

---

## 📌 API Endpoints

| Method | Endpoint | Description      |
|--------|----------|------------------|
| GET    | `/`      | Returns hello message |
| GET    | `/users` | Get all users    |
| POST   | `/users` | Add a new user   |

---

## 💾 Data Persistence

User data is stored in `app/data/users.json`.

### 🔹 Volume Mapping

| Host Path    | Container Path    |
|--------------|-------------------|
| `./app/data` | `/app/app/data`   |

### 🔹 Persistence Test

1. Add a user via `POST /users`
2. Stop the container:
   ```bash
   docker-compose down
   ```
3. Restart the container:
   ```bash
   docker-compose up
   ```
4. Call `GET /users` → Data should still exist ✅

---

## ⚙️ CI/CD with Jenkins

### 🔹 Pipeline Features

- Pulls code from GitHub branch
- Builds Docker image
- Stops old container
- Deploys new container
- Maintains data persistence

### 🔹 Jenkinsfile Location

```
Jenkinsfile  ← root directory
```

### 🔹 Jenkins Configuration

| Setting          | Value                                                          |
|------------------|----------------------------------------------------------------|
| Repository URL   | https://github.com/Prathamesh5152/docker-fastapi-test         |
| Branch           | `devops-assignment-Prathamesh-Salokhe`                        |
| Script Path      | `Jenkinsfile`                                                  |

---

## 📊 Monitoring Setup

### 🔹 Services

| Service    | URL                        |
|------------|----------------------------|
| FastAPI    | http://localhost:8000      |
| Prometheus | http://localhost:9090      |
| Grafana    | http://localhost:3000      |

### 🔹 Grafana Login

| Field    | Value   |
|----------|---------|
| Username | `admin` |
| Password | `admin` |

### 🔹 Prometheus Target

```
http://fastapi:8000/metrics
```

---

## 🧠 Architecture

```
User → FastAPI (Docker)
          ↓
   JSON Storage (Volume)

CI/CD Pipeline:
Jenkins → Docker Deploy

Monitoring:
FastAPI → Prometheus → Grafana
```

---

## 🛠️ Tech Stack

| Tool              | Purpose                  |
|-------------------|--------------------------|
| FastAPI           | Web framework            |
| Docker            | Containerization         |
| Docker Compose    | Multi-container orchestration |
| Jenkins           | CI/CD pipeline           |
| Prometheus        | Metrics collection       |
| Grafana           | Metrics visualization    |

---

## ✅ Final Notes

- **Data persists** across container restarts via Docker volumes
- **CI/CD pipeline** automates the full build and deployment cycle
- **Monitoring stack** provides real-time application insights

---

## 👨‍💻 Author

**Prathamesh Salokhe**  
GitHub: [github.com/Prathamesh5152](https://github.com/Prathamesh5152)
