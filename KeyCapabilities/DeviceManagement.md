# Overview
This module aims at managing different sensor devices and cameras installed in different enclosures. 

## Context 
With a lot of devices, it is imperative that there should be a strong device monitoring and alerting mechanism in place. Using LwM2M protocol, we will achieve following:
- Monitor devices
- Upgrade firmware
- Report if any device is not responding
- Generate alerts for misfunctioning devices

## Assumptions
- User will first create farms and enclosures via UI and that enclosure ID will be fed into sensor device. Sensor device is capable of sending this information in header. This assumption will help to identify/correlate farms/enclosures with respective devices. 

## Block Diagram 
![Block diagram - Device Management (2)](https://github.com/Anamika1911/ArchitecturalKatas/assets/6397314/4ddc5e32-d880-4194-bc85-598f93461ea1)


## Architecture
- Health data coming from sensor devices and cameras will be sent to apache kafka for real time processing.
- DeviceManagementAPI will interact with BFF to show device related data on UI.
- DeviceHealthAlertSystem will consume data from kafka and generate alerts if device needs attention. It will use [AlertSystem](KeyCapabilities/AlertSystem.md) to send alerts.
- To update object recognition models in camera, we can use lwM2M to send firmware upgrades to camera. For any compatibility issues, LwM2M supports rollback.
- 
## Non-functional Requirements 
- Solution is horizontally scalable.
- Security
  - Transport Layer Security (TLS): LwM2M typically relies on TLS for secure communication between devices and servers. TLS provides encryption, data integrity, and authentication, ensuring that data exchanged between devices and servers remains confidential and tamper-proof.

  - Certificate-Based Authentication: In addition to PSK, LwM2M supports certificate-based authentication. Devices and servers can use X.509 certificates to authenticate each other during the TLS handshake. This method provides stronger authentication and enables more robust identity verification.

  - DTLS (Datagram Transport Layer Security): LwM2M can also use DTLS for secure communication in UDP-based scenarios. DTLS is similar to TLS but is designed for datagram-based communication, making it suitable for UDP, which is often used in IoT deployments.

  - Authorization: Authorization in LwM2M typically involves controlling access to resources on both devices and servers. This can be implemented through access control policies defined by the LwM2M Server. These policies specify which devices or users are allowed to perform specific operations on resources, such as read, write, execute, or delete.
 
  - Client Registration: Before a device can communicate with an LwM2M server, it typically needs to register itself with the server. During the registration process, authentication and authorization mechanisms are employed to ensure that only authorized devices can connect to the server and access its resources.
