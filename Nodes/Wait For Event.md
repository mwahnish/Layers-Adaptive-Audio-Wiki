## About
When the Start input is triggered, this node waits until the the given event has also been triggered. Once this has occurred, the End output is triggered

## Inputs
Input | Type | Description
------------ | ------|-------
Start | Event | Once this event is triggered, the node begins waiting for the given event to be triggered
Unlabled | Event | When this node is triggered, it waits for this event to be triggered. Once this occurs, the End output is triggered

## Outputs
Output | Type| Description
------------ | -------|------
End | Event | This event is triggered once the Start event is triggered, and then the given event has also been triggered

[<- Back to nodes list](Nodes)
