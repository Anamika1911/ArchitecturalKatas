# FishWatch
This application aims to automate fish farming management. There are a lots of aspects that needs to be taken care of in this regard. Current application takes care of following aspects:
- [Automatic management of sensor devices and cameras](KeyCapabilities/DeviceManagement.md)
- [Inventory Management of farms and enclosures](KeyCapabilities/InventoryManagement.md)
- [Water Quality Management](KeyCapabilities/WaterQuality.md)
- [Weather Monitoring](KeyCapabilities/WeatherMonitoring.md)
- [Fish Health Tracking](KeyCapabilities/FishStatistics.md)
- [Harvest Management](KeyCapabilities/Harvest.md)
- [Alert System](KeyCapabilities/AlertSystem.md)

Overall Component diagram is available at:

## Approach and Architecture
This system is based on [Multi-tenant SAS model](ADRs/SingleTenantvsMultiTenant.md). Every customer is treated as a separate tenant and a unique tenantid is available throughout the system. Since, customers are geographically distributed, solution will be deployed in 


