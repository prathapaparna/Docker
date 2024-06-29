## types of volumes
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

## example
### without volume
```
docker run --name mysql-container -e MYSQL_ROOT_PASSWORD=Admin#123 -p 3306:3306 mysql:latest
docker exec -it <container-id> /bin/bash
mysql -u root -p
show databases;
use mysql;
CREATE TABLE employee_data (
    eno VARCHAR(40),
    ename VARCHAR(50),
    esal VARCHAR(40)
);
INSERT INTO employee_data (eno, ename, esal)
VALUES (101, "aparna", 5000);
select * from employee_data;
```
after creating mysql container, if its delete with anyreason your data also will lost

```
docker run --name mysql-container -v mysql_backup:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=Admin#123 -p 3306:3306 -d mysql:latest
```
if you create a contaner with volume you don't loose any date even if container deleted or recreated

