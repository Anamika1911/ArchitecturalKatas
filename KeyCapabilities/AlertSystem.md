# Overview
This module aims at collecting alerts from message broker and sending it to customer. Customer will be able to customize alerts.

## Context
In farming industry or any other industry, it is vital that customers are alerted for any unforeseen conditions so that corrective actions can be taken in time. This is a modular event driven design that will consume alert messages from broker and send to customers on real time basis.

## Notification Channels
- Email
- SMS
- phone call
- mobile app notifications
- Slack messages
- PagerDuty
- Showing on UI dashboards
These channels can be defined from UI.

## Alert Severity Levels
Alert security levels can be defined from UI. Various levels can be:
- Critical 
- Informational
- High
- Warning

## Escalation Policies
Escalation policies needs to be defined so that alerts are addressed promptly. We will
- Define escalation paths
- Contact persons or teams responsible for handling alerts
- Timeframes for acknowledging and resolving alerts. This will help prevent alert fatigue and ensures timely response to critical issues.

## Block Diagram
![Block diagram - Alerting Module](https://github.com/Anamika1911/ArchitecturalKatas/assets/6397314/452c9c93-9a4b-44b4-972a-74024c32d238)

## Architecture
- Event Driven
- MicroServices
## Non-functional Considerations
- Fault tolerant
- Scalability
- Security: All the communicatio is over TLS with proper authentication/authorization in place. 
