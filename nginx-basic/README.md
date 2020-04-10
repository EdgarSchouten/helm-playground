# nginx-basic

The simplest possible helm chart for nginx

### Install nginx-basic chart
`$ helm install nginx-basic`

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
    NAME         	REVISION	UPDATED                 	STATUS  	CHART            	APP VERSION	NAMESPACE
    mangy-chicken	1       	Fri Apr 10 12:44:10 2020	DEPLOYED	nginx-basic-0.1.0	1.0        	default 
    ```

2.  Delete release: `$ helm delete mangy-chicken`
