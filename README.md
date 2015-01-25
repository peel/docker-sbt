#Idea
The idea for the image is to create a fast-feedback container running test/'ci' env for scala/sbt apps. 
The base image is Busybox w/ OpenJDK (Zulu VM).

#Tags

#Usage

```
docker run -it --rm peel/sbt sbt ~re-start
```
