## Control traffic routing with weighted endpoints by using Traffic Manager

We wil descrobe how to use Azure Traffic Manager to control routing of user traffic between endpoints by using the weighted routing method.

## Prerequisites

  - Two instances of external service of aur sambple application
  - Traffic Manager routes user traffic to a semple website that has higher weight assigned to its endpoint.

## Create a Traffic Manager profile

  Create a Traffic Manager profile based on the Weighted routing method.
  - On the upper-left side of the screen, select **Create a resource > Networking > Traffic Manager profile > Create**.
  - In **Create Traffic Manager profile**, enter or select the following information. Accept the defaults for the other settings, and then select **Create**.
---

| Setting   | Value  |
|---|---|
| Name  |  Enter a unique name within the trafficmanager.net zone. It results in the DNS name trafficmanager.net, which is used to access your Traffic Manager profile. |
|  Routing method | Select the **Weighted** routing method.  |
|  Subscription |  Select your subscription. |
|  Resource group |  Select **Use existing** and then select prevously created RG |
    
## After creation you will got such sittuation:
![](/pic/TM-02.jpg)
![](/pic/TM-01.jpg)
