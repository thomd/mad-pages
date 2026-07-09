# minikube(1)

    minikube start --driver docker --nodes 1      # start one kubernets cluster in a Docker container and configure kubectl via ~/.kube/config file
    minikube status                               # should be Running
    kubectl config use-context minikube           # use minikube context

    minikube ip                                   # get IP of the primary control plane node
    minikube logs                                 # debug logs of Minikube cluster
    minikube ssh                                  # log into the minikube environment (same as docker exec -it -w /home/docker minikube /bin/bash)

    minikube stop
    minikube delete --purge                       # delete minikube container and remove minikube from ~/.kube/config

## Minikube Dashboard

    minikube dashboard                                # start proxy and open in browser (stop with ctrl-c)
    minikube dashboard --url                          # start proxy and show URL

## Minikube Metrics

    minikube addons enable metrics-server
    kubectl top node

## Minikube Ingress

The Ingress controller runs in its own dedicated namespace ingres-nginx. Wait for its status to show as fully active

    minikube addons enable ingress
    kubectl rollout status deployment ingress-nginx-controller -n ingress-nginx --timeout=90s

## Local Docker Registry with Minikube

By default, Kubernetes will try to pull images from a public registry (Docker Hub).

Set up and use a local container registry for your images:

    minikube start
    minikube addons enable registry                   # the registry will be available on localhost:PORT. PORT is told on startup
    eval $(minikube -p minikube docker-env)           # make local docker command communicate with Minikube’s Docker daemon
    docker build -t IMAGE .
    docker tag IMAGE:latest IMAGE:VERSION
    docker push localhost:PORT/IMAGE:VERSION

