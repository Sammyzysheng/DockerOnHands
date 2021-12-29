```Dockerfile
# Specify a base image
FROM node:alpine

WORKDIR /usr/app

# Install some depenendencies
RUN npm install

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
