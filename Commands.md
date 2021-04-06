## Start and run a container by an image from remote registry
```DockerFile
docker run --name containerName imageName:tag 
docker run -i -t imageName:tag 
//Run in foreground
ls
//Exit
exit
//list files under image repository 
docker run -i -t imageName:tag ls /
//Or
docker run -d imageName:tag commands
//Run in background to enable commands for other usage

```
## Docker images
```DockerFile
docker history imageName:tag
//show the layers of an image
docker ps
//Show all images running
docker ps -a
//Show all images 
docker inspect containerID
//show detailed container info
``` 
### Build a docker image
### Step 1: spin up a container from base image 
```DockerFile
docker run --name containerName -d newImageName:newTag
ls
```
### Step 2: install git package in the container
```DockerFile
apt-get update && apt-get install git
```
### Step 3 :commit changes made in container
```DockerFile
docker commit containerID(docker ps -a ) newImageName:newTag
//save changes made to docker image
```
