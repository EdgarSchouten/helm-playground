# helm-playground

Playground for helm.

This project uses docker desktop for mac for local kubernetes cluster.

### Pre-requisite

- [Docker desktop for mac](https://docs.docker.com/docker-for-mac/install/)
- [Helm](https://helm.sh/docs/intro/install/) `v3.1.2`

### Install Ingress Controller (optional)

[Install nginx ingress controller README.md](./ingress-controller-nginx/README.md)

### Kubernetes dashboard (optional)

[Install and configure kubernetes dashboard](./kubernetes-dashboard/README.md)

### Helm chart examples

#### 1. [simple nginx chart](./nginx-basic)

#### 2. [nginx template chart](./nginx-template)

#### 3. [upgrade and rollback nginx template release](./nginx-upgrade-rollback)

#### 4. [create chart for dp-caps-service-demo](./dp-caps-service-demo/README.md)

### Bonus
- [use external config](./nginx-external-config)
- [install ops view from remote repository](./kube-ops-view)

     
### References

- [Helm commands](https://helm.sh/docs/helm/helm/)
- [Helm hub](https://hub.helm.sh/)
        