# nginx-template

The helm chart generated with `helm create`. By default chart is generated for nginx.
The chart has template with `values.yaml` config and also tests.

### Install nginx-template chart
`$ helm install nginx-template nginx-template`

### Verify release

`$ kubectl get pods --selector=app.kubernetes.io/name=nginx-template`

On success, above command outputs:

```$xslt
NAME                              READY   STATUS    RESTARTS   AGE
nginx-template-7469db5fbf-v69vk   1/1     Running   0          7m45s
```

### Access nginx

`$ curl http://localhost/nginx-template`

or 

Open web browser and hit `http://localhost/nginx-template`

### Delete nginx-template release

1.  Get release name: `$ helm list --filter nginx-template`
    ```$xslt
    NAME          	NAMESPACE	REVISION	UPDATED                             	STATUS  	CHART               	APP VERSION
    nginx-template	default  	1       	2020-04-10 19:42:10.544842 +0100 BST	deployed	nginx-template-0.1.0	1.16.0   
    ```

2.  Delete release: `$ helm delete nginx-template`
