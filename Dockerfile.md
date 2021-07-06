### Build through a dockerfile
```
docker build . # build in current directory
docker built -f /pathToDockerfile . # build from dockerfile in your file system
docker build  -t /pathToSaveNewImage . # use -t to tage a place to save new iamge once built

```
### Sample Docker File
```
# Alpine Linux is a small, security-oriented, lightweight Linux distribution based on the musl libc library and BusyBox utilities platform instead of GNU
FROM alpine

# Step 2: Download and install dependency

# apk : apache package manager in Alphine lib to help download pacakge

RUN apk add --update redis

# Step 3: Tell the image what to do when it starts as container

CMD ["redis-server"]
```
### Build Process
Each line of Dockerfile will get image from last instruction -> create a container of the image -> run commands in the conainer -> take snapshot of the container , save as cache in FS -> delete temporary container -> get image ready for next instruction

### Build Format

#### comment
```
# comment
INSTRUCTION arguments
```

#### Case
dockerfile is not case sensitive but default Upper case instruction
#### WhiteSpaces
```
# WhiteSpaces: Instructions and comments are not affected by whicte spaces, but arguments whitespaces do matter
RUN echo "hello\
     world"
```
#### Escape Character
```
# set escape character from "\" to "`" on windows
# escape= `

```
#### new line
add  \ at end of line to combine two lines into one instruction
