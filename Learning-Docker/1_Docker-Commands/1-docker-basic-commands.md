# 1_Docker-Basic-Commands

```json
#run and or downloads an image
docker run IMAGENAME

#download image and don't run it
docker pull nginx

#list containers running
docker ps 

#list all containers running or stopped
docker ps -a

#stop a container
docker stop IMAGENAME OR CONTAINER ID

#remove a container
docker rm IMAGENAME OR CONTAINER ID

#list the docker images
docker images

#remove images
docker rmi nginx 

#execute commands on a container
docker exec IMAGENAME OR CONTAINER ID cat /etc/hosts

# run on detach mode
docker run -d nginx

#log in to container
docker run -it nginx bash

#name a container
sudo docker run -d --name discourse_app local_discourse/app


#rename a container
sudo docker rename discourse_app disc_app
```