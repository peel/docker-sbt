#Idea
The idea for the image is to create a fast-feedback container running test/'ci' env for scala/sbt apps. 
The base image is Busybox w/ OpenJDK (Zulu VM).
By default the image runs the 

#Tags
The repository contains several tags for various versions of SBT. Choose the correct version to utilize Docker Union FS layer caching of sbt libraries.
Pattern for tagging versions:

- 0.13, 0.13.7, latest - SBT 0.13.7
- 0.12, 0.12.x  - SBT 0.12.x (NOT AVAILABLE FOR NOW)

Older versions might be available under respectable tags ie. 0.13.5

#Usage
As template:

```
FROM peelsky/sbt:0.13.7
MAINTAINER Piotr Limanowski <plimanowski@gmail.com>

EXPOSE 9000
CMD sbt ~re-start
```

From command line:
```
docker run --rm -p 9000:9000 -v /Users/peel/wrk/spray-wip:/app:rw -it peelsky/sbt:0.13.7
```
