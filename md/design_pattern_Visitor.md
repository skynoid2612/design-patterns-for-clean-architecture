
# Visitor Design Pattern Summary
> Version: dp_20231231_202019

- [Builder Design Pattern](#builder-design-pattern)
   * [Summary](#summary)
      + [Essence](#essence)
      + [Real examples](#real-examples)
   * [Implementation](#implementation)
      + [How to use it?](#how-to-use-it)
      + [Python code examples:](#python-code-examples)
   * [Analysis](#analysis)
      + [Cleaner Code?](#cleaner-code)
      + [Readable Code?](#readable-code)
      + [Replaceable code?](#replaceable-code)
      + [Testable code?](#testable-code)
      + [Advantages?](#advantages)
      + [Disadvantages?](#disadvantages)
   * [Remarks](#remarks)
      + [Concerns and Tips?](#concerns-and-tips)
      + [Execrises](#execrises)

## Summary

### Essence

- The Visitor design pattern allows adding new operations to existing object structures without modifying those structures.
- Separates the algorithm from the objects, enabling the addition of new operations without modifying the classes of the objects.
- Defines a new operation without changing the classes of the elements on which it operates.
- Encapsulates the new operation in a visitor class.

### Real examples

- In a compiler, the Visitor pattern can be used to perform different operations on the abstract syntax tree nodes, such as type checking, code generation, or optimization.
- In a GUI framework, the Visitor pattern can be used to implement different behaviors for different types of UI elements, such as rendering, event handling, or layout calculations.
- In a financial application, the Visitor pattern can be used to calculate different types of financial metrics, such as profit margins, return on investment, or risk assessments.
- Adding new operations to existing object structures without modifying those structures.
- Separating the algorithm from the objects on which it operates.
- Enabling the addition of new operations without modifying the classes of the objects on which it operates.


```mermaid
classDiagram
  class Element {
    +accept(visitor: Visitor): void
  }

  class ConcreteElementA {
    +accept(visitor: Visitor): void
  }

  class ConcreteElementB {
    +accept(visitor: Visitor): void
  }

  class Visitor {
    +visitConcreteElementA(element: ConcreteElementA): void
    +visitConcreteElementB(element: ConcreteElementB): void
  }

  class ConcreteVisitor1 {
    +visitConcreteElementA(element: ConcreteElementA): void
    +visitConcreteElementB(element: ConcreteElementB): void
  }

  class ConcreteVisitor2 {
    +visitConcreteElementA(element: ConcreteElementA): void
    +visitConcreteElementB(element: ConcreteElementB): void
  }

  Element <|-- ConcreteElementA
  Element <|-- ConcreteElementB
  Visitor <|.. ConcreteVisitor1
  Visitor <|.. ConcreteVisitor2
```

## Implementation
### How to use it?
To use the Visitor design pattern:
1. Define the visitor interface with visit methods for each concrete element.
2. Implement the visitor interface with concrete visitor classes.
3. Define the element interface with an accept method that takes a visitor as an argument.
4. Implement the element interface with concrete element classes.
5. In the client code, create instances of the concrete visitor and concrete element classes.
6. Call the accept method on the concrete elements, passing the concrete visitor as an argument.

### Python code examples:
```python
from abc import ABC, abstractmethod

class Element(ABC):
    @abstractmethod
    def accept(self, visitor):
        pass


class ConcreteElementA(Element):
    def accept(self, visitor):
        visitor.visit_concrete_element_a(self)


class ConcreteElementB(Element):
    def accept(self, visitor):
        visitor.visit_concrete_element_b(self)


class Visitor(ABC):
    @abstractmethod
    def visit_concrete_element_a(self, element):
        pass

    @abstractmethod
    def visit_concrete_element_b(self, element):
        pass


class ConcreteVisitor1(Visitor):
    def visit_concrete_element_a(self, element):
        print('Visitor 1 visiting ConcreteElementA')

    def visit_concrete_element_b(self, element):
        print('Visitor 1 visiting ConcreteElementB')


class ConcreteVisitor2(Visitor):
    def visit_concrete_element_a(self, element):
        print('Visitor 2 visiting ConcreteElementA')

    def visit_concrete_element_b(self, element):
        print('Visitor 2 visiting ConcreteElementB')


def main():
    elements = [ConcreteElementA(), ConcreteElementB()]
    visitors = [ConcreteVisitor1(), ConcreteVisitor2()]

    for element in elements:
        for visitor in visitors:
            element.accept(visitor)


if __name__ == '__main__':
    main()
```
   


## Analysis
### Cleaner Code?

- Separates the algorithm from the objects, promoting single responsibility and modularity.
- Allows adding new operations without modifying existing classes, reducing the risk of introducing bugs or breaking existing functionality.
- Encapsulates related operations in visitor classes, making the code more organized and easier to understand and maintain.

### Readable Code?

- Improves code readability by encapsulating related operations in visitor classes, making the code more organized and easier to understand.
- Separates the algorithm from the objects, making the code more modular and promoting single responsibility, which enhances readability.
- Allows adding new operations without modifying existing classes, reducing complexity and making the code more readable.

### Replaceable code?

- Promotes loose coupling by separating the algorithm from the objects on which it operates.
- Allows adding new operations without modifying existing classes, reducing dependencies between objects and operations.
- Encapsulates related operations in visitor classes, making it easier to manage and control dependencies.

### Testable code?

- Makes code easier to test by separating the algorithm from the objects, allowing for easier mocking and isolation of dependencies.
- Encapsulates related operations in visitor classes, making it easier to write focused and targeted tests for each operation.
- Allows adding new operations without modifying existing classes, reducing impact on existing tests and making it easier to add new tests.

### Advantages?

- Allows adding new operations to existing object structures without modifying those structures.
- Separates the algorithm from the objects, promoting single responsibility and modularity.
- Enables the addition of new operations without modifying the classes of the objects on which it operates.
- Promotes loose coupling between the objects and the operations.
- Enhances code organization, readability, and maintainability.
- Makes code easier to test and write focused tests for each operation.
- Solves the problem of adding new operations to existing object structures without modifying those structures.

### Disadvantages?

- Increases the complexity of the code by introducing additional classes and interfaces.
- Requires careful design and planning to cover all possible operations and elements.
- May lead to a proliferation of visitor classes if there are many different types of elements and operations.
- Introduces additional classes and interfaces, increasing the complexity of the code.
- Needs careful design and planning to cover all possible operations and elements.
- May lead to a proliferation of visitor classes.


## Remarks
### Concerns and Tips?

- The Visitor pattern introduces additional classes and interfaces, increasing the complexity of the code.
- The visitor interface and visit methods need to be carefully designed to cover all possible operations and elements.
- The visitor pattern may lead to a proliferation of visitor classes if there are many different types of elements and operations.
- Promotes loose coupling and modularity in code.
- Test each operation separately using focused tests for each visitor class.
- Designing the visitor interface and visit methods can be challenging.
- Managing dependencies between objects and operations can be complex.
- Careful design and planning are required to use the visitor pattern appropriately and avoid unnecessary complexity.


### Execrises

- Q: What is the purpose of the Visitor design pattern?

  - A: The purpose of the Visitor design pattern is to add new operations to existing object structures without modifying those structures.
- Q: How does the Visitor pattern achieve loose coupling?

  - A: The Visitor pattern achieves loose coupling by separating the algorithm from the objects on which it operates and encapsulating the new operations in visitor classes.
- Q: What are the advantages of using the Visitor pattern?

  - A: The advantages of using the Visitor pattern include the ability to add new operations without modifying existing classes, promoting single responsibility and modularity, and making the code more organized, readable, and testable.
- Q: What are the disadvantages of using the Visitor pattern?

  - A: The disadvantages of using the Visitor pattern include increased complexity due to additional classes and interfaces, the need for careful design and planning to cover all possible operations and elements, and the potential proliferation of visitor classes.
- Q: How does the Visitor pattern help in making code easier to test?

  - A: The Visitor pattern makes code easier to test by separating the algorithm from the objects, allowing for easier mocking and isolation of dependencies, and encapsulating related operations in visitor classes, making it easier to write focused tests for each operation.

