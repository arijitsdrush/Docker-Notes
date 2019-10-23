# Docker Components

## Q. What is Docker Client and Daemon ?

**Answer:** **Docker demon** is called **dockerd**  It can create and manage docker images. Containers, networks, etc while running at backgorund as a demon process , and we communicate with this demon process via **Docker Client** . In between this Docker client and Docker Demon resides a **Rest API** which carries out instructions from Docker client to Docker demon. 
![]([https://github.com/arijitsdrush/Docker-Notes/blob/master/images/2_demon.jpg])