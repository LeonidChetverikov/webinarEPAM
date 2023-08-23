## Prerequisites
 - The latest version of connectedk8s Azure CLI extension, installed by running the following command:\
 ```az extension add --name connectedk8s```
 
 ## Register providers for Azure Arc-enabled Kubernetes

  1. Enter the following commands:
    ```
    az provider register --namespace Microsoft.Kubernetes 
    az provider register --namespace Microsoft.KubernetesConfiguration 
    az provider register --namespace Microsoft.ExtendedLocation 
    ``` 
  ![](/pic/ARC-setup-1.jpg)
  2. Monitor the registration process. Registration may take up to 10 minutes.
   ```
   az provider show -n Microsoft.Kubernetes -o table
   az provider show -n Microsoft.KubernetesConfiguration -o table
   az provider show -n Microsoft.ExtendedLocation -o table
   ```
   Once registered, you should see the _RegistrationState_ state for these namespaces change to _Registered_.
 ![](/pic/arc-setup-2.jpg)
  
## Connect an existing Azure Kubernetes cluster
  
  Run the following command to connect your cluster. This command deploys the Azure Arc agents to the cluster and installs Helm v. 3.6.3 to the _.azure_ folder of the deployment machine. This Helm 3 installation is only used for Azure Arc, and it doesn't remove or change any previously installed versions of Helm on the machine.

  ```
     az connectedk8s connect --name aks-webinar-francecentral-001 --resource-group rg-webinar-francecentral-001
  ```
  ![](/pic/arc-setup-3.jpg)

## Connect an existing Google Kubernetes cluster
  
  1. Check current kubernetes context:\
  ```kubectl config current-context ```

      Output:

     > _aks-webinar-francecentral-001_
  
  2. Switch context to Google kubernetes cluster:\
    - ``` kubectl config get-contexts ```
      ![](/pic/arc-setup-4.jpg)
    -  ```kubectl config use-context gke_compact-buckeye-223805_europe-west3_gke-europe-west3-webinar-001```
      ![](/pic/arc-setup-5.jpg)
  
  3. Run the following command to connect your cluster.\
    ``` az connectedk8s connect --name gke-europe-west3-webinar-001 --resource-group rg-webinar-francecentral-001 ```
     ![](/pic/arc-setup-6.jpg)

## View Azure Arc
  In search string on Azure portal type:\
  _Azure Arc_
   ![](/pic/arc-setup-7.jpg)
   ![](/pic/arc-setup-8.jpg)


