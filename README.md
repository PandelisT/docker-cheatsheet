# Docker Commands Cheatsheet - WIP

Install Docker on Ubuntu: https://docs.docker.com/engine/install/ubuntu/ (works for WSL2 as well)

``` systemctl start docker``` - start docker service in Ubuntu

`docker pull <repository-name>`

Pull images from docker hub to your local machine (https://hub.docker.com/)

```docker images```

See all images on your local computer

```docker create --name <container-name> <image>```

```docker ps -as```

```docker start -a <container-name>```

```docker create -it --name <container-name> <image-name>```

The -t flag is for allocating a pseudo terminal and the -i flag is to keep STDIN open even when we are not connected to this container. Without i even if we were typing into the terminal our container would not receive those commands.

```docker start -ai <container-name>```

```docker start <container-name>``` - starts the container

```docker attach <container-name>``` - opens the terminal

```docker stop <container-name>``` - stop container

```docker create -it --name <container-name> <image-name>```

```docker start -ai <container-name>```

```docker commit <container-name> <dockerhub-name>/<repository-name>```

```docker push <image repo name>```

```docker build --tag <dockerhub-name>/<repository-name> .```

```docker run -it --name <container-name> <dockerhub-name>/<repository-name>```

```docker system prune```

Clean up any resources — images, containers, volumes, and networks — that are dangling (not associated with a container

```docker login``` (might need to use sudo)

Dockerfile (example with Python application:

```
FROM ubuntu:latest
RUN apt-get update
RUN apt-get install python3.8 -y
WORKDIR /home
COPY <name-of-app-directory> .
RUN apt-get install python3-pip -y
RUN pip3 install -r requirements.txt
CMD [ "python3.8", "main.py" ]
```

```docker build --tag <name-of-app-directory> .```

```docker run -it --rm <name-of-app-directory>```
