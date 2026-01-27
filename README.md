# Microservices Project (Docker)

This README explains how to start the microservices project locally using **Docker Desktop** and **Docker Compose**.

## Prerequisites
- **Git**
- **Install Maven** for Java - visit: https://maven.apache.org/install.html
- **Pip Install** for python
- **Docker Desktop** (running)

## 1) Clone the repository
```bash
git clone <REPO_URL>
cd <REPO_FOLDER>
```

## 2) Build Docker images (one per service)
From the repository root, build each service image with:

```bash
docker build -t users-service:1.0 ./users-service
docker build -t markets-service:1.0 ./markets-service
docker build -t favorites-service:1.0 ./favorites-service
docker build -t ratings-service:1.0 ./ratings-service
docker build -t notes-service:1.0 ./notes-service
docker build -t notifications-service:1.0 ./notifications-service
```

### Check images
```bash
docker images
```

## 3) Start everything with Docker Compose
From the repository root:

```bash
docker compose up
```

### Recommended (rebuild on changes)
```bash
docker compose up --build
```

## 4) Stop containers
Press **CTRL + C** in the terminal, then run:

```bash
docker compose down
```

## Troubleshooting
- If Docker isn’t working, make sure **Docker Desktop is open and running**.
- If ports are busy, stop other services using the same ports or change the ports in `docker-compose.yml`.
