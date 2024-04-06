**Overview**

This module will take care of InventoryManagement which manages-
1. FarmCollection
2. Farm
3. Enclosures in Farm

**Use Cases**

1. We should be able to register Tenant in our System.
2. We should be able to create a FarmCollection for each tenant.
3. We should be able to create Farms under FarmCollection.
4. We should be able to add Enclosures as entities in Farm.
5. We should be able to map Water Monitoring Sensors and Cameras in each Enclosure.
6. We should be able to map Fish count in each Enclosure.


**Assumptions**

1. Mac Address of each Water Monitoring sensors and Camera will be coming in all data packets. We will use Mac address as unique identifiers for devices in inventory.
2. We can physically assign an identifier to Enclosure and same identifier can be configrued in Water Monitoring sensors and Camera so that when we will start getting data from these devices, we can map from which Enclosure it is coming.
3. There will be no unique identifier for Fish.
4. Camera can detect Fish count in Enclosure.


**Use Case Details**

1. **Farm Bootstraping**

Tenant, FarmCollection and Farm registration will be simple UI driven Steps, which will create entries in InventoryDatabase.
Once Enclosures are set up in field along with Water Monitoring sensors and Camera, Operator will upload this data in system under Farm to which they belong. This way we know association between Enclosures and Devices to Farm.

2. **Adding New Enclosure/Device to system**

Once a new Enclosure/Device is added in field, Operator will upload this detail under farm. 


3. **Payload Structure For Data packets**

![image](https://github.com/vivek-singh2/ArchitecturalKatas/assets/108721284/bf838cfc-ec32-4d42-a9cd-2f6346a57a3d)



4. **Getting Fish Health Data**

	Camera is going to send us-	
	* Fish Physical Attributes such as size, wings, colors etc.
	* Fish Behavioural Attributes such as active, inactive (may be due to bad health)
	* We will keep on storing this data and at any point of time Alerting engine can utilize this data to raise alarms.
	
	
5. **Detecting Fish Count Change in Enclosure**

Camera will push an event "Current Fish Count" periodically (Every 12 Hour).
New fish can be added to Enclosure by farmer or can result through breeding. On contrary fish can die due to health issue/environmental issue.
"Current Fish Count" will send us current count and we can update the count in InventoryDatabase.
Alarms can be raised if there is sudden decrease in count.
By analysing timings when fish count increases, we can identify best harvesting time as well.

![image](https://github.com/vivek-singh2/ArchitecturalKatas/assets/108721284/b64de2e2-f8b9-4267-8c84-2f7396967706)









	


