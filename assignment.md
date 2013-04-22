# <!--- LANGUAGE NAME (optional) -->: Language Design Document

**Authored by <!--- YOUR NAME -->**

## Goals and Objectives

* What problem/needs are you trying to solve?
* What tasks would be made easier using your language?
* Do solutions exist already?
* Are you designing a general purpose language or a domain-specific language?
* Where do you see your language being used and by who?

## Core Paradigms and Programming Model

* Some possible paradigms and considerations (not mutually exclusive, and
    non-exhaustive)
    * Object-oriented
        * Inheritance model: classical vs prototypal, multiple inheritance,
        * Polymorphism, multiple dispatch
        * Encapsulation and protection
        * Handling primitives
        * Generics/templating
    * Functional
        * Purely functional or impure?
        * How do you deal with side effects and state
        * Handling anonymous functions and function references
        * Special forms such as functors or monads
        * Dealing with deep recursion and stack overflows
        * Dealing with mutual recursion
        * Function overloading and/or polymorphism
    * Imperative
        * Defining and navigating through procedures
        * What additional control structures are necessary?
    * Declarative
        * General approach/algorithm for handling control flow
        * How to define relations and entities
        * Use of logic or constraints
    * Event-driven
        * How events are handled (triggering and registering)
        * Synchronization when reacting to events
    * Data-flow/Reactive
        * How do you listen and track dataflow changes
    * Pipes and filters
        * What unifying data structure would be used?
        * What protocols for communication would need to be established?
    * Automata/State-machine based

## Type System

* Static typing vs dynamic typing
    * Execution speed
    * Safety and exception handling
    * Tooling (e.g. IDEs, linters, etc.) support
* Strong vs weak typing
    * Flexibility vs safety
    * Type coercion
* Type inference
    * Is it even always possible?
* Polymorphism derived from...
    * Duck typing
    * Structural typing
* Is there a unified type system with a clear bottom and/or top type?
* Native primitives that may be useful/fundamental

## Core Control and Data Structures

* Scoping rules
    * Block scope vs function scope
    * Implications on closures
* Control Structures
    * Looping structures
    * Branching
    * Recursive calls
    * Premature exiting
    * Eager vs lazy evaluation
    * Generators and list comprehensions
    * Continuations and coroutines
* Data structures
    * Lists and collections
    * Messages
    * Events
    * Structures/records
    * Data storage: JSON, XML, etc.

## Memory Model

* Mutable vs immutable data
    * Varying levels of (im)mutability
* Garbage collected or manual memory management
    * Performance vs convenience
    * Varying levels of GC
* Shared memory model
    * Sharing data
    * Security/protection from other contexts
    * Dealing with distributed nodes
    * Built-in vs user-defined synchronization
    * Volatility and external 

## Implementation and Portability

* Compiled vs interpreted
* Target machine language
    * Native bytecode
    * Virtual machine
        * Working off JVM vs custom VM
    * Embedded applications
* Dependencies and interoperability with other languages
* Interfacing with IO devices

## Concurrency

## Reliability and Robustness

## Metaprogramming

## Tooling and Language Support

## Other Unique Features

## Conclusion

* Overview of features
* Differentiating characteristics or features
* Practical uses

## Code Examples and Syntax

```
# Include some code examples here...
# You can also do inline examples above if it helps to explain...
```
