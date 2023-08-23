## What is a resource group

 > A resource group is a container that holds related resources for an Azure solution. The resource group can include all the resources for the solution, or only those resources that you want to manage as a group. You decide how you want to allocate resources to resource groups based on what makes the most sense for your organization. Generally, add resources that share the same lifecycle to the same resource group so you can easily deploy, update, and delete them as a group.

 > The resource group stores metadata about the resources. Therefore, when you specify a location for the resource group, you are specifying where that metadata is stored. For compliance reasons, you may need to ensure that your data is stored in a particular region.

## Create resource groups
 
 > Create a new resource group in the France Central region.
 - ``` az group create -l francecentral -n rg-webinar-francecentral-001 ```
 - ![](/pic/rg-result.jpg)

 ##### Note
 > Azure provide naming convention for ressources. Please see a picture as a reference
 > ![](/pic/naming.jpg)
