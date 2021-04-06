## Start and run a container by an image from remote registry
```DockerFile
Docker run --name containerName imageName:tag 
Docker run -i -t imageName:tag 
//Run in foreground
ls
//Exit
exit
//list files under image repository 
Docker run -i -t imageName:tag ls /
//Or
Docker run -d imageName:tag commands
//Run in background to enable commands for other usage
Docker ps
//Show all images running
Docker ps -a
//Show all images 
Docker inspect containerID
//show detailed container info
```
## Docker images
```DockerFile
docker history imageName:tag
//show the layers of an image
``` 
### Build a docker image
### Step 1: spin up a container from base image 
```DockerFile
docker run --name containerName -d imageName:tag
ls
```
### Step 2: install git package in the container
```DockerFile
apt-get update && apt-get install git
```
### Step 3 :commit changes made in container
```DockerFile
docker commit containerName imageName:tag
//save changes made to docker image
```
