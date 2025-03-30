# Docker Full Course

## Table of Contents
1. [Introduction to Docker](#introduction-to-docker)
2. [Docker Commands](#docker-commands)
3. [Building Custom Images](#building-custom-images)
4. [Docker Compose](#docker-compose)
5. [Multi-Stage Build](#multi-stage-build)

---

## Introduction to Docker
Docker is a containerization tool that allows developers to package applications and their dependencies into portable containers.

### Install Docker
```sh
# Install Docker on Ubuntu
sudo apt update
sudo apt install docker.io -y

# Verify installation
docker --version
```

---

## Docker Commands

### Basic Commands
```sh
# Check Docker version
docker --version

# List running containers
docker ps

# List all containers (including stopped ones)
docker ps -a

# Start a container
docker start <container_id>

# Stop a container
docker stop <container_id>

# Remove a container
docker rm <container_id>

# Remove an image
docker rmi <image_id>
```

### Build and Run a Container
```sh
# Build a Docker image
docker build -t myapp .

# Run a container from an image
docker run -d -p 8080:80 myapp
```

---

## Building Custom Images

### Dockerfile Example
Create a `Dockerfile`:
```dockerfile
# Use official Node.js image as base
FROM node:18

# Set working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY package.json .
RUN npm install

# Copy application source code
COPY . .

# Expose port
EXPOSE 3000

# Command to run the app
CMD ["node", "server.js"]
```

Build and run:
```sh
docker build -t mynodeapp .
docker run -d -p 3000:3000 mynodeapp
```

---

## Docker Compose

Create a `docker-compose.yml` file:
```yaml
version: '3.8'

services:
  web:
    image: nginx:latest
    ports:
      - "8080:80"
    volumes:
      - ./html:/usr/share/nginx/html
```

Run with:
```sh
docker-compose up -d
```

---

## Multi-Stage Build

### Multi-Stage Dockerfile Example
```dockerfile
# Stage 1: Build the application
FROM node:18 as builder
WORKDIR /app
COPY package.json .
RUN npm install
COPY . .
RUN npm run build

# Stage 2: Serve the application
FROM nginx:latest
COPY --from=builder /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

Build and run:
```sh
docker build -t myapp-multistage .
docker run -d -p 80:80 myapp-multistage
