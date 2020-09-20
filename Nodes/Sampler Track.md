## About
This node takes events with MIDI information in, and plays a sample based on that event's note number

## Inputs
Input | Type | Description
------------ | ------|-------
MIDI In | Event | The event triggering sample playback. The sample will be chosen based on the MIDI Note set on the event.
Length | Float or Integer | The repeat length. If the Value input is greater than Length, it loops back around to zero. The type of this input changes according to the Type option

## Outputs
Output | Type| Description
------------ | -------|------
Audio Out | Audio | All audio output from this node flows through this output. Note that this output can be connected directly to an Audio Out, or audio can be "sent" by clicking the dropdown next to this output and selecting a target Audio Out. This function helps unclutter the Sound Graph.

## Options
Option | Type | Description
------------ | -------|------
Keys | List of Samples | The samples for this sample node. Each sample has a MIDI note number and an associated Audio Clip. When an event with the given MIDI note number triggers the MIDI In input, the associated Audio Clip will play. Each item in the samples list has a Listen for Key function to make setup of samples more convenient. When Listen for Key is active, the sample will set it's note number to the next key that is pressed on an attached MIDI device.

## Load Folder Function
This node can load in an entire folder of samples at once for convenience. Click the Load Folder button, pick a folder, and all audio in that folder will be loaded into the sampler. If the names of the clips have the note number in it, the sampler will try to parse them and automatically configure the note number.

[<- Back to nodes list](Nodes)
