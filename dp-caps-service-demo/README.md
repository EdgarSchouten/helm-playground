# dp-caps-service-demo

The helm chart for dp-caps-service-demo.

It is assumed that docker image for dp-caps-service-demo already pulled on local.

### Create helm chart

Run command `$ helm create dp-caps-service-demo`

It will generate helm chart with default template values.

### Updated generated chart as per demo service requirements

Update `values.yaml` as follow:

- `image.repository` to `dp-caps-service-demo:1.0.0`
- `service.port` to `8000`
- `ingress.enabled` to `true`
- `ingress.annotations` to `{nginx.ingress.kubernetes.io/rewrite-target: /health}`
- `ingress.hosts.host` to `localhost`
- `ingress.hosts.paths` to `[/demo]`


Update `templates/deployment.yaml` as follows:

- remove `:{{ .Chart.AppVersion }}` from `image` value
- update `containerPort` value to `{{ .Values.service.port }}`
- liveness and readiness probe `path` to `/health`

### Install demo service

`$ helm install dp-caps-service-demo dp-caps-service-demo/`