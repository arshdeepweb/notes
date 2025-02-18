# Docker CLI Cheat Sheet

## Build and Manage Docker Images

- **Build an Image from a Dockerfile:**
  ```bash
  docker build -t <image_name> .
  ```

- **Build an Image from a Dockerfile without the cache:**
  ```bash
  docker build -t <image_name> . --no-cache
  ```

- **List local images:**
  ```bash
  docker images
  ```

- **Delete an Image:**
  ```bash
  docker rmi <image_name>
  ```

- **Remove all unused images:**
  ```bash
  docker image prune
  ```

## Docker Hub Operations

- **Login into Docker:**
  ```bash
  docker login -u <username>
  ```

- **Publish an image to Docker Hub:**
  ```bash
  docker push <username>/<image_name>
  ```

- **Search Hub for an image:**
  ```bash
  docker search <image_name>
  ```

- **Pull an image from Docker Hub:**
  ```bash
  docker pull <image_name>
  ```

## Create and Manage Containers

- **Create and run a container from an image with a custom name:**
  ```bash
  docker run --name <container_name> <image_name>
  ```

- **Run a container and publish its port(s) to the host:**
  ```bash
  docker run -p <host_port>:<container_port> <image_name>
  ```

- **Run a container in the background:**
  ```bash
  docker run -d <image_name>
  ```

- **Start or stop an existing container:**
  ```bash
  docker start|stop <container_name>
  ```

- **Remove a stopped container:**
  ```bash
  docker rm <container_name>
  ```

- **Open a shell inside a running container:**
  ```bash
  docker exec -it <container_name> sh
  ```

## Monitoring and Debugging

- **Fetch and follow the logs of a container:**
  ```bash
  docker logs -f <container_name>
  ```

- **Inspect a running container:**
  ```bash
  docker inspect <container_name>
  ```

- **List currently running containers:**
  ```bash
  docker ps
  ```

- **List all Docker containers (running and stopped):**
  ```bash
  docker ps --all
  ```

- **View resource usage stats:**
  ```bash
  docker container stats
  ```

## General Commands

- **Start the Docker daemon:**
  ```bash
  docker -d
  ```

- **Get help with Docker (works with all subcommands):**
  ```bash
  docker --help
  ```

- **Display system-wide information:**
  ```bash
  docker info
  ```

## Additional Resources

- **Docker Desktop Installation:**
  Docker Desktop is available for Mac, Linux, and Windows. Learn more at: [Docker Desktop](https://docs.docker.com/desktop)

- **Example Projects Using Docker:**
  Explore examples at: [Awesome Compose](https://github.com/docker/awesome-compose)

- **Official Docker Documentation:**
  Visit: [Docker Documentation](https://docs.docker.com)

- **Docker Hub:**
  Find and share container images: [Docker Hub](https://hub.docker.com)
