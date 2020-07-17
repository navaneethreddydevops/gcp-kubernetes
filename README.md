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