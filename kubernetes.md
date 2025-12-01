# Kubernetes

    kubectl config current-context                # minikube or microk8s ?

## Minikube

  Start

    minikube start --nodes 1                      # start one kubernets cluster in a Docker container and configure kubectl via ~/.kube/config file
    minikube status                               # should be Running
    kubectl config current-context                # verify kubectl context. Should be minikube
    docker ps -f name=minikube                    # show container running minikube
    kubectl get nodes                             # node should be: minikube
    kubectl get services                          # service should be: kubernetes

    minikube ip                                   # get IP of the primary control plane node
    minikube logs                                 # debug logs of Minikube cluster
    minikube ssh                                  # log into the minikube environment (same as docker exec -it -w /home/docker minikube /bin/bash)

  Stop

    minikube stop
    minikube status                               # should be Stopped
    minikube delete                               # delete minikube container and remove minikube from ~/.kube/config

## MicroK8s

  Start

    microk8s start                                # start the kubernetes cluster
    microk8s config >> ~/.kube/config             # point kubectl to MicroK8s
    kubectl config current-context                # verify kubectl context &rarr; should be microk8s
    microk8s status                               # should show microk8s is running
    kubectl get nodes                             # node should be: microk8s-vm
    kubectl get services                          # service should be: kubernetes

    multipass info microk8s-vm                    # get IPs
    multipass shell microk8s-vm                   # ssh into MicroK8s VM

  Stop

    microk8s stop                                 # stop the kubernetes cluster
    microk8s status
    microk8s uninstall                            # remove microk8s-vm from Multipass VM Manager

## kubectl(1)

    kubectl get all

