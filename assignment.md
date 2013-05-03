# Barracuda: Language Design Document

**Authored by Ryan Toussaint**

## Goals and Objectives

* What problem/needs are you trying to solve?
* 
*  THE MAIN PROBLEM THAT I AM TRYING TO SOLVE IS OFFERING A LANGUAGE TO BEGINNER PROGRAMMERS THAT WILL TEACH THEM THE 
*  BASICS BUT ALSO GIVE THEM A SENSE OF WHAT IS GOING ON DURING THE CODE AND WHAT IS BEING EVALUATED.  I WANT TO DO THIS
*  THROUGH AN EMPHASIS ON DEBUGGING AND ERROR MESSAGES.  I THINK THESE ARE TWO BIG WAYS THAT PEOPLE CAN LEARN AND BY
*  SHOWING THEM LIVES UPDATES OF WHAT IS TAKING PLACE, I THINK WILL ALLOW BEGINNERS TO GET A BETTER GRASP OF PROGRAMMING
*  AND WHERE IT CAN TAKE THEM IN THE FUTURE WHEN THEY IMPROVE.
* 
* 
* 
* What tasks would be made easier using your language?
* 
* ^^^DEBUGGING AND LEARNING THE BASICS OF A PROGRAMMING LANAGUAGE FOR SOMEONE WHO IS COMPLETELY NEW TO CODING.
* 
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
        * 
        * I would like to use encapsulation in my ideal language so that I can limit content to certain properties
        * and thus restricting access to certain characteristics of the object's components.
        * 
        * Handling primitives
        * 
        * Primitives will be handled by using a loose interpretation.  That is, the line of code "a+5" will be 
        * concatenated together to return the value of "a5".  I think this will make my language more versatile and 
        * thus allow it to be adapted to a wide range of scenarios.  In addition, it will be more flexible to the 
        * programmer who will be writing the code.
        * 
        * Generics/templating
    * [Functional][functional]
        * Purely functional or impure?
        * 
        * I would like my language to be purely functional.  One of the areas that I am trying to cater to, 
        * with Barracuda is to people who are new to programming.  By allowing the new programmer to have some
        * flexibility with the code, I think it will be easier for them to learn.  However, I also want to make 
        * the language adaptable so that if they go on to learn other languages, the skills that they have learned 
        * with Barracude will carry over.  Thus by focusing on a functional language, I am able to implement recursion,
        * data structures that are popular across platforms, and higher order fuctions.  By integrating these and making
        * them a central focus, I hope to have people learn Barracuda fast but also let them carry it over to other
        * langauges.
        * 
        * How do you deal with side effects and state
        * Handling anonymous functions and function references
        * Special forms such as functors or monads
        * Dealing with deep recursion and stack overflows
        * 
        * Recursion is going to be a key part of Barracuda.  I would like to deal with recursion by implementing it in
        * a similar way to Java, but give a notification faster if someone was to stack overflow.  Since my Barracuda
        * is centered around learning, I would also like to put an emphasis on error checking and debugging.  Recursion
        * is an area where this can be done because most new coders will run into trouble with this.  As a result,
        * I want to add Barracuda Errors that make more sense than traditional errors and offer the coder, the chance to
        * see what went wront and where he/she can learn.
        * 
        * Dealing with mutual recursion
        * Function overloading and/or polymorphism
    * [Imperative][imperative]
        * Defining and navigating through procedures
        * What additional control structures are necessary?
    * [Declarative][declarative]
        * General approach/algorithm for handling control flow
        * How to define relations and entities
        * 
        * Defining entities will be very loose with Barracuda.  For example, in Java there are different uses for 
        * .size(), .length(), etc. and this make it confusing for a new programmer.  However, with Barracuda, it would
        * only use one call (e.g. ".length" with no '()').  Thus, this will consolidate what the new Barracuda learner
        * needs to know and get them into coding faster.  --Different strategies will be taking place like this
        * throughout the language, because the main goal is simplying the learning while still knowing how code works
        * 
        * One more example can be seen with .equals() and '==' -- this would be replaced with only == and give the 
        * lanauge more simplification.
        * 
        * Use of logic or constraints
    * [Event-driven][event]
        * How events are handled (triggering and registering)
        * Synchronization when reacting to events
    * [Data-flow][flow]/[Reactive][reactive]
        * How do you listen and track dataflow changes
        * 
        * The key aspect for dataflow that Barracuda will rely on is that if a variable is changed, then all the other
        * outputs and variables that rely on it, will also have to be recalculated.  Aside from this, tracking dataflow
        * changes will be similar to how they run in C and Java.
        * 
    * [Pipes and filters][unix]
        * What unifying data structure would be used?
        * 
        * Since Barracuda is focused around being a learning language, the major data structure that will be used, will 
        * be an array.  An array is easy to learn, has multiple uses, and can be adapated to may situations.  Arrays
        * will be able to hold ints, chars, etc.  However, one thing that may make Barracuda different is that if a word
        * wants to be stored in an array, then that index of the array will act as an array itself because each letter 
        * in the array is stored separately.  Although I have not played around with this, it seems like a neat area to 
        * research and see how this may be able to increase functionality.
        * 
        * What protocols for communication would need to be established?
    * [Automata/State-machine][automata] based

## Type System

* [Static][static] typing vs [dynamic][] typing
    * Execution speed
    * Safety and exception handling
    * 
    * Exception handling will be handed over the OS.  However the key emphasis that I want to give around Barracuda is 
    * that it's focus will be towards providing valuable feedback on what the programmer did wrong, and why this error
    * occured.  I hope that through the error-checking and debugging, the programmer can learn better and understand his
    * /her mistakes.
    * 
    * Tooling (e.g. IDEs, linters, etc.) support
    * 
    * Barracuda will be a language based on the web, so that it is universally accessible and widely distributed.  
    * Projects that are created on Barracuda will be stored in the Cloud that each person can make an account to
    * and thus have their work wherever they may be.
    * 
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
    * 
    * Barracuda will have function scope primarily because of its heavy emphasis with recursion.  By using recursion,
    * I want Barracuda to also be function scope so that methods are aware of the outer method that called it and know
    * the state that it is in.
    * 
    * Implications on closures
* Control Structures
    * Looping structures
    * 
    * Barracuda will hopefully be a logical programming language.  One example will be that is can execute loops in 
    * parallel with another.  Thus if a forloop is running 8 times, the forloop will execute all 8 loops at the same
    * time and then combine all the responses into one answer.  By doing this, Barracuda will run faster than tradtional
    * languages.
    * 
    * 
    * Branching
    * Recursive calls
    * 
    * --^^^^See the explanation above and how recursion will be implemented into this project.
    * 
    * Premature exiting
    * Pattern matching
    * 
    * Pattern matching will mostly be utilized when doing loops.  When Barracuda realizes that the same cycle of
    * instructions are being executed, it will learn from this and thus execute more instructions in its 'parallel mode'
    * so that things can run faster.
    * 
    * Eager vs lazy evaluation
    * 
    * Lazy evaluation will used because of the fact that Barracuda uses a loose interpretation.  Thus 'a+5' will be 
    * evaluated to a5.
    * 
    * Generators and list comprehensions
    * Continuations and coroutines
* Data structures
    * Lists and collections
    * Messages
    * Events
    * Structures/records
    * Data storage: JSON, XML, etc.
    * 
    * The files will be stored online in a cloud account.
    * 

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
    * 
    * Barracuda will restore state, by noticing that an error has occured and quitting out of the program.  It will then
    * prompt the user with an error and ask them to correct what is wrong.  The programmer can make this change, and 
    * Barracuda will know where to start again (from where it left off at) and keep evaluating.  In this sense, Barracuda
    * can keep state after the program has quit, as long as it does not quit entirely out.  What I mean by this, is that
    * Barracuda will focus again on helping people learn and thus give them a chance to correct the code (during the
    * first quit out), before it throws an another error and quits out entirely.
    * 
    * 
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
    * 
    * During runtime, Barracuda will give live updates to what it is doing and showing the programmer what he/she has
    * just coded.  With live updates, I want to put an emphasis on showing the programmer what is going on, so that they
    * can hopefully learn while the program evaluates.
    * 

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
* 
* ^^^Yes debugging will be a main focus of this language so that programmers can learn better and see why errors are
* occuring.
* 
* 
* Any special considerations for using IO devices?

## Other Unique Features

* Whatever you can think of that you think would be useful
* Examples
    * Syntactic sugar (or why not just make your syntax cleaner to begin with)
    * Native RegExp support if your language focuses on text manipulation
    * Code synthesis (e.g. generating getters and setters)
    * 
    * THE MAIN SPECIAL FEATURE THAT BARRACUDA WILL OFFER IS THE USE OF DEBUGGING AND ERROR MESSAGES THAT WILL ALLOW 
    * PEOPLE TO LEARN AND SEE WHAT THEY ARE DOING WRONG.  I WANT BARRACUDA TO HELP PEOPLE SO THAT THEY CAN GO ON TO LEARN
    * OTHER LANGUAGES AND TAKE THE BEGINNER SKILLS WITH THEM AND I THINK BARRACUDA CAN DO THIS BY SHOWING PEOPLE THE
    * ERRORS THAT THEY ARE GETTING (WITH LIVE UPDATES) AND HOW THESE ERRORS CAN BE AVOIDED IN THE FUTURE.
    * 

## Conclusion

* Overview of features
* Differentiating characteristics or features
* Practical uses
* 
* PLEASE REFERENCE THE ABSTRACT FOR THIS SECTION, BUT BASICALLY BARRACUDA WILL OPERATE AS A LANGUAGE THAT IS FOR NOOBS
* AND WANT TO GET STARTED WITH PROGRAMMING.  IT WILL FOCUS ON THE BASIC DATA STRUCTURES WITH AN EMPHASIS ON ARRAYS AND
* THEN GIVE EXTRA ATTENTION TO DEBUGGING AND ERROR MESSAGES SO THAT PEOPLE CAN SEE WHAT IS GOING ON IN THE PROGRAM THEY 
* WROTE
* 
* 
* 
* 
* YANG AND KEVIN,
* 
* Thank you very much for taking the time to teach this class.  I really appreciate and it was eye-opening to see all the
* different techniques that other languages are using.  I'm hoping to go back through over the summer and focus more on
* Javascript and Scala.  Good luck with your jobs next year!
* 
* - Ryan





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
