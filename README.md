# Docker Microservices Example

This project demonstrates 3 simple microservices containerized with Docker and orchestrated with Docker Compose.

## Microservices

1. **hi-service** (Port 5001)
   - Endpoint: `GET /` → Returns "Hi there! 👋"
   - Health check: `GET /health` → Returns status

2. **greeting-service** (Port 5002)
   - Endpoint: `GET /` → Returns "Hello, Welcome! 🎉"
   - Health check: `GET /health` → Returns status

3. **bye-service** (Port 5003)
   - Endpoint: `GET /` → Returns "Goodbye! 👋"
   - Health check: `GET /health` → Returns status

## Prerequisites

- Docker installed and running
- Docker Compose installed

## Running with Docker Compose

Navigate to the project root and run:

```bash
docker-compose up --build
```

This will:
- Build Docker images for each service
- Start all 3 containers
- Map ports to your localhost

## Testing the Services

Once running, test each service:

```bash
# Hi Service
curl http://localhost:5001/

# Greeting Service
curl http://localhost:5002/

# Bye Service
curl http://localhost:5003/

# Health checks
curl http://localhost:5001/health
curl http://localhost:5002/health
curl http://localhost:5003/health
```

## Stopping the Services

```bash
docker-compose down
```

## Building Individual Services

If you want to build or run individual services:

```bash
# Build hi-service image
docker build -t hi-service ./hi-service

# Run hi-service container
docker run -p 5001:5001 hi-service
```

## Learning Resources

- **Dockerfile**: Each service has a Dockerfile that defines how to containerize the app
- **docker-compose.yml**: The main orchestration file that manages all services
- **Key concepts**: 
  - Image building from Dockerfile
  - Port mapping
  - Container networking
  - Service orchestration with Compose
