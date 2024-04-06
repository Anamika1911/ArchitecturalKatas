# Overview
This module will take care of InventoryManagement which manages-
- FarmCollection
- Farm
- Enclosures in Farm

## Context
Customers should be able to manage their farms collection and enclosures in each farm. Farms and enclosures will have to be created manually for each tenant. 

## Assumptions
1. When farms are enclosure are configured, some unique identity will be geneated. This identifier can be physically assign/configrued in Water Monitoring sensors and Camera. It will help in farms/enclosures/device mapping.

## Block Diagram
![Block diagram - InventoryManagement](https://github.com/Anamika1911/ArchitecturalKatas/assets/6397314/3d576144-88d7-4350-bf46-f85f98173550)

## Architecture 
- Tenant, FarmCollection and Farm registration will be simple UI driven Steps, which will create entries in datalake.
- Once Enclosures are set up in field along with Water Monitoring sensors and Camera, Operator will upload this data in system under Farm to which they belong. This way we know association between Enclosures and Devices to Farm.
- Once a new Enclosure/Device is added in field, Operator will upload this detail under farm.

## Security
- TLS
- Authentication/Authorization









	


