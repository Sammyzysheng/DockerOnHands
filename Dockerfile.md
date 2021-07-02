### Build through a dockerfile
```
docker build . # build in current directory
docker built -f /pathToDockerfile . # build from dockerfile in your file system
docker build  -t /pathToSaveNewImage . # use -t to tage a place to save new iamge once built

```
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
add "\" at end of line to combine two lines into one instruction
