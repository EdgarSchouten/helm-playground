# Kubernetes Dashboard

Dashboard is a web-based Kubernetes user interface. You can use Dashboard to deploy containerized 
applications to a Kubernetes cluster, troubleshoot your containerized application, and manage the 
cluster resources. You can use Dashboard to get an overview of applications running on your cluster,
 as well as for creating or modifying individual Kubernetes resources (such as Deployments, Jobs, 
 DaemonSets, etc). For example, you can scale a Deployment, initiate a rolling update, restart a pod
  or deploy new applications using a deploy wizard.
  
### Install kubernetes dashboard

The kubernetes dashboard is not deployed by default. To deploy it, run the following command:

`$ kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v1.10.1/src/deploy/recommended/kubernetes-dashboard.yaml`
  
### Deploying the Dashboard UI

The Dashboard UI is not deployed by default. To deploy it, run the following command:

`$ kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.0.0-beta8/aio/deploy/recommended.yaml`

### Accessing the Dashboard UI

- Run command `kubectl proxy` and let it keep running.

- Open below URL in web browser.

  `http://localhost:8001/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/#!/login`

- Get login token using `kubectl describe secret kubernetes-dashboard --namespace=kube-system`
  and pass it to dashboard UI.

### Reference

https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/

