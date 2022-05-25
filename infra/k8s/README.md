# Kubernetes Objects

`ingress-controller` [Kubernetes Ingress Controller](https://kubernetes.io/docs/concepts/services-networking/ingress-controllers/)
[Minikube NGINX Ingress Controller](https://kubernetes.io/docs/tasks/access-application-cluster/ingress-minikube/)

`web-app` Kubernetes Deployment and Service for the web microservice

`ingress-srv` [Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/) rules for microservices.

## Commands to Deploy

```
kubectl apply -f .\infra\k8s\ingress-contoller.yaml
kubectl apply -f .\infra\k8s\web-app.yaml
kubectl apply -f .\infra\k8s\ingress-srv.yaml
```