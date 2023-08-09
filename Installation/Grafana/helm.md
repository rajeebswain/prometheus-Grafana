# Install using Helm

## Add helm repo

`helm repo add grafana https://grafana.github.io/helm-charts`

## Update helm repo

`helm repo update`

## Install helm 

`helm install grafana grafana/grafana`

## Expose Grafana Service

`kubectl expose service grafana — type=NodePort — target-port=3000 — name=grafana-ext`

## Access Grafana Web UI

### Expose Grafana service in minikube:
```
minikube service grafana-ext --url
```
### In the above command service name varies , here grafana-ext is the service name. To get the exacy service name use the command `kubectl get svc`

## References

[Ref1](https://brain2life.hashnode.dev/prometheus-and-grafana-setup-in-minikube)
[Ref2](https://blog.marcnuri.com/prometheus-grafana-setup-minikube)
[Ref3](https://opensource.com/article/21/6/chaos-grafana-prometheus)
