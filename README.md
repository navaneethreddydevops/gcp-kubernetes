# gcp-kubernetes


### Everything in kubernetes is a object

## Create a Project:
```
gcloud config set project ${projectname}
```
# Example:
```
gcloud projects create navaneethreddy-dev
gcloud projects create navaneethreddy-qa
gcloud projects create navaneethreddy-prod
```

# Enable Cloud shell for specific Project

```
DEV:
gcloud config set project navaneethreddy-dev

QA:
gcloud config set project navaneethreddy-qa

PROD:
gcloud config set project navaneethreddy-prod
```

## Connecting to a kubernets cluster
```
gcloud container clusters get-credentials ${clustername} --zone us-central1-c --project ${projectname}
```
## Examples
```
DEV:
export clustername="kubernetesdeepdive-dev"
export projectname="navaneethreddy-dev"
export zone="us-central1-c"

gcloud container clusters get-credentials ${clustername} --zone ${zone} --project ${projectname} 

QA:
export clustername="kubernetesdeepdive-qa"
export projectname="navaneethreddy-qa"
export zone="us-central1-c"

gcloud container clusters get-credentials ${clustername} --zone ${zone} --project ${projectname} 

PROD:
export clustername="kubernetesdeepdive-prod"
export projectname="navaneethreddy-prod"
export zone="us-central1-c"

gcloud container clusters get-credentials ${clustername} --zone ${zone} --project ${projectname} 

```
### Deployment
```
A single pod can be deployed
Pods can be deployed as a required number of replica
```
### Service
```
Pod can be deployed behind the loadbalancer with port binding to localhost
```
### Deamonsets
```
A specific pod will be deployed on every node of a cluster (Example: Node Exporter)
```


NAME: prometheus-1597762294
LAST DEPLOYED: Tue Aug 18 14:51:37 2020
NAMESPACE: default
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
The Prometheus server can be accessed via port 80 on the following DNS name from within your cluster:
prometheus-1597762294-server.default.svc.cluster.local


Get the Prometheus server URL by running these commands in the same shell:
  export POD_NAME=$(kubectl get pods --namespace default -l "app=prometheus,component=server" -o jsonpath="{.items[0].metadata.name}")
  kubectl --namespace default port-forward $POD_NAME 9090


The Prometheus alertmanager can be accessed via port 80 on the following DNS name from within your cluster:
prometheus-1597762294-alertmanager.default.svc.cluster.local


Get the Alertmanager URL by running these commands in the same shell:
  export POD_NAME=$(kubectl get pods --namespace default -l "app=prometheus,component=alertmanager" -o jsonpath="{.items[0].metadata.name}")
  kubectl --namespace default port-forward $POD_NAME 9093
#################################################################################
######   WARNING: Pod Security Policy has been moved to a global property.  #####
######            use .Values.podSecurityPolicy.enabled with pod-based      #####
######            annotations                                               #####
######            (e.g. .Values.nodeExporter.podSecurityPolicy.annotations) #####
#################################################################################


The Prometheus PushGateway can be accessed via port 9091 on the following DNS name from within your cluster:
prometheus-1597762294-pushgateway.default.svc.cluster.local


Get the PushGateway URL by running these commands in the same shell:
  export POD_NAME=$(kubectl get pods --namespace default -l "app=prometheus,component=pushgateway" -o jsonpath="{.items[0].metadata.name}")
  kubectl --namespace default port-forward $POD_NAME 9091

For more information on running Prometheus, visit:
https://prometheus.io/