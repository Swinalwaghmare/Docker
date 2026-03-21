# E-Commerce Application

This is a full-stack e-commerce web application with an Angular frontend and a Spring Boot backend, utilizing PostgreSQL as the database. It includes Docker configuration for easy setup.

## Project Structure

- `frontend/`: Angular application
- `backend/`: Spring Boot Java application
- `docker-compose.yml`: Local Docker environment (PostgreSQL + Frontend + Backend)

## Getting Started

### Prerequisites
- Node.js (for frontend development)
- Java 17+ and Maven (for backend development)
- Docker & Docker Compose (for running the full stack)

### Using Docker Compose (Recommended)

To run the entire stack locally:
```bash
docker-compose up --build
```
- The frontend will be available at `http://localhost:80`
- The backend API will be available at `http://localhost:8080`
- Database connects automatically.

### Running Backend Locally (Without Docker)

You need a running PostgreSQL instance:
1. Update `backend/src/main/resources/application.yml` with your local DB credentials.
2. Build and run:
```bash
cd backend
mvn clean install
mvn spring-boot:run
```

### Running Frontend Locally (Without Docker)

```bash
cd frontend
npm install
npm start
```
Frontend runs on `http://localhost:4200`

## Architecture
See `ecommerce_architecture.md` (or the architecture artifact) for full details on the schema and deployment.
