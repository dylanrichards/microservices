# Kubernetes Dashboard

`kube-dashboard` [Dashboard](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard)
[Github v2.5.1](https://github.com/kubernetes/dashboard/blob/v2.5.1/aio/deploy/recommended.yaml)

`ingress-dashboard` Ingress rules for accessing the dashboard.
Add `127.0.0.1 dashboard` to the /etc/hosts or C:\Windows\System32\drivers\etc\hosts file.
Then go to https://dashboard to access

`admin-user` Creates a Service Account for authenticating to the dashboard.
Since Kubernetes v1.24.0 the secret is not auto-generated.

Copy the login token from
```
kubectl -n kubernetes-dashboard describe secret secret-admin-user | grep 'token:' | awk '{print $2}'
```

## Commands to Deploy

```
kubectl apply -f .\infra\k8s\dashboard\kube-dashboard.yaml
kubectl apply -f .\infra\k8s\dashboard\ingress-dashboard.yaml
kubectl apply -f .\infra\k8s\dashboard\admin-user.yaml
```