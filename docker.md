
# boot2docker(1)

Start VM

    boot2docker start
    eval "$(boot2docker shellinit)"               # set the environment variables in your shell
    boot2docker status

Usage

    boot2docker ip                                # IP of the VM's Host interface
    boot2docker ssh                               # ssh into VM (docker:tcuser)
    boot2docker ssh -L 8000:localhost:8000        # port forwarding

# docker(1)

    docker -d                                     # Start docker daemon
    docker run -ti \<image> /bin/bash              # Start a container with an interactive shell
    docker inspect \<container>                    # Inspect a running container
    docker inspect --format \<pid> \<container>     # Get the process ID for a container
    docker ps                                     # List currently running containers
    docker ps -a                                  # List all containers
    docker images                                 # List all images
