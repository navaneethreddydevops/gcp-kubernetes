# gcp-kubernetes


### Everything in kubernetes is a object

```
gcloud config set project ${projectname}
```
# Example:
## Create a Project:

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

gcloud container clusters get-credentials ${clustername} --zone us-central1-c --project ${projectname} 

QA:
export clustername="kubernetesdeepdive-qa"
export projectname="navaneethreddy-qa"

gcloud container clusters get-credentials ${clustername} --zone us-central1-c --project ${projectname} 

PROD:
export clustername="kubernetesdeepdive-prod"
export projectname="navaneethreddy-prod"

gcloud container clusters get-credentials ${clustername} --zone us-central1-c --project ${projectname} 

```