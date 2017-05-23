# What is this docker?

This docker is learning AI group's docker image file.


# How to build the Dockerfile

You can build docker container the command.

```
$ git clone git@github.com:showmurai/aistudy.git
$ cd aistudy/docker
$ docker build -f Dockerfile -t aistudy .
$ docer run -it aistudy /bin/bash
```

Or you can download from Docker Hub like this.

```
$ docker pull showmurai/aistudy
$ docker run -it aistudy /bin/bash
```
