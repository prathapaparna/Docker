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
