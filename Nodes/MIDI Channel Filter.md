---
typora-root-url:../
---

## About
This node filters incoming events by its MIDI channel

## Inputs
Input | Type | Description
------------ | ------|-------
Input | Event | The incoming event

## Outputs
Output | Type| Description
------------ | -------|------
Output | Event | The outgoing event, which triggers only if the conditions in the Conditions list are met

## Options
Option | Type | Description
------------ | -------|------
Filter Type | Dropdown | Defines whether the Condition list is inclusive or exclusive. For example, if Filter Type is set to include and Channels 4 and 5 are in the Conditions list, all incoming events in MIDI channel 4 or 5 is forwarded along, and all others are discarded. If Filter Type is set to Exclude, all incoming events NOT in MIDI channel 4 or 5 is forwarded, and those in Channel 4 or 5 are discarded.
Conditions | List | A list of conditions by which incoming events are filtered. Each condition has a selectable channel number.

[<- Back to nodes list](Nodes)
