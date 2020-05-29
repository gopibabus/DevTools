# 🔥Docker

<img src="./assets/images/docker.png" alt="docker" width="400">

### ✳What is a Docker?

?> **Docker** provides the ability to package and run an application in a loosely isolated environment called a **container**. The isolation and security allow you to run many containers simultaneously on a given host.

### ✳What is a Container?

?> A standardized unit of software.

[🌐 Container Documentation](https://www.docker.com/resources/what-container)

### ✳How to create sample docker file(Dockerfile)?

```yaml
# Base Docker Image
FROM node:lts

# Command that should execute after creating of complete container
CMD ["/bin/bash"]
```

### ✳How to build a container?

```bash
docker build -t "smart-brain-api-node" .
```

### ✳How to run a container?

```bash
docker run -it smart-brain-api-node
```

### ✳How to run container in background?

```bash
docker run -it -d smart-brain-api-node
```

### ✳How can I view running containers?

```bash
docker ps
```

### ✳How can I enter into container running in background?

```bash
docker exec -it [container-id] bash
```

### ✳How to stop a container?

```bash
docker stop [container-id]
```

### ✳How can we implement port forwarding on the container?

```bash
docker run -it -p 3000:3000 smart-brain-api-node
```

### ✳Advanced version of Dockerfile

```bash
# Base Docker Image
FROM node:lts
# Creating work directory
WORKDIR /usr/src/smart-brain-api
# Copying files form host machine to work directory in the container
COPY ./ ./
# One of the steps in building an image
RUN npm install
# Command that should execute after creating of complete container
CMD ["/bin/bash"]
```

How to build containers using docker-compose?

```yaml
version: '3.8'
services:
  smart-brain-api:
    container_name: backend
    # image: node:lts
    # build command  uses existing Dockerfile
    build: ./
    command: npm start
    working_dir: /usr/src/smart-brain-api
    ports:
      - '3000:3000'
```

### ✳How to build containers using docker-compose?

```bash
docker-compose build
```

### ✳How to run a container using docker-compose?

```bash
docker-compose run [service name in docker-compose.yml]
```

```bash
docker-compose exec [service name in docker-compose.yml] bash
```

### ✳How to shutdown all containers?

```bash
docker-compose down
```

### ✳How to switch on containers?

```bash
docker-compose up
# Running in background
docker-compose up -d
# Build and run container
docker-compose up --build
```

### ✳Docker compose file with multiple services

```yaml
version: '3.8'
services:
  # Backend API
  smart-brain-api:
    container_name: backend
    # build command  uses existing Dockerfiles
    build: ./
    command: npm start
    working_dir: /usr/src/smart-brain-api
    environment:
      POSTGRES_USER: sally
      POSTGRES_PASSWORD: secret
      POSTGRES_DB: smart-brain
      POSTGRES_HOST: postgres
    links:
      - postgres
    ports:
      - '3000:3000'
    volumes:
      - ./:/usr/src/smart-brain-api

  # Database
  postgres:
    environment:
      POSTGRES_USER: sally
      POSTGRES_PASSWORD: secret
      POSTGRES_DB: smart-brain
      POSTGRES_HOST: postgres
    image: postgres
    ports:
      - '5432:5432'
```

[smart-brain-boost-api-dockerized](https://github.com/aneagoie/smart-brain-boost-api-dockerized)
