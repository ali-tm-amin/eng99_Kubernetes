
![](/k8.png)

Kubernetes, also known as K8s, is an open-source system for automating deployment, scaling, and management of containerized applications.

Kubernetes is a open-source container orchestrator

Kubernetes clusters together groups of hosts running containers, and helps you easily and efficiently manage those clusters.

- Open Docker > Settings > Kubernetes > tick `Enable Kubernetes` then `Apply and Restart`
- On the terminal `kubectl`
- Then check the virsion `kubectl version`
- kubectl get service `kubectl get svc`
- to DElete `kubectl delete <name>`
- `sudo kubectl create -f nginx_deploy.yml`
- `kubectl get deploy`
- `kubectl get pods`

## Its benefits
- Self Healing
- Load Balancing and Service Discovery
- Automated rollouts and rollback
- Auto Scaling
- Automatic bin packing
- Storage orchestration

### Loadbalancer
### Selector