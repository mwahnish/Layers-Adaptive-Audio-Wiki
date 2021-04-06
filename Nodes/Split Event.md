---
typora-root-url:../
---

# Split Event Node

## About

This node receives an event and splits it into an output event, MIDI Data, and Parameters

## Inputs
Input | Type | Description
------------ | ------|-------
Input | Event | The incoming event


## Outputs
Output | Type| Description
------------ | -------|------
Output | Event | The incoming event, minus its MIDI data and parameters
MIDI Data | MIDI Data | MIDI Data received in the input event
Parameters | Varies | Parameters on the incoming event will be listed as outputs in this Node

[<- Back to nodes list](Nodes)
