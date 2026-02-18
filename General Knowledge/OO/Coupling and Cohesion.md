In OO, the smallest module of code is a class. Functionality and programs are built by multiple classes calling each other, with each class having limited responsibilities (Read: [[Encapsulation]] and [[Single Responsibility Principle]]).


## Coupling

Coupling describes a relationship between two modules. Two modules are loosely coupled if one module can be modified without changing the other. Two modules are tightly coupled if changing one module requires changing another. Coupling can be as direct as a concrete reference in one module to a second module- but it can be more abstract, e.g. if one module assumes something about the internal workings of another module.

Tight coupling is bad- a change in one module requires a change in a second, which may cascade and require a change in a third. Loose coupling is good.

## Cohesion
Cohesion measures how strongly related the responsibilities of a single module are. High cohesion indicates that elements inside a module work together to achieve a single purpose. Low cohesion groups unrelated functionalities.

High cohesion is good, it improves maintainability, readability, and reusability. Low cohesion is bad and a violation of the [[Single Responsibility Principle]].

## Visualization
- High cohesion low coupling is good
- Low cohesion high coupling is bad

![[Pasted image 20260218140525.png]]