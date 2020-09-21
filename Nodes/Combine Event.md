## About
This node receives an event and produces an output event with appended MIDI Data and Parameters

## Inputs
Input | Type | Description
------------ | ------|-------
Input | Event | The incoming event
MIDI Data | MIDI Data | MIDI Data received on this input will be appended to any incoming event on Input
Parameters | List of Parameters | The parameter data to be appended to any incoming events on Input. Each parameter has a name, which must be unique in the parameters list, a type, and a value. 

## Outputs
Output | Type| Description
------------ | -------|------
Output | Event | When an event is sent to Input, an event is triggered on this output with the MIDI Data and Parameters appended.

[<- Back to nodes list](Nodes)
