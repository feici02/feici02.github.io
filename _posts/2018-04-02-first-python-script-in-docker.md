---
layout: post
title:  "How to run your first Python script in Docker?"
tags: docker
---

Please follow steps below.

### 1. Pull the `python` docker image from Docker hub
```
$ docker pull python
```
It will download the offical `python` docker image from Docker hub, which will be used as the base image to build your own image. And you can run `docker images` to check after the download is finished.

### 2. Test this image by checking the Python version (optional)
```
$ docker run --rm python python --version
Python 3.6.5
```
With the `--rm` option, the containter will be removed automatically after it exits.

### 3. Prepare your Python script
```
$ mkdir hello-docker
$ cd hello-docker

$ cat hello.py
import sys

name=sys.argv[1]
print(f"Hello, {name}!")
```

### 4. Edit your Dockerfile
```
$ cat Dockerfile
FROM python
RUN mkdir /app
COPY ./hello.py /app
ENTRYPOINT ["python", "/app/hello.py"]
CMD ["world"]
```
Notes:
- An "ENTRYPOINT" allows you to configure a container that will run as an executable.
- "CMD" should be used as a way of defining default arguments for an "ENTRYPOINT" command.

### 5. Build the image
```
$ docker build -t hello-docker .
```

### 6. Run your first Python script in Docker
```
$ docker run --rm hello-docker
Hello, world!
$ docker run --rm hello-docker docker
Hello, docker!
```
