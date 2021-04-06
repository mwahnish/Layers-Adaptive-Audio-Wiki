---
typora-root-url:../
---

## About
Variables are how data is passed around a Sound Graph. There are two types of events, named Sound Graph variables, and anonymous variables. Sound Graph variables are defined in the [Graph Input](Graph-Inputs) node, can be written to using a [Write](Write) node, read using a [Variable](Variable) node, and used externally if the variable is exposed.

![Named VS Anonymous Variables](IMG/NamedVSAnonymousVariables.png)

Many nodes use and produce anonymous variables as inputs and outputs. See the [Nodes](Nodes) documentation to learn more. Of particular note is the [Variable](Variable) node, which can both read named Sound Graph variables, or output a constant anonymous variable.
