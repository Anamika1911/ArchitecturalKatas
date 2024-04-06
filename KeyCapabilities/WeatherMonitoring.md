# Overview
This module aims to monitor weather conditions in particular region and alert customers accordingly

## Context
Customers will be geographically distributed. They need to be alerted for any unwelcoming weather conditions in the region where farms are located so that appropriate action can be taken accordingly. We will use readily available weather management system to udnerstand 
- Current weather conditions
- Predictions
- Change in weather conditions
  and many more

## Data Captured
-  temperature
-  humidity
-  wind speed
-  Visibility
-  Weather alerts
Customers will be able to set normal behaviour for particular region. Although, we will set normal conditions based on data available from WeatherApi.com. If there are any deviations from normal behaviour or we get any alerts from weatherAPI, alerts will be issued to Customers accordingly.

## Trend analysis
We will use existing weather monitoring system to find anomalies and will not invest time in creating new one from scratch. 

## Block Diagram
![Block diagram - WeatherMonitoring (2)](https://github.com/Anamika1911/ArchitecturalKatas/assets/6397314/af5c2ab1-dd05-4f10-966e-41d40bce1052)

