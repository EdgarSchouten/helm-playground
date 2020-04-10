# Kubernetes Operational View Helm Chart

[Kubernetes Operational View](https://github.com/hjacobs/kube-ops-view) provides a read-only system dashboard for multiple K8s clusters

[ops-view chart](https://hub.helm.sh/charts/incubator/kube-ops-view)

## Installing the Chart

To install the chart with the release name my-release:

```console
$ helm install ops-view-release incubator/kube-ops-view
```

The command deploys Kubernetes Operational View on the Kubernetes cluster in the default configuration.

## Accessing the UI

```console
$ kubectl proxy
```

Assuming you used `ops-view-release` for installation, you can now access the UI in your browser by opening 
`http://localhost:8001/api/v1/namespaces/default/services/ops-view-release-kube-ops-view:/proxy/#`

## Uninstalling the Chart

To uninstall/delete the my-release deployment:

```console
$ helm delete ops-view-release
```

The command removes all the Kubernetes components associated with the chart and deletes the release.
