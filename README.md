# Deploy-jenkins-using-k8s

There are multible resources needed to run `Jenkins` on K8S Cluster.

We are using [Docker Desktop](https://www.docker.com/products/docker-desktop/) as our K8S cluster provider.

[Jenkins Docker Hub](https://hub.docker.com/r/jenkins/jenkins)
Deploy jenkins using k8s that have kubectl and docker conatiner


to help you not to download minikube or docker as a plugins

Deploying a slave that have docker container if u want to run your pipline that have docker command on slave 


## 1.1 Run Jenkins on K8S Steps:

> 1. Apply `Jenkins` resources:

```
kubectl apply -f jenkins
```
> 2. Go to slave:
```
kubectl exec -it -n devops-tools name-of-yourpod   -- bash
```

> 2. Go to slave and run:
```
service ssh start
passwd jenkins
--> 123
chmod 666  /var/run/docker.sock
```
> 4. Make sure everything is ok:
```
kubectl get all -n jenkins 

kubectl logs -f  -n jenkins -l app=jenkins
