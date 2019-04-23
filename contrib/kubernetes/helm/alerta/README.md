
### NOTES:
#### See my medium post  at medium.com@IrekRomaniuk

###### export KUBECONFIG=/mnt/c/Users/irekromaniuk/AzureDevOps/aks-engine/_output/k8scfn/kubeconfig/kubeconfig.eastus.json

###### cd contrib/kubernetes/helm

###### helm install -f alerta/values.yaml alerta/ --name alerta
```
Error: found in requirements.yaml, but missing in charts/ directory: postgresql
```

###### cd alerta

###### helm dependency update

```
Hang tight while we grab the latest from your chart repositories...
...Successfully got an update from the "rook-stable" chart repository
...Successfully got an update from the "istio.io" chart repository
...Unable to get an update from the "local" chart repository (http://127.0.0.1:8879/charts):
        Get http://127.0.0.1:8879/charts/index.yaml: dial tcp 127.0.0.1:8879: connect: connection refused
...Successfully got an update from the "incubator" chart repository
...Successfully got an update from the "common" chart repository
...Successfully got an update from the "stable" chart repository
Update Complete. ⎈Happy Helming!⎈
Saving 1 charts
Downloading postgresql from repo https://kubernetes-charts.storage.googleapis.com
Deleting outdated charts
```

###### helm del --purge alerta

###### kubectl delete pvc alerta-postgresql (also kubectl delete pv ...)
