## Start and run a container by an image from remote registry
```DockerFile
Docker run imageName:tag 
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
```
