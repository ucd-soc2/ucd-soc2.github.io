---
title: "Smart Home Command Training Dataset"
date: 2025-08-13
draft: false
description: "A dataset for fine-tuning large language models to understand and respond to smart home commands."
tags: ["llm", "finetuning", "smart home", "dataset"]

---

This dataset is designed for fine-tuning large language models (LLMs) to improve their ability to understand, clarify, and respond to user commands in smart home environments. It contains realistic user instructions, device states, and expected assistant responses, supporting robust model training and evaluation.

[Dataset](https://github.com/ucd-soc2/smartintent/tree/main/data)

### Dataset Structure

The main file, `training.csv`, includes:

- **userInstruction**: User commands in natural language (Chinese).
- **current_state**: JSON strings representing the status of smart home devices, including device IDs, parameters (e.g., volume, humidity, temperature), and on/off status.
- **needsClarification**: Boolean indicating if the command is ambiguous and requires clarification.
- **message**: The assistant's response, such as a clarifying question or confirmation.
- **results**: JSON strings specifying actions to perform on devices, including device IDs, actions (e.g., "turn_on"), and parameters.

### Example Entry

```yaml
userInstruction: 电视声音太大了，吵到邻居了。
current_state: [
    {"deviceId": "LivingRoomTV", "parameters": {"volume": 60}, "status": "on"},
    {"deviceId": "BedroomTV", "parameters": {"volume": 35}, "status": "on"},
    {"deviceId": "KitchenTV", "parameters": {"volume": 25}, "status": "on"}
]
needsClarification: True
message: 您想调整哪个区域的电视音量呢？客厅、卧室还是厨房的电视机？
results: []
```

In this example, the user asks to lower the TV volume, but multiple TVs are present. The assistant detects ambiguity, asks for clarification, and waits for further input before taking action.

### Use Cases

This dataset is ideal for:

- Fine-tuning LLMs to understand smart home commands.
- Training models to interpret device states and parameters.
- Enabling assistants to handle ambiguous instructions with clarifying questions.
- Generating accurate, context-aware responses for smart home scenarios.

Researchers and developers can use this data to enhance smart home assistants' natural language understanding and interactive capabilities.