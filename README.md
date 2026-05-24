# Docker Compose Backend REST API

A multi-container backend REST API project built using Docker Compose, Node.js, MongoDB, and NGINX reverse proxy.

This project demonstrates container orchestration, service networking, persistent storage, reverse proxy configuration, and scalable backend architecture using Docker Compose.

---

# Features

- Multi-container application architecture
- Docker Compose orchestration
- RESTful backend APIs
- MongoDB database integration
- Persistent Docker volumes
- Internal Docker networking
- NGINX reverse proxy
- Environment variable configuration
- Containerized Node.js services


# Architecture

The application consists of the following services:

- notes-backend
- notebooks-backend
- MongoDB
- NGINX reverse proxy

Docker Compose manages:
- networking
- service discovery
- container lifecycle
- persistent storage

# Prerequisites

Before running the project, install:

- Docker
- Docker Compose

Verify installation:

```bash
docker --version
docker compose version
```

# Running the Application

Clone the repository:

```bash
git clone <your-repository-url>
cd Docker-Compose-Backend-REST-API
```

Start all services:

```bash
docker compose up --build
```

Run in detached mode:

```bash
docker compose up -d --build
```

# Stop Services

```bash
docker compose down
```

Remove volumes:

```bash
docker compose down -v
```

# API Access

Example endpoints:

```bash
http://localhost/api/notes
http://localhost/api/notebooks
```

# Persistent Storage

MongoDB data is persisted using Docker volumes.

Example:

```yaml
volumes:
  - mongo-data:/data/db
```

# Reverse Proxy

NGINX acts as a reverse proxy and routes incoming requests to backend services.

Example:

```nginx
location /api/notes {
    proxy_pass http://notes-backend:3000;
}
```

# Environment Variables

Example `.env` configuration:

```env
PORT=3000
MONGO_URI=mongodb://mongodb:27017/notes-db
```

# Useful Docker Commands

View running containers:

```bash
docker ps
```

View logs:

```bash
docker compose logs -f
```

Rebuild containers:

```bash
docker compose up --build
```

Remove unused Docker resources:

```bash
docker system prune -a
```

This project demonstrates:

- Docker containerization
- Multi-service architecture
- Container networking
- Docker Compose workflows
- Reverse proxy configuration
- Backend API development
- MongoDB integration
- DevOps fundamentals

---


---

# Author

Benjamin Hosseini
