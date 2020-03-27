+++
title = "Javascript Fundamentals"
menutitle = "Javascript Objects"
description = "Objects in JavaScript"
weight = 2
+++

# Objects in JavaScript

"Everything is an Object" (well, almost)

---

**Primitives**
```
- Numbers
- Strings
- Booleans
- Undefined
- Null
```

- Variables containing primitives actually hold that data inside the variable itself.

++++++


**Everything ELSE**
```
- Arrays
- Functions
- Objects
- Dates
- Wrappers for Numbers, Strings, and Booleans
```
**IS AN OBJECT.**

- Variables associated with objects don’t contain the object, but rather contain a reference to the place ***in memory*** to where the object sits/stored. (Pointers)

- Variable declared as an object doesn’t have a real copy of the object, it just points to the object.

---

## OOP

Object-Oriented Programming
- Objects interacting with another thru **methods** and **properties**.
- Used to store Data, Structure Applications into modules and keeping code _clean_.

- Inheritance
    - “Why repeat the same stuff?”
        - Example:
          Person Object
          ```
          Person {
            name,
            yearOfBirth,
            job,
            calcAge()
          }
          ```

          (inheritance) =>

          Athlete Object (inherits from Person Object)
          ```
          Athlete {
            olympics,
            olympicMedals,
            allowedOlympics()
          }
          ```

          =>

          All comes together to form something like this:
          ```
          Athlete {
            olympics,
            olympicMedals,
            allowedOlympics(),
            *name,
            *yearOfBirth,
            *isMarried,
            *calcAge()
          }
          ```
          **<small> \* Inherited properties from Person Object.</small>**

    - Prototypes and Prototype Chains
        - Person - Prototype(calcAge())
        - Example: John{} => Person{} => Object{}
            - ^^ Prototype Chain (moves up to look for methods)
            - No prototype is null
                - Returns undefined

- Polymorphism
- Abstraction
- Encapsulation

Blueprints to build as many objects as we want.
- Constructors and instances in JS
    - Constructor => Instances

    Constructor
    ```
    Person {
      name,
      yearOfBirth,
      job,
      calcAge()
      }
    ```

      =>

    3 Instances
    ```
    Jane {
      Jane,
      1948,
      retired,
      calcAge()
    }
    ```

    ```
    Mark {
        Mark,
        1969,
        designer,
        calcAge()
    }
    ```

    ```
    John {
      John,
      1990,
      teacher,
      calcAge()
    }
    ```

- Called a _“Class”_ as well in other languages.

Every JavaScript object has a **Prototype Property**, which makes inheritance possible in JavaScript.

The **Prototype Property** of an object is where we put methods and properties that we want other objects to inherit.

The Constructor’s prototype property is **NOT** the prototype of the Constructor itself.
Rather, it’s the prototype of ALL instances that are created through it.

When a certain method (or property) is called, the search starts in the object itself, and if it cannot be found, the search moves on to the object’s prototype.
This continues until the method is found. Called the **Prototype Chain**.
