# FishWatch
This application aims to automate fish farming management. There are a lots of aspects that needs to be taken care of in this regard. Current application takes care of following aspects:
- [Automatic management of sensor devices and cameras](KeyCapabilities/DeviceManagement.md)
- [Inventory Management of farms and enclosures](KeyCapabilities/InventoryManagement.md)
- [Water Quality Management](KeyCapabilities/WaterQuality.md)
- [Weather Monitoring](KeyCapabilities/WeatherMonitoring.md)
- [Fish Health Tracking](KeyCapabilities/FishStatistics.md)
- [Harvest Management](KeyCapabilities/Harvest.md)
- [Alert System](KeyCapabilities/AlertSystem.md)
- [Reporting](KeyCapabilities/Reporting.md)

Overall Component diagram is available at:

## Approach and Architecture
This system is based on [Multi-tenant SAS model](ADRs/SingleTenantvsMultiTenant.md). 
- Every customer is treated as a separate tenant and a unique tenantid is available throughout the system.
- Since, customers are geographically distributed, solution will be deployed in regions closer to farm. Multiple availability zones will be used in a region for failover and availability. Deployment diagram is available at:
- Thirdparty weather monitoring APIs will be used to monitor and predict weather conditions. Accordingly, alerts will be generated.
- Association between devices and enclosures/farms will be either manually entered or devices can be programmed to send specific enclosure/farm Ids in header.
- To accomodate low bandwidth areas, compression and packeting features will be used to send data from sensor devices to brokers.
- To process data in real time for alerts etc., ApacheSpark is used (even if it not explicitely mentioned in all diagrams in interest of time).
- For reporting, matplotlib/plotly is deployed which can easily process big data from datalake.
  


