<img src="../../../img/logo.png" alt="Chmurowisko logo" width="200" align="right">
<br><br>
<br><br>
<br><br>

# Working with Dockerfiles

## Lab Overeview

#### In this lab you will learn how to work with Dockerfiles and how to build your own docker images and containers

## Task 1: Create container that will run apache2 server on ubuntu

1. Create new file and name it "Dockerfile"
1. Copy content of files/Dockerfile and past it into your Dockerfile
1. Run: `docker build -t myapache2 .`. Wait for the build to finish.
1. Run `docker images` and verify that your image is on a list.
1. Execute `docker run -p 8081:80 -d myapache2`
1. Open web browser and verify that your container is running `http://localhost:8081`
1. Stop the container

## Task 2: Run apache2 server with your custom page added

1. Modify existing Dockerfile so it executes following command during build: `mkdir /var/www/html/mypage`
1. Add this command to Dockerfile (after creating "mypage" directory): `COPY index.html /var/www/html/mypage`
1. Build image: `docker build -t myapache2-mypage .`
1. Run container: `docker run -p 8081:80 -d myapache2-mypage`
1. Check your web page: `http://localhost:8081/mypage/`
