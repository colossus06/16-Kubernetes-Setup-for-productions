# 16-Kubernetes-Setup-for-productions
## Minikube environment for testing

```
minikube status
kubectl create deployment hello-minikube --image=k8s.gcr.io/echoserver:1.0
kubectl get deployments
kubectl get pods
```

![image](https://user-images.githubusercontent.com/96833570/221562064-100866ca-30a1-4af5-801b-a6e0f94e5a3b.png)

When you describe the pod with `kubectl describe pod hello-minikube-844fbb9876-n8x9x`:

![image](https://user-images.githubusercontent.com/96833570/221564734-3d87677c-242d-45e3-9f8f-db40aed48871.png)

`kubectl expose deployment hello-minikube --type=LoadBalancer --port=8080`

![image](https://user-images.githubusercontent.com/96833570/221565199-de4bf375-edda-4d36-87b7-4d4290bb61a7.png)



## Debugging 

```
error: failed to create deployment: Post "https://kubernetes.docker.internal:6443/apis/apps/v1/namespaces/default/deployments?fieldManager=kubectl-create&fieldValidation=Strict": dial tcp 127.0.0.1:6443: connectex: No connection could be made because the target machine actively refused it.
```

I got this error and solved simply by starting docker on windows.



## REf

https://kubernetes.io/docs/tutorials/hello-minikube/
