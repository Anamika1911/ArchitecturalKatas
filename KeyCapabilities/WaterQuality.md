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

