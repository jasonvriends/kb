# Podman

Containers provide an isolated environment for running applications, allowing developers to package their software in a consistent manner and deploy it across different computing environments, such as development, testing, staging, and production. Containers also enable faster and more efficient deployment of applications, as they can be easily moved between different hosts or cloud platforms without the need for complex setup and configuration.

Podman is an open-source container engine that allows you to manage and run containers on Linux without requiring a daemon. It provides a command-line interface and API for building, running, and managing containers and pods. Podman is a lightweight alternative to Docker, which doesn't require a separate daemon or root privileges.

These sample Compose files can help you quickly establish the necessary infrastructure for your development projects.

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