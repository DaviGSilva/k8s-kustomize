# Hands-on with K8s Kustomize

Practicing kubernetes using declarative management with Kustomize.

## What did I use?

- MiniKube (https://minikube.sigs.k8s.io/docs/start)
- KubeCTL (https://kubernetes.io/pt-br/docs/tasks/tools)


My current cluster version ``kubectl version``:
````
Client Version: v1.30.1
Kustomize Version: v5.0.4-0.20230601165947-6ce0bf390ce3
Server Version: v1.30.0
````

> **_NOTE:_** If you're using a version below 1.14 you need to install a separate binary to **Kustomize** (https://kubectl.docs.kubernetes.io/installation/kustomize)

## Code Snippets

KubeCTL
````
kubectl create namespace dev
kubectl create namespace prod

kubectl get pods
kubectl get services/svc

kubectl get all
kubectl get all -n dev/prod

kubectl delete pods --all -n dev/prod
kubectl delete services --all -n dev/prod
````

Kustomize
````
kubectl kustomize .
kubectl kustomize overlays/dev/
kubectl kustomize overlays/prod/

kubectl apply -k .
kubectl apply -k overlays/dev/
kubectl apply -k overlays/prod/
````

Minikube
````
minikube start

minikube service kustom-mywebapp-v1
minikube service kustom-mywebapp-v1 -n dev/prod
````

# References

The original content came from the "DevOps Journey" youtube channel:

[Kustomize: The Best Way to Manage Your Kubernetes Configs](https://www.youtube.com/watch?v=spCdNeNCuFU)
