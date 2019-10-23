# Docker Components

## Q. What is Docker Client and Daemon ?

**Answer:** **Docker demon** is called **dockerd**  It can create and manage docker images. Containers, networks, etc while running at backgorund as a demon process , and we communicate with this demon process via **Docker Client** . In between this Docker client and Docker Demon resides a **Rest API** which carries out instructions from Docker client to Docker demon. 
 
<p align="center">
  <img src="https://github.com/arijitsdrush/Docker-Notes/raw/master/images/2_demon.png">
</p>

## Below is an example of how to see running process and communicate with them

1. First we need to find all running processes in Docker. we will run following `docker ps` command in our **Docker client** which will list all current running process. 


| CONTAINER ID  | IMAGE | 
| ------------- | ------------- |
| 8840645135fb  | wodby/nginx:1.17-5.6.5  |
| 248eee72e83e  | wodby/drupal-php:7.1-dev-4.13.5  |

2. Now using docker client we can login to any of this container's SSH and run command as we may like. `docker exec -it 24 /bin/bash` will give us access to SSH of wodby/drupal-php:7.1-dev-4.13.5 and now we can run any command in that container.

**Note :**
<ol type="I">
<li>When we run exec command we can communicate with container using first few hash , we used 24 instead of full 248eee72e83e </li>
<li> <b>-it</b>  means <b>"interactive"</b> and ,<b>"emulate " </b> . Means we want to run the container interactively rather than in the background and we also want to emulate a terminal. This is necessar when working with the container interactively
</ol> 

## Q. What is Docker Images ?
**Answer:** Docker images are read-only templates with instructions to create a docker container. Docker image can be pulled from a Docker hub and used as it is, or you can add additional instructions to the base image and create a new or modified docker image. You can create your own docker images also using a  **dockerfile**. Create a dockerfile with all the instructions to create a container and run it; it will create your custom docker image.

Docker image has a base layer which is read-only, and the top layer can be written. When you edit a dockerfile and rebuild it, only the modified part is rebuilt in the top layer.

**Some important commands regarding images**
`docker image ls -a`  List all docker images
`docker rmi wodby/rsyslog` will remove image **wodby/rsyslog**  from your system and will keep your system clean
 
## Q. What is Docker registries ?
**Answer:** **Docker registry** is a repository for Docker images. Using Docker registry, you can build and share images with your team. A registry can be public or private. Docker Inc provides a hosted registry service called Docker Hub. It allows you to upload and download images from a central location. If your repository is public, all your images can be accessed by other Docker hub users. You can also create a private registry in Docker Hub. Docker hub acts like git, where you can build your images locally on your laptop, commit it and then can be pushed to the Docker hub.

## Q. What is docker container ?

**Answer:** **Container** is the execution environment for Docker. Containers are created from images. It is a writable layer of the image. You can package your applications in a container, commit it and make it a golden image to build more containers from it. Two or more containers can be linked together to form tiered application architecture. Containers can be started, stopped, committed and terminated. If you terminate a container without committing it, all the changes made to the container will be lost.