# Docker-compose
-  Docker Compose is a tool for defining and running multi-container Docker applications. It uses a YAML file (docker-compose.yml) to configure the application's services and their dependencies, allowing you to manage multiple containers as a single application.
## install docker and docker compose
```
yum install docker -y
systemctl start docker
curl -L https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
docker-compose version
```

Key Concepts of Docker Compose
- Service: A service defines a container that you want to run. Each service runs one image and can be scaled to run multiple instances if necessary.
- Network: Networks allow services to communicate with each other. By default, Docker Compose creates a network for the services defined in a single Compose file.
- Volume: Volumes are used to persist data generated and used by Docker containers.
Basic Structure of a docker-compose.yml File
A docker-compose.yml file typically consists of the following sections:

- version: Specifies the version of the Compose file format.
- services: Defines the list of services (containers) that make up your application.
- networks: (Optional) Defines custom networks for your services.
- volumes: (Optional) Defines named volumes for persistent data storage.
