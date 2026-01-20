# docker(1)

    ds                                                         # list docker disk usage
    docker system prune -f                                     # remove unused containers, volumes, networks and images
    docker inspect CONTAINER                                   # Inspect a running container

Run Container

    d                                                          # list docker container
    docker run -it IMAGE /bin/bash                             # Start a container with an interactive shell
    docker run -it -w /app IMAGE /bin/bash                     # Start a container with an interactive shell in new dir `/app`
    docker run -it -v "$(pwd)":/app IMAGE /bin/bash            # Start a container with an interactive shell and mount PWD
    docker run --rm IMAGE env                                  # show environment of a container

Create and run a Docker Image from a _Dockerfile_

    di                                                         # list docker images
    docker build -t IMAGE .
    docker build --no-cache -t IMAGE .                         # build an image from a Dockerfile without using the cache
    docker run --rm --name CONTAINER -d -p 8080:8080 IMAGE
    docker logs CONTAINER
    docker exec -it CONTAINER /bin/bash 

Push Image to Docker-Hub (https://hub.docker.com/u/thomd)

    docker login
    docker tag IMAGE thomd/IMAGE:TAG
    docker push thomd/IMAGE:TAG

Docker Volumes

    dv                                                         # list docker volumes

Alpine Image

    docker run -it alpine:latest /bin/sh
    > apk update
    > apk add nginx
