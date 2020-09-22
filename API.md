# About
The primary way of interacting with Layers via code are through the generated Player Component API's. In short, player components are responsible for executing Sound Graphs in a scene. There are two kinds, Sound Graph Player Components and Pooled Sound Graph Player Components. The difference between the two is Pooled Sound Graph Player Components share instances of the Sound Graph to save resources, while each Sound Graph Player Component is backed by it's own copy of its Sound Graph Asset. See [here](Sound-Graph-Playback) for more information on the different kinds of Player Components.

Each Sound Graph has a custom Player Component generated for it. This means that each Sound Graph's events and variables are accessible directly through code. This also means that code that incorrectly references a Sound Graph (for example, referencing an event that has since been renamed) can be identified at compile time, rather than as a runtime bug. Below are the API references for the two kinds of Player Components.

# Sound Graph Player Component API
## public enum Events
This enum contains the names of all the exposed events in the Sound Graph for this player

## public void RegisterEventListener( Events targetEvent, UnityAction<double, Dictionary<string, object>, MidiFlowInfo> onEventCalled )
This function allows the user to register a listener for the event identified by the targetEvent parameter

Parameter Name | Type | Description
------------ | -------|------
targetEvent | Events | The event to register a listener to
onEventCalled | UnityAction<double, Dictionary<string, object>, MidiFlowInfo> | The function to call when the event identified by targetEvent is triggered. Note that the function should take in three values - A Double representing the time the event is called, a Dictionary<string,Object> representing the values of the event's parameters (the string is the event name, and the Object is the value), and MidiFlowInfo, which contains any MIDI data contained in the event. Note that in most circumstances, functions called here are called *before* the event's scheduled time. Use the time parameter to precisely schedule any actions based on an event.

## public void UnRegisterEventListener( Events targetEvent, UnityAction<double, Dictionary<string, object>, MidiFlowInfo> onEventCalled )
This function allows the user to unregister a listener from the event identified by the targetEvent parameter

Parameter Name | Type | Description
------------ | -------|------
targetEvent | Events | The event to remove onEventCalled from
onEventCalled | UnityAction<double, Dictionary<string, object>, MidiFlowInfo> | The function to call when the event identified by targetEvent is triggered. Note that the function should take in three values - A Double representing the time the event is called, a Dictionary<string,Object> representing the values of the event's parameters (the string is the event name, and the Object is the value), and MidiFlowInfo, which contains any MIDI data contained in the event. Note that in most circumstances, functions called here are called *before* the event's scheduled time. Use the time parameter to precisely schedule any actions based on an event.

## public VariableType InputVariableName {set;}
All graph variables that are set to As Input are available as a property with a setter, where VariableType is the type of the variable in the Sound Graph, and InputVariableName is the name.

## public VariableType OutputVariableName {get;}
All graph variables that are set to As Output are available as a property with a getter, where VariableType is the type of the variable in the Sound Graph, and OutputVariableName is the name.


## public void EventName( )
When this method is called, the exposed event sharing a name with this method is triggered. The event will be triggered immediately. If the event has parameters, they will be additional parameters to this method.

## public void EventName( MidiFlowInfo midiData )
When this method is called, the exposed event sharing a name with this method is triggered. The event will be triggered immediately

Parameter Name | Type | Description
------------ | -------|------
midiData | MidiFlowInfo | Contains any MIDI data to be sent with the event

If the event has parameters, they will be additional parameters to this method.

## public void EventName( Double startTime )
When this method is called, the exposed event sharing a name with this method is triggered. The event will be scheduled to trigger at the given [DSP Time](https://docs.unity3d.com/ScriptReference/AudioSettings-dspTime.html)

Parameter Name | Type | Description
------------ | -------|------
startTime | Double | The [DSP Time](https://docs.unity3d.com/ScriptReference/AudioSettings-dspTime.html) to schedule the event for

If the event has parameters, they will be additional parameters to this method.

## public void EventName( Double startTime, MidiFlowInfo midiData )
When this method is called, the exposed event sharing a name with this method is triggered.

Parameter Name | Type | Description
------------ | -------|------
startTime | Double | The [DSP Time](https://docs.unity3d.com/ScriptReference/AudioSettings-dspTime.html) to schedule the event for
midiData | MidiFlowInfo | Contains any MIDI data to be sent with the event

If the event has parameters, they will be additional parameters to this method.

## public void StopAll( )
When called, this method stops all playback on player immediately

## public void StopAll( Double time )
When called, this method stops all playback on the player at the given [DSP Time](https://docs.unity3d.com/ScriptReference/AudioSettings-dspTime.html)
Parameter Name | Type | Description
------------ | -------|------
time | Double | The [DSP Time](https://docs.unity3d.com/ScriptReference/AudioSettings-dspTime.html) to schedule the stopping all playback

# Pooled Sound Graph Component API
## public SoundGraphPlayerType Checkout( )
This method checks out a Sound Graph Player of type SoundGraphPlayerType from the pool. Once checked out, it may be used like any other Sound Graph Player (see the documentation above).

## public void Checkin( SoundGraphPlayerType player )
This method returns a checked out Sound Graph Player. Once it has been returned, it will be reset and reused by other Pooled Sound Graph Components. Do not try to access a returned Sound Graph Player

# Add Component Support
Note that adding players to a gameobject via GameObject.AddComponent() is not currently supported, but is coming soon. For now, make your players are added to Game Objects at start, either in the scene or in a prefab.
