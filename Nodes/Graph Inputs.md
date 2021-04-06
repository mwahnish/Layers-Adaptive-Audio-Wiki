---
typora-root-url:../
---

## About
This node contains the named variables and events for the entire graph. This node is required in all sound graphs, cannot be deleted, and there can only be one per graph. 

## Variables
The Variables list contains all of the named variables for this sound graph. Variables can be referenced across the graph using the Variable node, or by referencing the variable's value directly from the graph input node. Variables that are not exposed externally or exposed as inputs can be written to using the Write node. Variables can also be exposed out so they can be referenced externally by Sound Graph Player components or Sound Graph Pools, or by Subgraph nodes if this graph is being used as a subgraph. Each variable has the following options:

* Name - The name of the variable. This name must be unique for the graph.
* Type - The type of this variable. The following types are available:
    * Array
    * Audio Clip
    * Audio Mixer
    * Audio Mixer Group
    * Boolean
    * Number (Double)
    * Number (Float)
    * Number (Integer)
    * MIDI File
    * String
    * Transform
    * Vector 3
* Exposure - A variable can be not exposed externally, exposed as an input, or exposed as an output. These options govern how the variable can be read and written to:
    * Do Not Expose - The variable cannot be read or written to externally. The variable can be read or written to within the graph.
    * As Input - The variable can be read and written to externally. The variable can be read within the graph, but cannot be written to.
    * As Output - The variable can be read externally, but cannot be written to. The variable can be read and written to within the graph.
* Default Value - The default value this variable contains. This default value may be overrode by the Sound Graph Player or Sound Graph Pool running the sound graph.

## Events
The Events list contains all of the named variables for this sound graph. Events can triggered using the Trigger Event node, or listened for using the Event node or connecting directly to them in the Graph Input node. They can also be triggered manually by pressing the event's "Trigger" button. Events can be exposed externally in Sound Graph Player components, Sound Graph Pools, and Subgraph nodes if the graph is being used as a subgraph, or made internal to the graph. Events can carry arbitrary parameters and MIDI information, like the note number, channel number, and velocity. Each event has the following options:

* Name - The name of the event. This name must be unique for the graph.
* Expose - Set this checkbox to true if this event can be referenced externally to this graph. Otherwise, it will only be accessible within this graph.
* Parameters - This is a list of parameters that must be included when triggering this event. These parameters may be used by nodes that are triggered by this event. Each parameter has the following options:
    * Name - The name of the parameter. This name must be unique within the event
    * Type - The type of this parameter. The following types are available
        * Array
        * Audio Clip
        * Audio Mixer
        * Audio Mixer Group
        * Boolean
        * Number (Double)
        * Number (Float)
        * Number (Integer)
        * MIDI File
        * String
        * Transform
        * Vector 3
        

In addition to user-defined events, this node exposes one pre-defined event, Update. Update is triggered every frame.

## Pooling sound graphs
See sound graph pools for details

[<- Back to nodes list](Nodes)
