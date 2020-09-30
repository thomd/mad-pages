
# docker(1)

Container

    docker run -it \<image> /bin/bash              # Start an Ubuntu container with an interactive shell
    docker run --rm \<image> env                   # show environment of a container
    docker inspect \<container>                    # Inspect a running container
    docker ps -aq | xargs docker rm               # remove all containers

Create and run a Docker Image from a _Dockerfile_

    docker build -t thomd/my-app .
    docker run --rm --name \<name> -d -p 8080:8080 thomd/my-app            # run as daemon
    docker logs \<name>
    docker exec -it \<name> /bin/bash                                      # go inside container

Share a Docker Image

    docker login
    docker tag thomd\<image> thomd/\<image>:\<tag>
    docker push thomd/\<image>

_alpine_ Image

    docker run -it alpine:latest /bin/sh
    > apk update
    > apk add nginx

Dockerized Webserver

    docker run -d --rm -v $(pwd):/usr/local/apache2/htdocs -p 80:80 httpd
    docker run -d --rm -v $(pwd):/usr/share/nginx/html -p 80:80 nginx
    echo Hello Apache > index.html
