## What is AKS? 

 > Azure Kubernetes Service (AKS) offers the quickest way to start developing and deploying cloud-native apps in Azure, datacenters, or at the edge, with built-in code-to-cloud pipelines and guardrails. As a hosted Kubernetes service, Azure handles critical tasks, like health monitoring and maintenance.

## Create AKS in previously created ressource group

 > Create an AKS cluster using the az aks create command with the --enable-addons monitoring parameter to enable Azure Monitor Container insights with managed identity authentication (Minimum Azure CLI version 2.49.0 or higher).


 ``` az aks create -g rg-webinar-francecentral-001 -n aks-webinar-francecentral-001 --enable-managed-identity --node-count 2 --enable-addons monitoring --generate-ssh-keys ```

 > After a few minutes, the command completes and returns JSON-formatted information about the cluster.

 ![](/pic/aks-result.jpg)

 > **Note.**
 > When you create a new cluster, AKS automatically creates a second resource group to store the AKS resources. 

## Merge kubernetes configuration

> Configure kubectl to connect to your Kubernetes cluster using the az aks get-credentials command. \
This command executes the following operations:

  - Downloads credentials and configures the Kubernetes CLI to use them.
  - Uses ~/.kube/config, the default location for the Kubernetes configuration file. Specify a different location for your Kubernetes configuration file using --file argument.

``` az aks get-credentials --resource-group rg-webinar-francecentral-001 --name aks-webinar-francecentral-001```

>> _Merged "aks-webinar-francecentral-001" as current context in /Users/leonidchetverikov/.kube/config_
