# docker

https://devopscube.com/docker-containers-as-build-slaves-jenkins/


docker images

docker pull image:version

docker run --name <container-name> hostport:containerport image:version
  
docker ps 

docker ps -a
  
  docker rm <container-name/iD>
  
  docker rmi <imagename/id>
  
  docker exec -it <conatinername/id>  /bin/bash
  
  docker cp <filepath> <container-ID>:<folder-path> ---linux to container
  
  docker cp <container-ID>:<folder-path> <filepath> --- container to linux
  
  
  
