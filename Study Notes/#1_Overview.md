# 01 – Overview

## What is Ruckus?

Ruckus Networks is a WiFi equipment vendor that provides enterprise-grade wireless networking solutions, including:
- Access Points (APs) for indoor/outdoor WiFi coverage
- Controllers for centralized management of APs
Ruckus is commonly used in universities, hospitals, and anywhere high density WiFi is required.

## What is a WiFi Controller?

A WiFi controller is a central system that:
- Manages all connected access points from one interface
- Handles: Resource management, firmware updates, load balancing, security policies
- Collects **telemetry**: power usage, user count, signal strength, and more

It basically makes monitoring a large scale WiFi system much easier. Our interest for this particular project is on how these controllers collect telemetry.

## Ruckus Controller Types

Ruckus offers multiple controller options:
- SmartZone (vSZ): Virtualized controller for large-scale or cloud deployments
- ZoneDirector: On-prem controller for small/medium networks
- Unleashed: Controller-free setup where one AP acts as a master

This project will focus on **SmartZone (vSZ)** and CLI/API access for data crawling.



Understanding how Ruckus APs are managed and monitored is essential for simulating AP states and performance.
By successfully simulating AP states, we can obtain the crawling network metrics, and recreate AP behaviours in a digital model

