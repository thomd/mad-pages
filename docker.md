# docker(1)

    docker system df                              # docker disk usage
    docker system prune -f                        # remove unused containers, volumes, networks and images

Container

    docker run -it \<image> /bin/bash              # Start a container with an interactive shell
    docker run --rm \<image> env                   # show environment of a container
    docker inspect \<container>                    # Inspect a running container
    docker ps -aq | xargs docker rm               # remove all containers

Create and run a Docker Image from a _Dockerfile_

    docker build -t \<image> .
    docker run --rm --name \<container> -d -p 8080:8080 \<image>
    docker logs \<container>
    docker exec -it \<container> /bin/bash 

Push Image to Docker-Hub (https://hub.docker.com/u/thomd)

    docker login
    docker tag \<image> thomd/\<image>:\<tag>
    docker push thomd/\<image>:\<tag>

Alpine Image

    docker run -it alpine:latest /bin/sh
    > apk update
    > apk add nginx

Dockerized Webserver

    docker run -d --rm -v $(pwd):/usr/local/apache2/htdocs -p 80:80 httpd
    echo "Hello Apache" > index.html

    docker run -d --rm -v $(pwd):/usr/share/nginx/html -p 80:80 nginx
    echo "Hello Nginx" > index.html

    docker run -d --rm -v $(pwd):/var/www/html -p 80:80 php:8-apache
    echo -e "\<?php phpinfo(); ?>" > index.php

# Docker Best Practices

  Run interactive Ubuntu

    docker run -it --rm ubuntu /bin/bash
