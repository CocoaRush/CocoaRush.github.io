---
layout:     post
author:     Pitt
catalog:    true
title:      All about protocols in Swift
subtitle:   Protocol oriented programming is an important concept in Swift
date:       2018-03-08
header-img: img/post-bg-22.jpg
tags:
    - 2018.03
    - Swift
    - ABC
---

A protocol defines a blueprint of methods, properties, and other requirements that suit a particular task or piece of functionality. The protocol can then be adopted by a class, structure, or enumeration to provide an actual implementation of those requirements. Any type that satisfies the requirements of a protocol is said to conform to that protocol.

>So, keeping it simple, a protocol says a struct , class or enum that if you want to be THAT, do THIS, THIS and THIS. Example: if you want to be a human, you have to EAT, SLEEP, and Take REST.


## Adding Property Requirements

* A protocol can have properties as well as methods that a class, enum or struct conforming to this protocol can implement.
* A protocol declaration only specifies the required property name and type. It doesn’t say anything about whether the property should be a stored one or a computed one.
* A protocol also specifies whether each property must be gettable or gettable and settable.
* Property requirements are always declared as variable properties, prefixed with the var keyword.
* Gettable and settable properties are indicated by writing `{ get set }` after their type declaration, and gettable properties are indicated by writing `{ get }`.

>Stored and computed properties are usually associated with instances of a particular type. However, properties can also be associated with the type itself. Such properties are known as type properties.

## Method Requirements

As mentioned earlier, protocols can have methods as well.

* A protocol can have type methods or instance methods.
* Methods are declared in exactly the same way as for normal instance and type methods, but without curly braces or a method body.
* Variadic parameters are allowed.
* Default values are not allowed.
* As with type property requirements, you always prefix type method requirements with the `static` keyword when they are defined in a protocol. This is true even though type method requirements are prefixed with the `class` or `static` keyword when implemented by a class.


## Protocols with mutating methods
Mutating methods are methods that we use on value types like structs and enums. These methods are allowed to modify the instance it belongs to and any properties of that instance.


## Initializer Requirements
Protocols can have specific initializers like normal methods which the confirming types can implement.



## Class Implementations of Protocol Initializer Requirements
You can implement a protocol initializer requirement on a conforming class as either a designated initializer or a convenience initializer. In both cases, you must mark the initializer implementation with the `required` modifier.


## Failable Initializer Requirements
Protocols can have failable initializers. A failable initializer requirement can be satisfied by a failable or nonfailable initializer on a conforming type. A nonfailable initializer requirement can be satisfied by a nonfailable initializer or an implicitly unwrapped failable initializer.


## Protocols as Types
Protocol is a type. You can use it in many places like:

* As a parameter type or return type in a function, method, or initializer
* As the type of a constant, variable, or property
* As the type of items in an array, dictionary, or other container
* Because protocols are types, begin their names with a capital letter to match the names of other types in Swift (such as `Int`, `String`, and `Double`).


## Delegation
Delegation is a design pattern that enables a class or structure to hand off (or delegate) some of its responsibilities to an instance of another type. Delegation pattern can also be used as a callback kind of mechanism.


## Adding Protocol Conformance with an Extension
You can extend an existing type to adopt and conform to a new protocol, even if you do not have access to the source code for the existing type. Extensions can add new properties, methods, and subscripts to an existing type, and are therefore able to add any requirements that a protocol may demand.



## Declaring Protocol Adoption with an Extension
If a type already conforms to all of the requirements of a protocol, but has not yet stated that it adopts that protocol, you can make it adopt the protocol with an empty extension.

Types do not automatically adopt a protocol just by satisfying its requirements. They must always explicitly declare their adoption of the protocol.



## Collections of Protocol Types
Protocols can be used as a type to be stored in collection types like array or dictionary.



## Protocol Inheritance
A protocol can inherit one or more other protocols. The syntax of protocol inheritance is similar to class inheritance.



## Class-Only Protocols
You can limit protocol adoption to class types (and not structures or enumerations) by adding the AnyObject or class protocol to a protocol’s inheritance list.



## Protocol Composition
Sometimes it is required for a type to confirm to multiple protocols. Image a function which accepts a parameter which should confirm to multiple protocols.

You can combine multiple protocols into a single requirement with a protocol composition. Protocol compositions behave like you defined a temporary local protocol that has the combined requirements of all protocols in the composition. Protocol compositions don’t define any new protocol types.



## Checking for Protocol Conformance
You can use the is and as operators described in Type Casting to check for protocol conformance, and to cast to a specific protocol. Checking for and casting to a protocol follows exactly the same syntax as checking for and casting to a type:

* The `is` operator returns `true` if an instance conforms to a protocol and returns `false` if it does not.
* The `as?` version of the downcast operator returns an optional value of the protocol’s type, and this value is `nil` if the instance does not conform to that protocol.
* The `as!` version of the downcast operator forces the downcast to the protocol type and triggers a runtime error if the downcast does not succeed.



## Optional Protocol Requirements
Protocol can have optional methods and properties.These requirements do not have to be implemented by types that conform to the protocol.

Optional requirements are prefixed by the `optional` modifier as part of the protocol’s definition. Optional requirements are available so that you can write code that interoperates with Objective-C. Both the protocol and the optional requirement must be marked with the `@objc` attribute. Note that `@objc` protocols can be adopted only by classes that inherit from Objective-C classes or other `@objc` classes. **They can’t be adopted by structures or enumerations**.


## Protocol Extensions
Protocols can be extended to provide method and property implementations to conforming types. This allows you to define behavior on protocols themselves, rather than in each type’s individual conformance or in a global function.


## Adding Constraints to Protocol Extensions
When you define a protocol extension, you can specify constraints that conforming types must satisfy before the methods and properties of the extension are available. You write these constraints after the name of the protocol you’re extending using a generic `where` clause.

```
extension Array where Element: Equatable
{

}
```

**End**
