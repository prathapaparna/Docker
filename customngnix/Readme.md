# Create custom ngnix image

## Step-01: Introduction
- create ec2 server
- install docker
   
```
yum-config-manager --enable rhui-REGION-rhel-server-extras
yum -y install docker 
systemctl start docker
systemctl enable docker
docker version
```
## Step-02: Create required files
clone the git repo
```
git clone https://github.com/prathapaparna/docker.git
cd customngnix
```
## Step-03: Create docker image using Dockerfile

```
docker build -t nginx:1.0 .
```
## Step-04: Create docker container using docker image
```
docker run -d -p 9090:80 --name webserver nginx:1.0 
```
## step-05: Add port number in security groups

- Goto ec2 server --> security groups --> add inbound rules --> add port number 9090

## step-06: browse the application

<img width="396" alt="image" src="https://user-images.githubusercontent.com/99127429/209327173-5b96259b-57eb-4b44-b1d1-f0b462e12585.png">

## Step-07: Push docker image into dokcer hub

```
docker login -u aparnaprathap
```
enter the password
<img width="385" alt="image" src="https://user-images.githubusercontent.com/99127429/209327481-c40a69cd-8258-480e-a60f-25b95b9b4e12.png">
<img width="476" alt="image" src="https://user-images.githubusercontent.com/99127429/209327555-d7b6b4e7-f2c1-4e2d-813e-f3a3f210d2a9.png">

### Create a tag and push

```
docker tag nginx:1.0 aparnaprathap/nginx:1.0
docker push aparnaprathap/nginx:1.0
```




