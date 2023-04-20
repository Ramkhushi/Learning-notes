## Prerequisites of Kubernetes
- [ ] Install Docker (Already Installed on Lab VM)
- [ ] Install Kind on Lab VM

```
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.18.0/kind-linux-amd64
chmod +x ./kind
sudo mv ./kind /usr/local/bin/kind
```

- [ ] Install Kubectl on Lab vm (Already Installed)

```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
sudo mv  kubectl /usr/local/bin
```
- [ ] Install Kubernetes cluster

```
kind create cluster --name <kubernetes cluster>
```

- [ ] Now create a pod using below command

```
kubectl run myapp --image=nginx
```
- [ ] How to Create svc

```
kubectl expose pod myapp --port=80
```
- [ ] Create a deployment

```
kubectl create deployment myapp1 --image=nginx
```
- [ ] Create svc for above deployment 

```
kubectl expose deployment/myapp1 --port=80
```

- [ ]  Access your svc using port forward 

```
kubectl port-forward  <svc/pod/deployment/rs>  <hostport:appport>
```

- [ ] How to Access app
```
localhost:hostpaort
```

#### Integration Kubernetes and jenkins 


- [ ] Copy .kube file to /var/lib/jenkins

```
 cp .kube/  /var/lib/jenkins/ -rvf 
 ```
 - [ ] Add permission so that jenkins users can execute command

```
chown jenkins /var/lib/jenkins/.kube/ -R
```

**Now you should be able to execute any kubectl command from jenkins**




## Frequently used kubernets commands
 ```
 https://kubernetes.io/docs/reference/kubectl/cheatsheet/
 ```
 - [ ] Check no of nodes attached

```
kubectl get nodes
```
- [ ] To check no of pods

```
kubectl get pods
```
- [ ] To check no of deployment

```
kubectl get deploy
```
- [ ] How to check no of SVC

```
kubectl get svc
```


# Optional and Additional
- [ ] Create one deploy

```
kubectl create deployment myapp1 --image=nginx
     
 ```
 - [ ] Create svc 
 
  ```
  kubectl expose deployment/myapp1 --port=80
  ```
 - [ ] Update your deployment
   ```
    kubectl set image deployment myapp1 nginx=httpd
    
    ```
 - [ ] Check your app
     
    ```
   kubectl port-forward deployment/myapp1 81:80
    ```
 - [ ] Rollback your Application
    ```
   kubectl rollout undo deploy/myapp1
    ```
 - [ ] Verify once
    ```
   kubectl port-forward deployment/myapp1 81:80
    ```

