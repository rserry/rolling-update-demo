# Rolling update demo
## Start the minikube dashboard
```
minikube dashboard
```

```
kubectl apply -f hello-world.yaml
```
## Go to minikube-ip:30007
```
kubectl get pods
kubectl rollout history deployment hello-world-app
```

## Change image to green
```
kubectl set image deployments/hello-world-app hello-world-app=robbes3/hello-world-app:green
```

## View rollout status
```
kubectl rollout status deployment hello-world-app
```

## View rollout history
```
kubectl rollout history deployment hello-world-app
```

## Change image by using edit deployment or editing the original config file
```
kubectl edit deployment hello-world-app
```
```
nano hello-world.yaml
kubectl apply -f hello-world.yaml
```


## Wrong image (doesn't exist)
```
kubectl set image deployments/hello-world-app hello-world-app=robbes3/hello-world-app:red
```

## Undo last update
```
kubectl rollout undo deployment hello-world-app
```