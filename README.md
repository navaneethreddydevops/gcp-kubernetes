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