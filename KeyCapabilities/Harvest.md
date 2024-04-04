# Overview
This module aims at keeping track of harvesting information of fish.
## Assumptions

## Context
To determine automatically, when a fish has been harvested from enclosures, information sent from cameras will be used. If on some days, there is a drastic decrease in number of fish, we can assume fish has been harvested. Same information will be captured in database. User will be prompted on UI to confirm this assumption. If there were any other reasons for removal of fish from enclosures, Customers can specify reason for same. This information about harvest will be used to determine best harvest time depending on different parameters like:
- Species
- Region
- Date of breeding
- Weather conditions

Datalake will already have all this information available. Special machine learning algorithms will be employed to understand best time to harvest the fish and accordingly user will be alerted for same. 
## Block Diagram
![Block diagram - Harvesting](https://github.com/Anamika1911/ArchitecturalKatas/assets/6397314/77e0b00e-9f28-4059-8c29-34ac637e5f54)
