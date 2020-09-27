## About
When all input events in the In list are triggered, the Out event is triggered

## Inputs
Input | Type | Description
------------ | ------|-------
In | List of Events | The list of events to wait for. Once all of these events are triggered, the Out event is triggered
Reset | Event | If this node is waiting for events to be triggered, triggering this event will reset that wait. Out will not be triggered

## Outputs
Output | Type| Description
------------ | -------|------
Out | Event | This event is triggered when all incoming events are triggered

[<- Back to nodes list](Nodes)
