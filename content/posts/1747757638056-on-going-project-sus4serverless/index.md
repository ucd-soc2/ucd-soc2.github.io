---
title: "Ongoing Project: Sustainable Serverless Computing"
date: 2025-05-20
draft: false
description: "Sustainable Serverless Computing: A Research Initiative"
tags: ["sustainable", "serverless", "computing", "energy efficiency", "carbon footprint"]
authors:
  - "haditabatabaee"
showAuthor: false
---

In this ongoing project, we're exploring methods to optimize serverless computing platforms for energy efficiency and sustainability. Our goal is to reduce the carbon footprint of cloud functions while maintaining performance.

## Project Objectives

- Measure energy consumption of serverless functions across providers
- Develop optimization techniques for reducing resource usage
- Create frameworks for carbon-aware function scheduling
- Provide developers with tools to monitor and improve sustainability

## Preliminary Results

We've collected data from multiple cloud providers and analyzed the energy profiles of various function types:

| Function Type | AWS Lambda (W·h) | Azure Functions (W·h) | Google Cloud Functions (W·h) |
|---------------|------------------|----------------------|------------------------------|
| REST API      | 0.042            | 0.039                | 0.045                        |
| Data Processing| 0.087           | 0.092                | 0.081                        |
| ML Inference  | 0.156            | 0.148                | 0.152                        |
| File Operations| 0.063           | 0.058                | 0.061                        |

## Carbon-Aware Deployment Strategy

We've developed a prototype scheduler that routes function executions to regions with the lowest carbon intensity:

```python
def deploy_function(function_code, requirements):
    regions = get_available_regions()
    carbon_intensities = fetch_carbon_intensity(regions)
    
    # Sort regions by carbon intensity (lowest first)
    green_regions = sorted(regions, key=lambda r: carbon_intensities[r])
    
    # Deploy to the greenest region with capacity
    for region in green_regions:
        if check_capacity(region, requirements):
            return deploy_to_region(function_code, region)
    
    # Fallback to default region if needed
    return deploy_to_region(function_code, DEFAULT_REGION)
```

## Next Steps

1. Expand our dataset to include more function types and workloads
2. Develop a plugin for popular serverless frameworks
3. Create developer guidelines for writing energy-efficient functions
4. Partner with cloud providers to implement carbon-aware scheduling

We welcome collaborators interested in sustainable computing! Reach out if you'd like to contribute to this research.