
![](/images/k8.png)

Kubernetes, also known as K8s, is an open-source system for automating deployment, scaling, and management of containerized applications.

Kubernetes is a open-source container orchestrator

Kubernetes clusters together groups of hosts running containers, and helps you easily and efficiently manage those clusters.

### What is a Kubernetes Cluster? 
[11 Key Components](https://www.aquasec.com/cloud-native-academy/kubernetes-101/kubernetes-cluster/) 

Kubernete is a container orchestrator used to deploy, automate and manage large-scale containerized workloads. A Kubernetes cluster is a collection of nodes on which workloads can run—these can be physical (bare metal) machines, or virtual machines (VMs), or serverless compute systems like Amazon Fargate. It is managed by a control plane, which is responsible for the orchestrating container activity on the nodes, and maintaining the desired cluster state.


- Open Docker > Settings > Kubernetes > tick `Enable Kubernetes` then `Apply and Restart`
- On the terminal `kubectl`
- Then check the virsion `kubectl version`
- kubectl get service `kubectl get svc`
- to Delete `kubectl delete <name>`
- `sudo kubectl create -f nginx_deploy.yml`
- `kubectl get deploy`
- `kubectl get pods`
Other commands
- `kubectl run deployment sparta-app --image=imagename:tag --port=port--replicas=number`
- `kubectl run deployment spata-app --image=name --port=5000 --replicas=3`
- `sudo kubectl run sparta-app --image=eng99/eng99-final-project:latest --port=5000 --replicas=2`
- `kubectl run app --image=sparta-app:v1 --port=3000.....`
- `kubectl edit deploy sparta-app`
- `kubectl get deply`
- `kubectl get node`
- `

## Its benefits
- Self Healing
- Load Balancing and Service Discovery
- Automated rollouts and rollback
- Auto Scaling
- Automatic bin packing
- Storage orchestration

### Kubernetes Architecture and Terminology
- When you deploy Kubernetes, you get a cluster.
- A Kubernetes cluster consists of a set of worker machines, called nodes, that run containerized applications. Every cluster has at least one worker node.
- The worker node(s) host the Pods that are the components of the application workload.
- A node can be either a virtual or physical machine, depending on the cluster. You'll usually have several nodes on each cluster, and on each node you'll find the kubelet, kube-proxy and container runtime.

![](/images/Kubernetes--Architecture-Diagram-768x555.jpeg)

- [read more here](https://www.aquasec.com/cloud-native-academy/kubernetes-101/kubernetes-architecture/)

### Load balancer
Load balancing is a straightforward task in many non-container environments, but it involves a bit of special handling when it comes to containers. There are two types of load balancing in Kubernetes 
- Internal load balancing across containers of the same type using a label, and 
- External load balancing.


## install hyperhit and minikube
brew update
brew install hyperkit
brew install minikube
kubectl
minikube

## create minikube cluster
minikube start --vm-driver=hyperkit
kubectl get nodes
minikube status
kubectl version

## delete cluster and restart in debug mode
minikube delete
minikube start --vm-driver=hyperkit --v=7 --alsologtostderr
minikube status

## kubectl commands
kubectl get nodes
kubectl get pod
kubectl get services
kubectl create deployment nginx-depl --image=nginx
kubectl get deployment
kubectl get replicaset
kubectl edit deployment nginx-depl

## debugging
kubectl logs {pod-name}
kubectl exec -it {pod-name} -- bin/bash

## create mongo deployment
kubectl create deployment mongo-depl --image=mongo
kubectl logs mongo-depl-{pod-name}
kubectl describe pod mongo-depl-{pod-name}

## delete deplyoment

kubectl delete deployment mongo-depl
kubectl delete deployment nginx-depl

## create or edit config file

    vim nginx-deployment.yaml
    kubectl apply -f nginx-deployment.yaml
    kubectl get pod
    kubectl get deployment

## delete with config
kubectl delete -f nginx-deployment.yaml
## Metrics
kubectl top The kubectl top command returns current CPU and memory usage for a cluster’s pods or nodes, or for a particular pod or node if specified.