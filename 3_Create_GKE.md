## What is GKE?
 
 > Google Kubernetes Engine (GKE) is a managed Kubernetes service for containers and container clusters running on Google Cloud infrastructure.

## Create a GKE cluster

> You can create a zonal cluster by using the gcloud CLI or the Google Cloud console.
> To create a zonal cluster with the gcloud CLI, use one of the following commands.

 ```gcloud container clusters create gke-europe-west3-webinar-001 --machine-type n1-standard-2 --num-nodes 2 --zone europe-west3```

 ![](/pic/gke-result.jpg)


## Merge kubernetes configuration

 > __gcloud container clusters get-credentials__ updates a kubeconfig file with appropriate credentials and endpoint information to point kubectl at a specific cluster in Google Kubernetes Engine.

 ```gcloud container clusters get-credentials gke-europe-west3-webinar-001 --region europe-west3```
 
 >> _Fetching cluster endpoint and auth data.\
    kubeconfig entry generated for gke-europe-west3-webinar-001._