# docker(1)

Start docker daemon

    docker -d

Start a container with an interactive shell

    docker run -ti <image-name> /bin/bash

Inspect a running container

    docker inspect \<container-name> (or \<container-id>)

Get the process ID for a container

    docker inspect --format \<pid> \<container-name-or-id>

List currently running containers

    docker ps

List all containers

    docker ps -a

List all images

    docker images
