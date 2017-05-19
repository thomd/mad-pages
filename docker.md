
# docker-machine(1)

    docker-machine ls
    docker-machine create -d virtualbox dev

    docker-machine start dev
    eval "$(docker-machine env dev)"

    docker-machine ip dev                         # get IP

# docker(1)

    docker images                                 # list local images (in /var/lib/docker of your VM)
    docker run -it ubuntu /bin/bash               # Start an Ubuntu container with an interactive shell
    docker inspect \<container>                    # Inspect a running container
    docker inspect --format \<pid> \<container>     # Get the process ID for a container
    docker ps                                     # List currently running containers
    docker ps -a                                  # List all containers
    docker images                                 # List all images
    docker ps -aq | xargs docker rm               # remove all containers

Share an image

    docker login
    docker tag \<image> thomd/\<image>:\<tag>
    docker push thomd/\<image>
    docker run thomd/\<image>


