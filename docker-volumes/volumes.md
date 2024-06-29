##types of volumes
local volume:   backup is taken in host system
network volume:   backup is taken outside of host ex: EFS
```
docker volume --help
docker volume create <volume-name> it will create a directory in /var/lib/docker/vloumes in host machine
docker run --name mysql-container -v mysql-backup:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=Admin#123 -p 3306:3306 -d mysql:latest
docker volume ls
docker volume inspect <volume-name>

```
They provide a way to store data outside of the container's filesystem, ensuring data persists even when the container is deleted.
```
docker run -d --name my_container -v my_volume:/data my_image
docker run -d --name my_container --mount source=my_volume,target=/data my_image

```
In this example, my_volume is mounted to the /data directory inside the container.
