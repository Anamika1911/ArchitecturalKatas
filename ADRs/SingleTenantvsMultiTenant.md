# Single Tenant vs Multi Tenant
## Status
Accepted
## Context and Problem Statement
Should we develop FishWatch as single tenant system or multi tenant system?
## Requirements
The FishWatch system should be able to serve customers of varying sizes spread across geography. 
## Business Assumptions
If customers want to access solution from varying locations across geography, they will be willing to accept SAS based solution.
## Decision drivers
Since, IOT devices will generate huge amount of data and that needs to be processed using machine learning algorithms, so solution will be provided as SAS based solution. FishWatch will be used by customers of varying sizes, so, we need to charge them for their usage. Smaller customers should be charged less and larger customers more. With single tenant system, it will become very difficult to manage cost. 
## Considered options

## Decision
Multi-Tenant system

