This document contains useful CLI commands to interact with Ruckus SmartZone via SSH, intended for simulation, testbed crawling, and digital twin modeling.

## 1. SSH Access Format

To connect to SmartZone controller or AP:
```bash
ssh admin@<ip-address>
```

## 2. Basic System Status
``` get sysinfo  ```
Shows details such as system name, version, model, and up time.

## 3. Access Points
``` get ap-list ```
Lists all detected APs and their status.

## 4. AP Radio Status
```get wlan-radio <ap-name>```
Lists the status of an AP including the channel, power, and bandwidth for its frequencies.

## 5. Traffic
```get traffic-ap <ap-name>```
Lists the current traffic status of an AP, including uplink, downlink, and peak client count.
