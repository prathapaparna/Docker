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

