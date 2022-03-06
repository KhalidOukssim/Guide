#                                             DOCKER

## Problem!!!

<p align="center">
  <img src="Images/Docker Problem.JPG">
  <br/>
</p>

Developers used to run the code on their system, it would perfectly . But the same code did not run on the operations team system.

we need an entity  which can "contain" all the software  dependencies,and can be ported on to other computers as plug and play package. 

## 2 - What is Docker

it is a computer program that performs operating-system-level virtualization, also known as "containerization".

<p align="center">
  <img src="Images/Docker architecture.JPG">
  <br/>
</p>

Application **containerization** is an OS-level virtualization method used to deploy and run distributed applications without launching an entire virtual machine (VM) for each app

## 3-Common Docker Operations

```bash
docker --version #vesion
docker pull <image-name> #download the docker image 
docker images #show image that we downloaded
```

## 4-DockerFile

```dockerfile
FROM node:version

WORKDIR /usr/src/smart-brain #work directory path 
COPY ./ ./ #copy all the work dir to our container
RUN yarn install 
CMD ["/bin/bash"]
```

```bash
docker build -t name #after creating dockerFile
docker run -it name
docker ps #show all our containers details
docker exec -it container_id bash #access to docker
docker stop container_id

```

 when all the project is in our container,it can not run in a port's machine if we didn't specify it to the docker

```bash
docker -it -p 3000:3000 name_container #Machine_port:container_port
```

the container contain our project!! yaaaay...but what about our DB;docker has another solution called: **docker Compose**

## 5-	Docker-compose.yaml

```yaml
version: '3.6' #you can choose the last version
services:
  smart-brain-api:
    container_name: backend
    image: node:8.11.1
    build: ./ 
    command: npm start
    working_dir: /app
    environnement:
      POSTGRES_USER: sally
      POSTGRES_PASSWOR: secret
      POSTGRES_DB: smart-brain-docker
      POSTGRES_DB: postgres
      #instead of all thos 4 lines
      #POSTGRES_URI: postgres://sally:secret@localhost:5432/smart-brain-docker
    links:
      -  postgres
    ports: 
      -"3000:3000"
    volumes:
      - ./:/usr/src/smart-brain #this fix rebuild probleme:it is a way to have connection with our container
  
  postgress:
    environnement:
      POSTGRES_URI: postgres://sally:secret@localhost:5432/smart-brain-docker 
    image: postgres #change image to build if you create a dockerfile for Postgres
    ports:
      - "5432:5432"
```

```bash
docker-compose build #You must execute this commande every time you change smtg
docker-compose run service_name  
docker-compose down
docker-compose up --build
```

