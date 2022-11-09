# Azure App Service Plans

__Category: Azure__

Apps Service apps run in an App Service plan which defines a set of computing resources for a specifed region. One or more apps can be configured to run on the same computing resources or plan including Azure Functions.

Each App Service plan defines the following:

* Region
* Number of VM instances
* Size of VM instances (Small, Medium, Large)
* Pricing tier (Free, Shared, Basic, Standard, Premium, PremiumV2, PremiumV3, Isolated)

Free and Shared pricing tiers share the resource pools of your apps with other customers and should only be used for development and testing purposes.

Basic, Standard, Premium, PremiumV2, and PremiumV3 pricing tiers run apps on dedicated Azure VMs.

Isolated pricing tier provides network isolation on top of compute isolation and therefore maximum scalability.
