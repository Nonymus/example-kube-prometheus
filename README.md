# Dashboard loading in kube-prometheus

This is a small example on how to use the 
[kube-prometheus](https://github.com/coreos/prometheus-operator/tree/master/helm) helm chart as dependency while adding 
dashboards from files.

## TL; DR
```bash
helm repo add coreos https://s3-eu-west-1.amazonaws.com/coreos-charts/stable/
helm install coreos/prometheus-operator --name prometheus-operator --namespace monitoring
helm dep build dashboard-loader
helm install dashboard-loader --name dashboard-loader --namespace monitoring
``` 

Visiting http://\<node-ip>:30910/ , you should find Grafana with the default dashboards and an additional 
dashboard, which has been created from [example-dashboard.json](dashboard-loader/dashboards/example-dashboard.json)
