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
