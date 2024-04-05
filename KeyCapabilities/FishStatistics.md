# Overview
This module aims at processing information captured from cameras in enclosures.

## Assumptions
- Cameras have object recognition techniques and they are able to identify individual fish, its species, fish movement and parasites.
- Devices have sufficient power supply.

## Attributes Captured by Camera
- Images in Jpeg/PNG/TIFF
- Metadata including cameraId, GPS co-ordinates
- Annotations specifying bounded boxes for images, keypoints indicating parasites on image and class
  
## Block Diagram
![Block diagram - FishStatistics (1)](https://github.com/Anamika1911/ArchitecturalKatas/assets/6397314/f12fcb97-2e98-459b-9dda-b8c05f11c4c3)

## Architecture
MicroService Architecture
Event based Architecture for alerts
