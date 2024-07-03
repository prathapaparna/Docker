# Docker Network
- Docker networking enables communication between Docker containers
  ## types of network
  - bridge
  - host
  - none
  - overlay
 
- Bridge Network: Default network created automatically when Docker is installed. Containers on a bridge network can communicate with each other using IP addresses. Containers can be exposed to the outside world via port mappings.

- Host Network: Containers share the host's network stack, bypassing Docker's network abstraction. This can improve performance but may introduce port conflicts if multiple containers use the same ports.

- Overlay Network: Used for connecting multiple Docker daemons together across multiple hosts. Containers on an overlay network can communicate securely across hosts.

- Macvlan Network: Assigns a MAC address to each container's network interface, making containers appear as physical devices on the network. This allows containers to be directly accessible on the network.

- None Network: Removes networking from the container, meaning the container has no network interfaces. Useful in scenarios where networking is not needed.
```
docker network create --driver <driver-name> <network-name>
docker network create --driver bridge mynetwork
docker network ls
```
- create springboot and nginx with default container and create database with custom bridge network
- note: if we don't mention any network by default they get created in default network
  ```
  docker run --name springboot-mongodb  -p 8080:8080 -d techcloudifyme/springboot-mongodb:latest
  docker run --name mynginx  -d -p 8080:80 nginx
  docker run --name mymongodb  --network mynetwork -p 27017:27017 -d mongo
  ```
 - try to access each ip from one container to another
 - you can enables the connection from spring boot to nginx but not for mongodb
```
docker container inspect <container-name/id> ---> you can get ip container1
docker exec -it  <container-name/id> sh  ---> login to c2
ping ip(c1)
```



  
