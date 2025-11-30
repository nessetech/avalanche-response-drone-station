# Avalanche Detection Subsystem

This document covers the design of the avalanche detection module and trigger logic.

## Possible Sensors

- Infrasound microphone  
- Geophone / vibration sensor  
- Pressure sensor / barometric variations  
- Camera (visible / thermal) + ML model  
- Combined IMU-based detection (if hangar experiences shock)

## Detection Logic

1. Raw sensing from multiple channels  
2. Filtering and denoising  
3. Feature extraction (energy, spectrum, waveform characteristics)  
4. Event classification (possible avalanche / not avalanche)  
5. Confidence scoring  
6. Trigger decision with hysteresis / time window

## Requirements (initial)

- Low false positive rate  
- Short detection latency  
- Continuous operation in harsh weather  
- Low power consumption when idle

## TODO

- Choose first sensor set for prototype  
- Define thresholds and detection pipeline  
- Evaluate possibility of using external avalanche warnings as additional input (e.g. API)
