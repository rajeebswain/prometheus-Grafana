# Install using Helm

## Add helm repo

`helm repo add prometheus-community https://prometheus-community.github.io/helm-charts`

## Update helm repo

`helm repo update`

## Install helm 

`helm install prometheus prometheus-community/prometheus`

## Expose Prometheus Service

This is required to access prometheus-server using your browser.

`kubectl expose service prometheus-server --type=NodePort --target-port=9090 --name=prometheus-server-ext`

## Check Service

`kubectl get svc`
### Search for the type node port and get the TCP port
![image](https://github.com/rajeebswain/prometheus-Grafana/assets/105234711/c49a61eb-2de8-4678-a7b5-f329d21944e3)

# Access to promethus through CLI
### Get the minikube IP
```
minikube ip
```
![image](https://github.com/rajeebswain/prometheus-Grafana/assets/105234711/58bbafc3-4286-4f7f-ae26-0e543a8e98cf)

### Use curl to login
```
curl http://<minikube ip>:tcp port
```
e.g. ![image](https://github.com/rajeebswain/prometheus-Grafana/assets/105234711/569c2b5a-35ca-47e5-a3a8-86f1f45c5912)



## Access promethus through UI.
### Expose the service URL.
```
minikube service <Add the promethus server name> --url
```
for e.g., ![image](https://github.com/rajeebswain/prometheus-Grafana/assets/105234711/82004099-a4a3-475e-aec9-d3caae2a98aa)
The server name got from the command "kubectl get svc"

### Now use the URL in browser which gets from above command to
```
as e.g. http://127.0.0.1:40477
```

## References:
[Ref1](https://blog.marcnuri.com/prometheus-grafana-setup-minikube)
[Ref2](https://opensource.com/article/21/6/chaos-grafana-prometheus)
[Ref3](https://brain2life.hashnode.dev/prometheus-and-grafana-setup-in-minikube)
