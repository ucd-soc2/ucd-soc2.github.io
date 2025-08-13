---
title: "SmartIntent: Smart Home Control System"
date: 2025-08-13
draft: false
description: "a description"
tags: ["example", "tag"]
---

SmartIntent is a modular smart home automation platform designed with a microservices architecture. It enables seamless control of various home devices through a web interface and voice commands, supporting automation rules and real-time updates.

{{< github repo="ucd-soc2/smartintent" showThumbnail=true >}}

## System Overview

The system consists of independent backend services for each device (such as air conditioners, TVs, lights, and sensors), middleware for business logic and integration, and a Vue.js-based frontend. Voice control is powered by Python and machine learning models for natural language understanding.

## Key Features

- **Device Microservices**: Each device (AC, TV, lights, etc.) runs as a separate Node.js service, exposing REST APIs for control and status.
- **Middleware**: Includes rule engine (automation), intent service (voice command processing), proxy (API gateway), and aggregator (status collection).
- **Frontend**: Responsive web UI with real-time device status, control panels, and voice command integration.
- **Voice Interface**: Real-time speech recognition and intent extraction using Python and ML.
- **Automation**: Define rules to automate device actions based on sensor readings.

## Getting Started

1. **Install prerequisites**: Node.js, Python, Redis, MongoDB.
2. **Clone the repo** and start Redis/MongoDB (Docker recommended).
3. **Install dependencies** for each service and start them individually.
4. **Run the frontend** and access the control panel via browser.
5. **Test device control, voice commands, and automation rules.**

## API Highlights

- Consistent REST endpoints for device control and status.
- Voice commands sent to the intent service for processing.
- Automation rules managed via dedicated endpoints.

## Usage Examples

- Control devices via web UI or API.
- Use English or Chinese voice commands for hands-free operation.
- Set up automation rules (e.g., turn on AC if temperature exceeds threshold).

## Configuration & Troubleshooting

- Environment variables for service URLs and ports.
- Debug logging available for diagnostics.
- Common issues include connection errors and service startup problems.

## Note

SmartIntent is a research prototype accompanying an academic paper (TBA). It is not intended for production use.
