## Commands

```bash
docker info ## give the information about containers and images
docker imgaes
docker pull <image:version> ## to pull imgaes from dockerhub or private registry
docker build -t <repodetails>/<appname>:version . ## -t is for tag, repo details are docker hub registry(public repo)
docker build -t <hostname/ip:port>/<appname>:version . ## for private repos ex: nexus/jfrog
docker login -u <username> -p
docker login -u <username> -p <password> <repourl> ## for private repos
docker history <imagename/id>  ## it will display layers of an image
docker rmi <imagename/id> ## to remove images
docker rmi $(docker images -q) ## delete multiple images
docker rmi -f <imagename/id> ## delete image forcefully if it in use 
docker save -o <filename.tar> <imagename> ## create a tar file from image
docker load -i <filename.tar>  ## create an image from tar file

docker run --name <contaner-name> -p <hostport>:<conatinerport> <image-name> ## -d id for detach mode
                                                                                 -p is for port forwarding from host to container

docker ps
docker ps -a
docker stop <conatiner-name/id>
docker start <conatiner-name/id>
docker restart <conatiner-name/id>
docker pause <conatiner-name/id>
docker unpause <conatiner-name/id>
docker rm <conatiner-name/id>
docker rm -f <conatiner-name/id> ## for removing running containers
docker rm -f $(docker ps -aq)   ## to remove all stopped and running containers
docker logs <conatiner-name/id> ## to access container logs
docker top <conatiner-name/id> display process id which is running inside container

docker exec -it <container-name/id>  <commands>
docker inspect <conatner/imageid>  ## display all info about containers or images

docker cp <file/name/with/path> <containername/id>:<path/of/container> ## copy files from system to container
docker cp <containername/id>:<path/of/container> <file/name/with/path>  ## copy files from container to system
```
