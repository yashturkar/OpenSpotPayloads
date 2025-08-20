# Networking Overview

This document describes the networking setup for **OpenSpotPayloads**.  
It covers how Spot, the Jetson, sensors, and the operator’s Steam Deck are connected through the payload electronics and wireless bridge.

---
## System Layout

![Payload Networking Diagram](../media/Spot-Setup.png)

- **Spot**  
  - GXP port provides power + network.  
  - Example IPs:  
    - `192.168.50.3` (GXP)  
    - `192.168.80.3` ("SpotSpot")  
    - `10.0.0.3` (Management)  

- **Payload Switch (2.5G)**  
  - Connects Spot, Jetson Orin, Ouster OS-0 sensor, and Ubiquiti Bullet (via PoE injector).  

- **Jetson Orin**  
  - Example IP: `192.168.50.5`.  

- **Ouster OS-0 Lidar**  
  - Example IP: `192.168.50.XXX`.  

- **Wireless Bridge**  
  - Pair of Ubiquiti Bullets with passive PoE.  
  - Extends payload network to the operator side.  

- **Operator Side**  
  - Router + AP (`192.168.50.1`, SSID: `spotfi-5`).  
  - Steam Deck connects via Wi-Fi (`192.168.50.XXX`).  
  - Powered from external power station (e.g., Jackery).  

---

## Notes
- **Passive PoE** injectors are required for Ubiquiti Bullets.  
- **Color coding in diagram**:  
  - Blue = Network  
  - Red = Power  
  - Red dotted = Passive PoE  
---
More details on the networking setup will be provided in the upcoming documentation.