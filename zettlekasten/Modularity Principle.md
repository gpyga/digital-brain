2023-12-24 09:12:58
Status: #reference 
Tags: [[Design Principles]]
# Modularity Principle

```ad-quote
Systems should be decomposed into cohesive, loosely coupled modules.
```

Modularity is a design pattern seen in programming, where concerns are separated into cohesive modules and the modules are formed to be loosely coupled. By separating concerns into these modules, we have more control over building and maintaining systems, because each module can be independently maintained.

![Coupling vs Cohesion](https://upload.wikimedia.org/wikipedia/commons/0/09/CouplingVsCohesion.svg)
[[@CohesionComputerScience2023]]

```ad-note
Cohesion and coupling can be thought of as a form of [[Cluster  Analysis]]. In the case of clustering, we want to create groups in which the variance within clusters are less than the variance between clusters; in the case of modularity as a design princple, we want to create modules such that the inter-relatedness within modules (cohesion) is much more than the inter-relatedness between modules (coupling).

Specifically, cohesion and coupling are metrics of network clustering.
```

The Modularity Principle is further enhanced by the [[Abstraction Principle]], which states that the interface should be independent of implementation. 

```ad-note
Modularity is the composition of "black-boxes" such that the connection points are the core inputs and outputs of each black-box. Separation of the interface from the implementation allows us to easily replace individual black-boxes. It also frees users from needing to know anything about implementation for the sake of application. 
```

### Cohesion
Cohesion in a module is the degree to which its responsibilities form a meaningful unit of responsibility. Higher cohesion means the functionalities of a module are closely related. There is no direct way to measure cohesion, however, we can identify the type and the degree of cohesion.

#### Degrees of Cohesion:
1. Coincidental Cohesion (worst)
2. Logical Cohesion and Temporal Cohesion
3. Procedural Cohesion
4. Informational Cohesion 
5. Sequential Cohesion
6. Functional Cohesion (best)
7. Perfect Cohesion (atomic)

Coincidental cohesion is where modules are grouped together more-or-less by happenstance. There is no relation between the tasks other than (*coincidentally*) being contained in the same place.

```python
class CoincidentalCohesiveClass:
    """CoincidentalCohesiveClass
    The methods in this class are not really related to each other in any meaningful way.
    """
    def init_printer(self) -> None:
        ...

    def calc_interest(self, ...) -> float:
        ...

    def get_date(self, ...) -> datetime.datetime:
        ...
```

**Logical cohesion** is where modules are all conceptually related to each other. Additionally, a module can be **temporally cohesive** if the logical cohesion is due to the fact that tasks are invoked at the same time.

```python
class LogicallyCohesiveClass:
    """LogicallyCohesiveClass
    Each method in the class is logically related to one-another (calculating the area of some geometric shape), but they do not belong to the same proceedure.
    """
    def get_circle_area(self, ...) -> float:
        ...

    def get_rectangle_area(self, ...) -> float:
        ...

    def get_square_area(self, ...) -> float:
        ...


class TemporallyCohesiveClass:
    """TemporallyCohesiveClass
    Each method in the class is logically related by being executed at approximately the same time. 
    """
    def init_disk(self) -> None:
        ...

    def init_printer(self) -> None:
        ...

    def init_monitor(self) -> None:
        ...
```

**Procedural cohesion** occurs when all modules are belonging to the same application domain process.

```python
class ProceedurallyCohesiveClass:
    """ProceedurallyCohesiveClass
    Each method in this class represents an action taking place in the same process flow within a single application domain (making a cake).
    """
    def add_ingredient(self, ...) -> None:
        ...

    def mix(self) -> None:
        ...

    def bake(self) -> None:
        ...
```

**Informational cohesion** occurs when all modules are services performed by application domain objects.

```python
class InformationallyCohesiveClass:
    """InformationallyCohesiveClass
    Each method in this class represents an action taking place in the same process in a single application domain object (an airplane).
    """
    def takeoff(self) -> None:
        ...
        
    def fly(self) -> None:
        ...
        
    def land(self) -> None:
        ...
        
```

Informational cohesion is ruined when unrelated modules are added which are unrelated to the specific application domain object.

```ad-todo
Sequential and functional cohesion are missing from Pearce's notes.
https://en.wikipedia.org/wiki/Cohesion_(computer_science)
```

Sequential cohesion...

Functional cohesion...
```ad-info
From [Wikipedia](https://en.wikipedia.org/wiki/Cohesion_(computer_science)):

**Sequential cohesion** is when parts of a module are grouped because the output from one part is the input to another part like an assembly line (e.g., a function which reads data from a file and processes the data).
...
**Functional cohesion** is when parts of a module are grouped because they all contribute to a single well-defined task of the module (e.g., Lexical analysis of an XML string).
```

### Coupling
```ad-todo
[[5. Design Principles and Patterns]]
```

Coupling is the degree to which modules are inter-related to each other.

Transparency Principle ([[Law of Demeter]]): Avoid hidden dependencies.


---

## References
[[@pearceObjectOrientedAnalysis]]
[[@CohesionComputerScience2023]]

```ad-note
Pearce oft references "Jones", but seems to have missed the specifc reference. I have Googled `"jones" "law of demeter" "domains" object oriented` and I believe this *may* be the reference which was missing: https://books.google.com/books/about/What_Every_Programmer_Should_Know_about.html?id=GvsoAQAAMAAJ

```
