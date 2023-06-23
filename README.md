# Kubernetes-minikube-setup

## Kubernetes setup (kubectl) :

- Go to the official documentation of kubernetes `kubernetes.io`

### Intel mac :

```
   curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/darwin/amd64/kubectl"
```

### M1 chip :

```
   curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/darwin/arm64/kubectl"
```

### x86 Linux :

```
   curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```

## Minikube setup :

- Go to the official documentation of kubernetes `https://minikube.sigs.k8s.io/docs/start/`

### Intel mac :

```
  curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-darwin-amd64
  sudo install minikube-darwin-amd64 /usr/local/bin/minikube

```

### M1 chip :

```
  curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-darwin-arm64
  sudo install minikube-darwin-arm64 /usr/local/bin/minikube

```

### x86 Linux :

```
  curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
  sudo install minikube-linux-amd64 /usr/local/bin/minikube

```

## Deployment of hello world minikube to test our setup :

- First step
```
minikube start
```

- Create a sample deployment and expose it on port 8080:

```
kubectl create deployment hello-minikube --image=kicbase/echo-server:1.0
kubectl expose deployment hello-minikube --type=NodePort --port=8080
```

- It might take some time to run .

```
kubectl get services hello-minikube
```

<img width="573" alt="image" src="https://github.com/Kamalesh-Seervi/kubernetes-minikube-setup/assets/107933310/07db2b03-346a-4b7a-a8b7-0de0087c3a6d">


- The easiest way to access this service is to let minikube launch a web browser for you:


```
minikube service hello-minikube
```


<img width="682" alt="image" src="https://github.com/Kamalesh-Seervi/kubernetes-minikube-setup/assets/107933310/2e5a5bce-3797-4fa9-b71d-abf953aecaf9">


- Check the service url from the terminal


<img width="1381" alt="image" src="https://github.com/Kamalesh-Seervi/kubernetes-minikube-setup/assets/107933310/3d7af92d-762d-46c6-ad41-21fb8780fcdc">


## Manage your cluster:

- Pause Kubernetes without impacting deployed applications

```
minikube pause
```

- Unpause a paused instance

```
minikube unpause
```

- Halt the cluster

```
minikube stop
```

- Delete all of the minikube clusters:

```
minikube delete --all
```
