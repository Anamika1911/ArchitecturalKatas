# Datalake vs NoSql vs Dataware house
## Status
Accepted

## Context and Problem Statement
We need to select a big data storage technology that will support multi-region support, replication and machine learning for varied types of data. 

## Decision drivers
We wanted to rely on a technology that supports varied types of data (structured/non-structured), replication across regions, reporting. Multi-region deployments of NoSQL databases may introduce complexities in data management, synchronization, and conflict resolution, especially in geographically distributed environments. Data warehouses have limitations in handling semi-structured or unstructured data compared to data lakes.

## Considered options
Datalake/Nosql/Dataware house

## Decision
- Use Data lake 
