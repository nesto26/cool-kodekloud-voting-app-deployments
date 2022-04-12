# cool-kodekloud-voting-app with deployments

This is a simple kubernetes voting app deployment that was discussed in the kodekloud.com
for "Kubernetes for the Absolute Beginners - Hands-on" course.

## How to deploy in minikube?
1.  Install Oracle VM
2.  Install kubectl
3.  Install minikube
4.  Deploy the k8s deployment and services
    a. kubectl create -f voting-app-deploy.yaml
    b. kubectl create -f voting-app-service.yaml
    c. kubectl create -f redis-deploy.yaml
    d. kubectl create -f redis-service.yaml
    e. kubectl create -f postgres-deploy.yaml
    f. kubectl create -f postgres-service.yaml
    g. kubectl create -f result-app-deploy.yaml
    h. kubectl create -f result-app.service.yaml
    i. kubectl create -f worker-app-deploy.yaml


## How to verify the k8s deployment?
Execute **kubectl get deploy,svc**

## How to scale the deployment?
Execute kubectl scale deployment <deployment-name> --replicas=<instended #replicas>
  
## How to cast the vote and verify the result?
Identify the URL: minikube service <service-name> --url
  
  
## IMPORTANT ##
If the intended deployment is for the cloud, modify the voting-app-service and result-app-service to use a service type of LoadBalancer instead of NodePort.
This is true for any cloud platform such as GCP, AWS and Azure.
  
