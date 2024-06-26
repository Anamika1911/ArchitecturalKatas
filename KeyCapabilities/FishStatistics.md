# Overview
This module aims at processing information captured from cameras in enclosures.

## Assumptions
- Cameras have object recognition techniques and they are able to identify individual fish, its species, fish movement and parasites.
- Devices have sufficient power supply.

## Attributes Captured by Camera
- Images in Jpeg/PNG/TIFF
- Metadata including cameraId, GPS co-ordinates
- Annotations specifying bounded boxes for images, keypoints indicating parasites on image and class, confidence level
  
## Block Diagram
![Block diagram - FishStatistics (4)](https://github.com/Anamika1911/ArchitecturalKatas/assets/6397314/62608914-2ade-4761-afee-5b7e54371c78)



## Architecture
- Data from MQTT broker will be streamed to Kafka after some pre-processing.
- Datalake will store data from every tenant in its space based on tenant Id.
- TenantId will be available to every service via some registry of tenants.
- It will be made sure that tenants should not be able to access each other's data.
- FishStatistics alert service will process data from kafka in real time and is horizontal scaled.
  - It will work on huge volumes of incoming data for processing. We will use apache flink to work on incoming data to find anything that does not fit into thrashold set for different incoming images.
  - If keypoints are varying, algorithms will generate an alert for same.
  - Incoming data will be windowed based on configurable Window interval.
  - Data will be filtered for low confidence points.
  - For any considerable change in movement and number of bounded boxes, alert will be generated.
- ImageProcessingService will consume data from datalake in batches, pre-process, train model using CNN. Data will be manually modified for images marked with low confidence.  
- MicroService Architecture
- Event based Architecture for alerts
## Security
- When data is written to the data lake, it is automatically encrypted before being persisted to disk. This encryption is transparent to users and applications accessing the data lake.
- Proper authentication and authorization
