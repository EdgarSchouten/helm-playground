# nginx-basic

The simplest possible helm chart for nginx

### Install nginx-basic chart
`$ helm install nginx nginx-basic`

### Verify installation

`$ kubectl get pods --selector=app=nginx`

On success, above command outputs:

```$xslt
NAME                           READY   STATUS    RESTARTS   AGE
nginx-basic-66bf74b75c-4hstl   1/1     Running   0          15s
```

### Access nginx

`$ curl http://localhost/nginx`

or 

Open web browser and hit `http://localhost/nginx`

### Delete nginx-basic chart

1.  Get release name: `$ helm list`
    ```$xslt
    NAME 	NAMESPACE	REVISION	UPDATED                             	STATUS  	CHART            	APP VERSION
    nginx	default  	1       	2020-04-10 19:30:32.177196 +0100 BST	deployed	nginx-basic-0.1.0	1.0     
    ```

2.  Delete release: `$ helm delete nginx`
