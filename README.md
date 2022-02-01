# edu-airflow-helm-argo

Can be easily implemented with Docker Desktop

1. Install Argo from [getting started](https://argo-cd.readthedocs.io/en/stable/getting_started/)

2. Add application

```
argocd app create applications \
  --repo https://github.com/yurgas/edu-airflow-helm-argo.git \
  --path argo \
  --dest-server https://kubernetes.default.svc \
  --dest-namespace argo
```

3. Open proxy connection to airflow web-server (assuming 8080 is busy with Argo)
```
kubectl port-forward svc/airflow-webserver 8081:8080 --namespace airflow-official
```
