Overview
This module will take care of InventoryManagement which manages-
1.FarmCollection
2.Farm
3.Enclosures in Farm
4.Devices(Water Monitoring sensors and Camera) in each Enclosure
5.Fish (Or can say Cattle) in each Enclosure

Use Cases

We should be able to register Tenant in our System.
We should be able to create a FarmCollection for each tenant.
We should be able to  create Farms under FarmCollection.
We should be able to add Enclosures as entities in Farm.
We should be able to map Water Monitoring Sensors and Cameras in each Enclosure.
We should be able to map Fish count in each Enclosure.


Assumptions
Mac Address of each Water Monitoring sensors and Camera will be coming in all data packets. We will use Mac address as unique identifiers for devices in inventory.
We can physically assign an identifier to Enclosure and same identifier can be configrued in Water Monitoring sensors and Camera so that when we will start getting data from these devices, we can map from which Enclosure it is coming.




