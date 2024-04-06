# Water Quality Module
## Overview
This module caters to following requirements:
- Getting water quality data from data sensors using MQTT protocol.
- Saving data to datalake for reports and analytics.
- Saving alert thrashold configured on UI.
- Monitor incoming data for any instant alerts to be generated.
- Background services running every minute to check for any thrashold breach for data received in last 1 minute.

## Sensor Parameters
- Temperature: Fish have specific temperature requirements depending on the species. Monitoring temperature ensures that it remains within the optimal range for the species being farmed.
- Dissolved Oxygen (DO): Adequate oxygen levels are crucial for fish respiration. Low DO levels can lead to stress or suffocation.
- pH Level: The pH of water affects the overall health and growth of fish. It's important to maintain pH within the appropriate range for the species.
- Ammonia (NH3/NH4+), Nitrite (NO2-), and Nitrate (NO3-) Levels: Monitoring these nitrogen compounds is essential for preventing ammonia and nitrite toxicity, which can harm fish.
- Turbidity: The clarity of water can affect light penetration and thus photosynthesis in aquatic plants. Excessive turbidity can also indicate sedimentation or pollution issues.

![Block diagram - WaterQuality (2)](https://github.com/Anamika1911/ArchitecturalKatas/assets/6397314/3f49495e-f53f-4740-ac7c-c6c05e46e1d9)

## Architecture
- Data from MQTT broker will be streamed to datalake after some pre-processing.
- Datalake will store data from every tenant in its space based on tenant Id.
- TenantId will be available to every service via some registry of tenants.
- It will be made sure that tenants should not be able to access each other's data.
- WaterQualityAlert service will process data from datalake in real time and is horizontal scaled.
- It will work on huge volumes of incoming data for processing. We will use apache spark to work on incoming data to find anything that does not fit into thrashold set for different incoming images.
- Incoming data will be windowed based on configurable Window interval.
- For any considerable change, alert will be generated.
- MicroService Architecture
- Event based Architecture for alerts
## Security
- When data is written to the data lake, it is automatically encrypted before being persisted to disk. This encryption is transparent to users and applications accessing the data lake.
- Proper authentication and authorization
