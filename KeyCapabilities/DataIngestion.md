## Overview
This module aims to ingest data coming from sensor devices and camera.
## Assumptions
- Sensor devices are registered with system and have unique ids. There ids are stored in inventory database. Association between devices and farms/enclosures is stored in inventory database. 
- Devices are well powered, have cellular connectivity and are able to send data to backend system.
- Devices are programmed with IP/FQDN where data needs to be sent. 
- Cameras have object recognition capability including fish and parasites on fish.
- Object recognitions models used in cameras are pre-trained. 
## Considerations
- Handle the case if devices do not have good connectivity.
