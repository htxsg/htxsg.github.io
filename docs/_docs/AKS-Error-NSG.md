---
title: AKS Provisioning Error due to NSG
subtitle: Issues encountered during the setup AKS in Level 4 using CAF codes.
author: raj
tags: [AKS, Troubleshoot]
---

## Issue

When AKS was deployed from the bamboo pipeline, the pipeline failed with the below error message:

```
Code="ControlPlaneAddOnsNotReady"
Message="Pods not in Running status: coredns-69c47794-tbf9z,coredns-autoscaler-5f85dc856b-nfdpq,metrics-server-79f9556b5b-hdpsd,tunnelfront-55688c684-6ht4l,tunnelfront-569f899fd9-z2gr8"
```

After investigation, we found that some of the components inside the AKS get created like node pool, MSI, etc gets created but some other components needed for AKS are not getting created.

### Screenshot of AKS Provisioning Errors

Refer to the attached screenshots:


{% include image.html img="aks-error-nsg/image-20220524-075843.png" caption="Not all components created in AKS" %}

{% include image.html img="aks-error-nsg/image-20220524-075926.png" caption="Node Pool Provisioning State in Scaling" %}

{% include image.html img="aks-error-nsg/image-20220524-080005.png" caption="Resource Status in Creating" %}

{% include image.html img="aks-error-nsg/image-20220524-080100.png" caption="Deployment Failed" %}




## Investigation

The issue was caused by Network Security Group (NSG) was not opened. Port 443 needs to be opened to **Microsoft Container Registry** and the below **FQDN**s.

Based on [Microsoft Article](https://docs.microsoft.com/en-us/azure/aks/limit-egress-traffic)  we need to allow the following FQDN/destinations for port 443:

```
*.hcp.SoutheastAsia.azmk8s.io
mcr.microsoft.com
*.data.mcr.microsoft.com
management.azure.com
ogin.microsoftonline.com 
Index of / 
acs-mirror.azureedge.net
```

In addition, use the MCR Service tag (**MicrosoftContainerRegistry**) and add the Azure Front Door service tag (**AzureFrontDoor.FirstParty**) as well as dependency. Reference: [Azure service tags overview](https://docs.microsoft.com/en-us/azure/virtual-network/service-tags-overview)

> After opening 443 for the above 2 service tags in the NSG, the AKS
> deployment went through successfully.