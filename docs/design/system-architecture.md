# System Architecture

This document describes the overall system architecture of the **Avalanche Response Drone Station**.

## High-Level Components

- Avalanche detection subsystem  
- Autonomous drone hangar  
- UAV platform (multirotor)  
- RF search module (457 kHz)  
- Onboard processing & autonomy  
- Cloud / backend services  
- Rescuer user interface (app / web)

## Data Flow Overview

1. Avalanche sensors detect a potential avalanche event  
2. Sensor fusion module validates the event and triggers drone launch  
3. Hangar opens and arms the UAV, then initiates take-off  
4. UAV executes initial search pattern and activates RF receiver  
5. RF localization narrows down the victim area  
6. Estimated victim location is sent to cloud backend  
7. Rescue teams receive coordinates, heatmaps and status updates

## Interfaces Between Subsystems

- **Detection → Hangar**: digital trigger + confidence level  
- **Hangar → UAV**: launch command, health status, battery status  
- **UAV → RF module**: orientation, position, timing  
- **RF module → Autonomy**: signal strength & gradient  
- **UAV → Cloud**: telemetry, RF data, mission state  
- **Cloud → Rescuer**: map view, notifications, export

## Open Design Questions / TODO

- Exact communication protocol between hangar and UAV (wired / wireless)  
- Bandwidth and latency requirements for cloud connection  
- Redundancy and fail-safe behaviour in case of communication loss  
- How many stations/drones per mountain area for coverage

