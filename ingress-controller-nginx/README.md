# Install NGINX Ingress Controller on docker desktop for mac

Follow below instructions to install nginx ingress controller on docker desktop for mac.

### Pre-requisite
- [Docker desktop for mac](https://docs.docker.com/docker-for-mac/install/)

### Install mandatory resources

`$ kubectl apply -f mandatory.yaml`

### Install nginx

`$ kubectl apply -f cloud-generic.yaml`

### Verify installation
`$ kubectl get pods --namespace ingress-nginx`

On successful installation, above command results into below output: 
```$xslt
NAME                                        READY   STATUS    RESTARTS   AGE
nginx-ingress-controller-7fcf8df75d-lvkz7   1/1     Running   0          5m41s
```

### Reference

https://kubernetes.github.io/ingress-nginx/deploy/