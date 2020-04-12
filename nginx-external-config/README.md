# nginx-external-config

The helm install/upgrade can override config either using external yaml file or individual properties.

### Install chart with external config yaml

`$ helm install nginx-template nginx-template --values ./nginx-external-config/new-values.yaml`

### Install chart with external config value

`$ helm install nginx-template nginx-template --set ingress.hosts[0].host=localhost 
--set ingress.hosts[0].paths[0]=/nginx-template-value`