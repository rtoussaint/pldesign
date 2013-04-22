# <!--- LANGUAGE NAME (optional) -->: Language Design Document

**Authored by <!--- YOUR NAME -->**

## Goals and Objectives

* What problem/needs are you trying to solve?
* What tasks would be made easier using your language?
* Do [solutions](lang_list) exist already?
* Are you designing a [general purpose][general] language or a [domain-specific][dsl] language?
* Where do you see your language being used and by who?

## Core Paradigms and Programming Model

* Some possible [paradigms][paradigm] and considerations (not mutually exclusive, and
    non-exhaustive)
    * [Object-oriented][OO]
        * Inheritance model: classical vs prototypal, multiple inheritance,
        * Polymorphism, multiple dispatch
        * Encapsulation and protection
        * Handling primitives
        * Generics/templating
    * [Functional][functional]
        * Purely functional or impure?
        * How do you deal with side effects and state
        * Handling anonymous functions and function references
        * Special forms such as functors or monads
        * Dealing with deep recursion and stack overflows
        * Dealing with mutual recursion
        * Function overloading and/or polymorphism
    * [Imperative][imperative]
        * Defining and navigating through procedures
        * What additional control structures are necessary?
    * [Declarative][declarative]
        * General approach/algorithm for handling control flow
        * How to define relations and entities
        * Use of logic or constraints
    * [Event-driven][event]
        * How events are handled (triggering and registering)
        * Synchronization when reacting to events
    * [Data-flow][flow]/[Reactive][reactive]
        * How do you listen and track dataflow changes
    * [Pipes and filters][unix]
        * What unifying data structure would be used?
        * What protocols for communication would need to be established?
    * [Automata/State-machine][automata] based

## Type System

* [Static][static] typing vs [dynamic][] typing
    * Execution speed
    * Safety and exception handling
    * Tooling (e.g. IDEs, linters, etc.) support
* [Strong][strong] vs [weak][] typing
    * Flexibility vs safety
    * Type coercion
* Type [inference][]
    * Is it even always possible?
* [Polymorphism][polymorphism] derived from...
    * Duck typing
    * Structural typing
* Is there a [unified type system][unified] with a clear bottom and/or top type?
* Native [primitives][] that may be useful/fundamental

## Core Control and Data Structures

* [Scoping][scope] rules
    * Block scope vs function scope
    * Implications on closures
* Control Structures
    * Looping structures
    * Branching
    * Recursive calls
    * Premature exiting
    * Pattern matching
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

* Mutable vs [immutable][] data
    * Varying levels of (im)mutability
* [Garbage collected][GC] or manual memory management
    * Performance vs convenience
    * Varying levels of GC
* [Shared memory][shared] model
    * Sharing data
    * Security/protection from other contexts
    * Dealing with distributed nodes
    * Built-in vs user-defined synchronization
    * Volatility and external 

## Implementation and Portability

* [Compiled][compiled] vs [interpreted][]
* Target machine language
    * [Native][native] bytecode
    * [Virtual machine][vm]
        * Working off JVM vs custom VM
    * Embedded applications
* Dependencies and interoperability with other languages
* Interfacing with IO devices

## Concurrency

* [Multi-threading][multithreaded] vs [green threads][greenthreads]
* Alternative [concurrency model][concurrency]
    * Actor model
    * Agent model
* Communication
    * [Inter-process communication][ipc]
    * Message passing between nodes in a [distributed system][distributed]
* How do you deal with [synchronization][synchronization]?

## Reliability and Robustness

* [Exception][exception] and failure handling
    * Explicit control structures/types vs convention
    * Checked vs unchecked exceptions
* Failure free vs expecting failure
    * How do you restore state?
* [Design by contract][DbC] (see [Eiffel][])
* Support for hot-swapping or updating code on the fly
* How might your type system choices affect reliability?

## Metaprogramming

* Ability to extend language
    * [Macro][macro] system
    * Code as data (e.g. Lisp)
* Maintain meta-data for analysis or documentation
    * Annotations
    * Type hinting
    * Type dependencies/relations
* Code introspection and generation
    * [Reflection][reflection]
    * [Decorators][decorators]
    * Runtime code generation facilities (see [JIT][] compilation)

## Code Organization

* Namespaces
* Packages
* Modules
* Libraries and linking
* Separating headers and implementation

## Tooling and Language Support

* Can your language be easily analyzed statically
    * What level of hinting/support might be possible
* Support for debugging and setting up traps
* Any special considerations for using IO devices?

## Other Unique Features

* Whatever you can think of that you think would be useful
* Examples
    * Syntactic sugar (or why not just make your syntax cleaner to begin with)
    * Native RegExp support if your language focuses on text manipulation
    * Code synthesis (e.g. generating getters and setters)

## Conclusion

* Overview of features
* Differentiating characteristics or features
* Practical uses

## Code Examples and Syntax

```
# Include some code examples here...
# You can also do inline examples above if it helps to explain...
```


[lang_list]: http://en.wikipedia.org/wiki/List_of_programming_languages_by_type
[general]: http://en.wikipedia.org/wiki/General-purpose_programming_language#Taxonomies
[dsl]: http://en.wikipedia.org/wiki/Domain-specific_language
[paradigm]: http://en.wikipedia.org/wiki/Programming_paradigm
[OO]: http://en.wikipedia.org/wiki/Object-oriented_programming
[functional]: http://en.wikipedia.org/wiki/Functional_programming
[imperative]: http://en.wikipedia.org/wiki/Imperative_programming
[declarative]: http://en.wikipedia.org/wiki/Declarative_programming
[event]: http://en.wikipedia.org/wiki/Event-driven_programming
[dataflow]: http://en.wikipedia.org/wiki/Dataflow_programming
[reactive]: http://en.wikipedia.org/wiki/Reactive_programming
[unix]: http://en.wikipedia.org/wiki/Pipe_and_filter
[automata]: http://en.wikipedia.org/wiki/Automata-based_programming
[static]: http://en.wikipedia.org/wiki/Type_system#Static_typing
[dynamic]: http://en.wikipedia.org/wiki/Type_system#Dynamic_typing
[strong]: http://en.wikipedia.org/wiki/Strong_and_weak_typing#Strong_typing 
[weak]: http://en.wikipedia.org/wiki/Strong_and_weak_typing#Weak_typing
[inference]: http://en.wikipedia.org/wiki/Type_inference
[polymorphism]: http://en.wikipedia.org/wiki/Polymorphism_(computer_science)
[unified]: http://en.wikipedia.org/wiki/Type_system#Unified_Type_System
[primitives]: http://en.wikipedia.org/wiki/Primitive_data_type
[scope]: http://en.wikipedia.org/wiki/Scope_(computer_science)
[immutable]: http://en.wikipedia.org/wiki/Immutable_object
[GC]: http://en.wikipedia.org/wiki/Garbage_collection_(computer_science)
[shared]: http://en.wikipedia.org/wiki/Shared_memory
[compiled]: http://en.wikipedia.org/wiki/Compiled_language
[interpreted]: http://en.wikipedia.org/wiki/Interpreted_language
[native]: http://en.wikipedia.org/wiki/Bytecode
[vm]: http://en.wikipedia.org/wiki/Virtual_machine
[multithreaded]: http://en.wikipedia.org/wiki/Multithreading_(computer_architecture)
[greenthreads]: http://en.wikipedia.org/wiki/Green_threads
[concurrency]: http://en.wikipedia.org/wiki/Concurrency_(computer_science)#Models
[ipc]: http://en.wikipedia.org/wiki/Inter-process_communication
[distributed]: http://en.wikipedia.org/wiki/Distributed_system
[synchronization]: http://en.wikipedia.org/wiki/Synchronization_(computer_science)
[exception]: http://en.wikipedia.org/wiki/Exception_handling
[DbC]: http://en.wikipedia.org/wiki/Design_by_contract
[Eiffel]: http://en.wikipedia.org/wiki/Eiffel_(programming_language)#Design_by_Contract
[macro]: http://en.wikipedia.org/wiki/Macro_(computer_science)
[reflection]: http://en.wikipedia.org/wiki/Reflection_(computer_programming)
[decorators]: http://wiki.python.org/moin/PythonDecorators
[JIT]: http://en.wikipedia.org/wiki/Just-in-time_compilation
