---
title: "Ongoing Project: Sustainable Serverless Computing"
date: 2025-05-20
draft: false
description: "Sustainable Serverless Computing: A Research Initiative"
tags: ["sustainable", "serverless", "computing", "energy efficiency", "carbon footprint"]
authors:
  - "shaoshuzhu"
showAuthor: false
---

In this ongoing project, we're exploring methods to optimize serverless computing platforms for energy efficiency and sustainability. Our goal is to reduce the carbon footprint of cloud functions while maintaining performance.

## Project Objectives

- Setup a framework to measure energy consumption of serverless functions
- Analyze the carbon footprint of different serverless providers
- Develop optimization techniques for reducing resource usage
- Create frameworks for carbon-aware function scheduling
- Provide developers with tools to monitor and improve sustainability

## Test Bed and Accurate Measurement

To accurately assess energy consumption, we employ CPU frequency-based estimation rather than relying solely on utilization metrics. Utilization-based measurement often fails to capture the true power draw, as CPU utilization does not directly correlate with energy usage—different workloads and processor states can result in varying power consumption even at similar utilization levels.

| Architecture | Device                | Quantity | Measurement Method         |
|--------------|----------------------|----------|---------------------------|
| x64          | Intel-based Machine   | 1        | Shunt Resistor     |
| x64          | AMD-based Machine     | 1        | Shunt Resistor     |
| ARM          | Apple Mac Mini (M4)   | 2        | Shunt Resistor     |
| ARM          | NVIDIA Jetson         | 2        | Shunt Resistor     |
| ARM          | Raspberry Pi 5        | 1        | Shunt Resistor     |

Expect for a more accurate measurement framework, all devices are monitored using shunt resistors to measure current and voltage during function execution, enabling direct calculation of power usage and validation of our estimation models.

## Preliminary Results

We've collected carbon emission data from power grids in various regions and correlated it with serverless function executions. This allows us to estimate the carbon footprint of executing functions in different regions. Our initial findings show significant variations in carbon intensity based on geographic location and time of day.

| Region      | Time        | Carbon Emission per Watt (gCO₂/W) |
|-------------|-------------|-----------------------------------|
| US-East     | 10:00 AM    | 0.45                              |
| EU-West     | 2:00 PM     | 0.32                              |
| Asia-South  | 6:00 PM     | 0.60                              |
| Australia   | 9:00 AM     | 0.28                              |
| South America | 3:00 PM   | 0.52                              |

## Carbon-Aware vs. Standard Scheduler Example

Below is a simplified Python example comparing a standard scheduler with a carbon-aware scheduler for serverless function execution. The carbon-aware scheduler selects the region with the lowest carbon emission at the time of scheduling.

```python
import random

regions = {
  "US-East": 0.45,
  "EU-West": 0.32,
  "Asia-South": 0.60,
  "Australia": 0.28,
  "South America": 0.52
}

def standard_scheduler():
  # Randomly select a region
  return random.choice(list(regions.keys()))

def carbon_aware_scheduler():
  # Select region with lowest carbon emission
  return min(regions, key=regions.get)

print("Standard Scheduler selected:", standard_scheduler())
print("Carbon-Aware Scheduler selected:", carbon_aware_scheduler())
```

The carbon-aware scheduler consistently chooses the region with the lowest carbon emission, demonstrating a simple but effective optimization for sustainability.

## Next Steps

1. Expand our dataset to cover a broader range of serverless function types, workloads, and real-world use cases.
2. Develop and test optimization algorithms for reducing energy consumption in serverless functions.
3. Collaborate with serverless providers to implement carbon-aware scheduling and resource allocation.

We welcome collaborators interested in sustainable computing! Reach out if you'd like to contribute to this research.