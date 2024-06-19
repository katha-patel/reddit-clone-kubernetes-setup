# Reddit Clone App on Kubernetes 
This project demonstrates how to deploy a Reddit clone app on Kubernetes using Minikube cluster and expose it to the world using Ingress.
Below is an overview of the architecture of this Reddit Clone App running on Kubernetes.



## Prerequisites
Before you begin, you should have the following tools installed on your local machine: 

- Docker 
- Minikube cluster ( Running )
- kubectl
- Git

To install Prerequisites follow these steps:

- For Docker Installation: 
```sh
sudo apt-get update
sudo apt-get install docker.io -y
sudo usermod -aG docker $USER && newgrp docker
```

- For Minikube & Kubectl:
```sh
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube 

sudo snap install kubectl --classic
minikube start --driver=docker
```


## Installation
Follow these steps to install and run the Reddit clone app on your local machine:

1) Clone this repository to your local machine: `git clone https://github.com/katha-patel/reddit-clone-kubernetes-setup.git`
2) Navigate to the project directory: `cd reddit-clone-kubernetes-setup`
3) Build the Docker image for the Reddit clone app: `docker build -t reddit-clone-app .`
4) Deploy the app to Kubernetes: `kubectl apply -f deployment.yaml`
1) Deploy the Service for deployment to Kubernetes: `kubectl apply -f service.yaml`
5) Enable Ingress by using Command: `minikube addons enable ingress`
6) Expose the app as a Kubernetes service: `kubectl expose deployment reddit-deployment --type=NodePort --port=5000`
7) Create an Ingress resource: `kubectl apply -f ingress.yaml`


## Test Ingress DNS for the app:
- Test Ingress by typing this command: `curl http://domain.com/test`
