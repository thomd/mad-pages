
# docker-machine(1)

    docker-machine create -d virtualbox dev
    eval "$(docker-machine env dev)"

# docker(1)

    docker run -ti \<image> /bin/bash              # Start a container with an interactive shell
    docker inspect \<container>                    # Inspect a running container
    docker inspect --format \<pid> \<container>     # Get the process ID for a container
    docker ps                                     # List currently running containers
    docker ps -a                                  # List all containers
    docker images                                 # List all images
