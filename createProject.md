```Dockerfile
# Specify a base image
FROM node:alpine
# specify the working dir in container
WORKDIR /usr/app
COPY ./package.json ./
# Install some depenendencies
RUN npm install
COPY ./ ./

# Default command
CMD ["npm", "start"]
```
### Common Errors
1. npm not found: no npm in base image(alphone)
Solution: use base image:tag that contains npm\
2. package.json not found 
this happens because alphine image cannot refer to the place that contains pacakge.json\
** copy (path to folder to copy from machine) (palce to  copy stuff inside the container)
Solution: copy ./ ./ \
3. container port mapping
map ports on machine to container ports\
Solution: \
```Dockerfile
docker build -t imagename .
docker run -p 8080:8080 imagename 
```
### start a shell to enable debug
```Dockerfile
docker run -it imagename sh
```
### specify working directory
not best practice to copy files/folders to root directory of container\
because there may be some conflixts in folder names\
Solution: specify a working dir that's a subdirectory\
then when copy it will copy to working dir
### avoid uneccessary rebuilds
commands in dockerfile will be rebuild if changes were made that affect commands before\
COPY unchanged files before npm install to avoid rebuild
