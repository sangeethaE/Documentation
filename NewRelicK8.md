## Install New Relic:
  •	Install kube-state-metrics in the pod where Minikube is installed .
  
  ```
  #curl -L -o kube-state-metrics-1.9.5.zip https://github.com/kubernetes/kube-state-metrics/archive/v1.9.5.zip && unzip kube-state-metrics-1.9.5.zip && kubectl apply -f kube-state-metrics-1.9.5/examples/standard
  
  ```
  
•	Download the manifest file:

```
#curl -O https://download.newrelic.com/infrastructure_agent/integrations/kubernetes/newrelic-infrastructure-k8s-latest.yaml

```

•	Add your license key in the newrelic-infrastructure-k8s-latest.yaml file  and name for your cluster

```
  #vi newrelic-infrastructure-k8s-latest.yaml
```

Add below lines in yaml file

```
env:
  - name: NRIA_LICENSE_KEY
    value: YOUR_LICENSE_KEY
  - name: CLUSTER_NAME
    value: YOUR_CLUSTER_NAME
```    

•	Make sure Kubemetrics is installed  with below command

```
#kubectl get pods --all-namespaces | grep kube-state-metrics

```

•	Now Create a New-relic Daemonset 

```
#kubectl create -f newrelic-infrastructure-k8s-latest.yaml

```

•	We can validate the New-relic pod status by below command

```
#Kubectl get pods

```

### Glimpse of NewRelic Dashboard:

<image src="images/newRelic.jpg"/>
