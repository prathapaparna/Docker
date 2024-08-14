# create containers without volume backup
# Pre-requisites:
  - Install Java
  - Install Maven
  - Install Docker
  - Install Docker-compose
 
# Clone Springboot-mongodb application:
    git clone https://github.com/prathapaparna/docker.git
    cd docker/Docker-compose/springboot-mongodb
# Build artifact
    mvn clean install -DskipTests=true
 
# Build Docker Image
    docker build -t techcloudifyme/springboot-mongodb:latest .
# Docker login
    docker login -u techcloudifyme -p
# Push Docker image to Dockerhub
    docker push techcloudifyme/springboot-mongodb:latest
    
# Deploy application with run command:
    docker run --name mymongodb -p 27017:27017 -d mongo
    docker run --name springboot-mongodb --link mymongodb:mymongodb -p 8080:8080 -d techcloudifyme/springboot-mongodb:latest
# Use postman app and Add Employee data
Check API: /addEmployee

    http://<ip-address>:8080/addEmployee
  
In postman app keep Post method and give Json data by selecting Body --> raw (Json format)

    {"id": "1001", "name": "techcloudifyme", "departement": "Engineer"}
    
Check API:- /findAllEmployees

Goto Web UI and check below link

    http://<ip-address>:8080/findAllEmployees
  **Note** delete and recreate container and check data is exist or not  
# create the same container with volume backup
```
docker volume create mongodb_backup
docker run --name mymongodb -v mongodb_backup:/data/db -p 27017:27017 -d mongo
docker run --name springboot-mongodb --link mymongodb:mymongodb -p 8080:8080 -d techcloudifyme/springboot-mongodb:latest
```
# Use postman app and Add Employee data
Check API: /addEmployee

    http://<ip-address>:8080/addEmployee
  
In postman app keep Post method and give Json data by selecting Body --> raw (Json format)

    {"id": "1001", "name": "techcloudifyme", "departement": "Engineer"}
    
Check API:- /findAllEmployees

Goto Web UI and check below link

    http://<ip-address>:8080/findAllEmployees

## now delete and recreate same containers and check the employees data
```
docker run --name mymongodb -v mongodb_backup:/data/db -p 27017:27017 -d mongo
docker run --name springboot-mongodb --link mymongodb:mymongodb -p 8080:8080 -d techcloudifyme/springboot-mongodb:latest
```

