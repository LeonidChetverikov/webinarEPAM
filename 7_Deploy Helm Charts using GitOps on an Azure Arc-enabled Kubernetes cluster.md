## Prerequisites

  - Install the k8s-configuration Azure CLI extension of version >= 1.0.0\
    ``` 
    az extension add --name k8s-configuration 
    az extension add -n k8s-extension
    ```

## Create a configuration

  - Before proceeding with deploying your application using the Azure Arc GitOps extension, ensure that you have Azure Arc installed on your Kubernetes cluster.

    ```
    az k8s-configuration flux create \
    --cluster-name aks-webinar-francecentral-001 \
    --resource-group rg-webinar-francecentral-001 \
    --name flux-azure-arc \
    --namespace default \
    --cluster-type connectedClusters \
    --scope cluster \
    --url https://github.com/LeonidChetverikov/webinarEPAM \
    --branch main  \
    --kustomization name=app path=./releases prune=true
    ```

    ---

   ```
   az k8s-configuration flux create \
   --cluster-name gke-europe-west3-webinar-001 \
   --resource-group rg-webinar-francecentral-001 \
   --name flux-azure-arc \
   --namespace default \
   --cluster-type connectedClusters \
   --scope cluster \
   --url https://github.com/LeonidChetverikov/webinarEPAM \
   --branch main  \
   --kustomization name=app path=./releases prune=true
   ```


    

