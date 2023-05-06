Containers provide an isolated environment for running applications, allowing developers to package their software in a consistent manner and deploy it across different computing environments, such as development, testing, staging, and production. Containers also enable faster and more efficient deployment of applications, as they can be easily moved between different hosts or cloud platforms without the need for complex setup and configuration.

Docker and Podman are both popular containerization tools that enable developers to create, manage, and deploy containerized applications. While Docker has been the de facto standard for containerization, Podman offers some distinct advantages. Podman's architecture does not require a separate daemon, which reduces complexity and potential security vulnerabilities. Additionally, Podman's security-focused design, including running containers as regular user accounts by default and built-in support for SELinux, makes it an attractive option for security-conscious organizations. Furthermore, Podman is compatible with Docker, meaning that it can run Docker container images and use Docker Compose files. Given these advantages, my preference would be to use Podman over Docker for containerization tasks.

These sample Compose files can help you quickly establish the necessary infrastructure for your development projects, whether you're using Docker or Podman.

## Commands

- Delete all containers
``` bash
podman rm -f $(podman ps -a -q)
```

- Delete all images
``` bash
podman rmi -f $(podman images -q)
```

- Delete all volumes
``` bash
podman volume rm $(podman volume ls -q)
```

- Creates and starts containers for all services defined in a Compose file 
``` bash
podman-compose up -d
```

- Stops all containers managed by the Compose file.
``` bash
podman-compose stop
```

## MongoDB
``` yaml title="podman-compose.yml"
version: "3.8"

services:
  mongodb:
    image: mongo:latest
    container_name: mongodb
    environment:
      MONGO_INITDB_ROOT_USERNAME: mongodb
      MONGO_INITDB_ROOT_PASSWORD: mongodb
    ports:
      - "27017:27017"
    volumes:
      - mongodb_data:/data/db

volumes:
  mongodb_data:
```

## PostgreSQL

``` yaml title="podman-compose.yml"
version: "3.8"

services:
  db:
    image: postgres:latest
    environment:
      POSTGRES_USER: postgresql
      POSTGRES_PASSWORD: postgresql
      POSTGRES_DB: postgresql
    ports:
      - "5432:5432"
    volumes:
      - pgdata:/var/lib/postgresql/data

volumes:
  pgdata:
```