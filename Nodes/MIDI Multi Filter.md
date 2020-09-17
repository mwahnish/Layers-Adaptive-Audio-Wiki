## About
This node provides a simple way to break out an incoming event by its MIDI note number

## Inputs
Input | Type | Description
------------ | ------|-------
Input | Event | The incoming event

## Outputs
Output | Type| Description
------------ | -------|------
Note name | Event | The outgoing event for the given note. The number of these events vary depending on the Start Note and End Note parameters. When an incoming event arrives on Input, if its MIDI note number matches this output this event will be triggered

## Options
Option | Type | Description
Start Note | Integer | The first note in the range of notes this node will display an event for
End Note | Integer | The last note in the range of notes this node will display an event for

[<- Back to nodes list](Nodes)
