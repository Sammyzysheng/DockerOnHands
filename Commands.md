## Start and run a container by an image from remote registry
Container is an instance of image with startup commands
![image](https://user-images.githubusercontent.com/49420214/124324032-44055980-db50-11eb-8a62-32637d4d9c1d.png)


```cmd
docker create --name containerName imageName:tag  
docker run -a containerID 
# docker create + docker start = docker run 
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
```cmd
docker history imageName:tag
//show the layers of an image
docker ps
//Show all images running
docker ps -a
//Show all images 
docker inspect containerID
//show detailed container info
``` 
## Build a docker image using Dockerfile

### Step 1: Writing a local dockerfile
```DockerFile
FROM originalimage:tag
RUN apt-get update && apt-get install -y git
//using debian/ubuntu tools
CMD ["echo","Hello World"]
//Copy files from a location to another
COPY filelocation movedToLocation
```
### Step 2:Building an image
```cmd
//Building an image using local Dockerfile
docker build -t newImagename .
```
### Step 3 :start container services
```cmd
docker run newImageID 
```
## Build a docker image using docker commit command
### Step 1: spin up a container from base image 
```cmd
docker run --name containerName -it newImageName:newTag
ls
```
### Step 2: install git package in the container
```DockerFile
 apt-get update && apt-get install -y git
```
### Step 3 :commit changes made in container
```DockerFile
docker commit containerID(docker ps -a ) newImageName:newTag
//save changes made to docker image
```
## Push image to docker hub
```cmd
docker tag imageID nameofImage:tagofImage
docker login --username=username
password:
docker push imageName:tag(docker images)
```
## Other commands
#### Restart a stopped container
```
docker start -a containerID
```
#### Delete all stopped container
```
docker system prune
```
#### Stop Kill a running container
```
docker stop containerID
docker kill containerID
```
### Multi-command Containers
start up a second program\
eg. run redis using docker, run redis cli using the same container
```
docker run redis
# run redis-cli in redis-server container
docker execuetev -it containerID command
```
### Getting a command prompt in c caontainer
go inside command prommpt
 ```
 docker execuetev -it containerID sh
 ```
 
