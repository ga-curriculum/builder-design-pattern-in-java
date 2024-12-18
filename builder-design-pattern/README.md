<h1>
  <span class="headline">Builder Design Pattern in Java</span>
  <span class="subhead">Builder Design Pattern</span>
</h1>

**Learning objective:** By the end of this lesson, you'll be able to identify the problem contexts, during your programming tasks, in which the singleton design pattern is the best solution.

## Problem: A pizza shop
Imagine a pizza shop that lists a variety of ways for customers to customize their pizzas on their menu, as shown below: 

- **Size**: A customer can choose one of the three sizes - Small, Medium, or Large.
- **Crust**: A customer can choose on of the three crust types - Thin, Pan, or Stuffed.
- **Toppings**: A customer can choose nothing to any number of offered ingredients as toppings - Cheese, Vegetables, Chicken, etc.

The pizza shop guarantees that their kitchen will deliver any pizza order with in 10 minutes. Now let's translate it to OOP programming paradigm. Each pizza is a product (an object instance) that needs to be created. In order to avoid delays, the pizza shop can employ a chef and an oven (constructor code block) for every permutation and combination of pizzas (Classes of pizzas) that are in the offering. Everytime, a customer gives a customized order, the corresponding class and it's contructor can create the pizza. However, this is coding intensive (code of classes and their constructors) and space intensive (Memory area to load and store the classes to be accessible anytime) 

Or, the pizza shop can prepare all possible permutations an combinations of pizzas well in advance and keep (pizza objects). That way when a customer orders any pizza, they just need to serve it. However, that would also need an enormous amount of space to store all the pizzas (heap memory to store the pizza objects). A lot of those pizzas might never get ordered.

The constaint of space (memory) and computing power (number of pizza maker can make simultaneously). To reduce this problem to its fundamentals, what needs to be solved is: How can a program (pizza shop) create any complex object (pizzas) as per customized requirements, with:
- Least number of classes (Recipes for pizza)
- An equal and reasonable number of statement executions (time taken) for creating any object
- Least amount of constructor code (chefs and ovens)


## The builder design pattern

The Builder pattern is a creational design pattern that separates the construction of an object from its
representation, allowing the same construction process to build a variety objects step-by-step in a controlled manner. This pattern is particularly useful when dealing with complex objects that require multiple steps to be constructed, or when there are different variations of the same object.

### Components of a builder design pattern

The Builder design pattern has the following components:

- **Product**: The complex object being built (e.g., Pizza).
- **Builder**: Abstract interface or base class that defines the steps to build the object.
- **Concrete Builder**: Implements the Builder interface to create and assemble the parts of the product.
- **Director** (Optional): Orchestrates the building process using the Builder.


### Advantages of builder design pattern

- **Separation of Concerns**: Builder pattern separates the construction of a complex object from its representation,
  allowing the same construction process to create different representations. This promotes cleaner and more modular
  code by separating the construction logic from the object's final structure.
- **Flexibility**: Builders allow for the construction of objects with complex configurations by providing a
  step-by-step approach. This flexibility enables the creation of different variations of objects without modifying
  their core implementation, making the codebase more adaptable to changing requirements.
- **Encapsulation**: Builder pattern encapsulates the construction process within the builder class, hiding the
  implementation details from the client code. This promotes information hiding and reduces the complexity of client
  code by providing a clear interface for object construction.
- **Immutability**: Builders can be designed to create immutable objects, ensuring that once constructed, the objects
  cannot be modified. Immutable objects are thread-safe and can help prevent unintended side effects in multi-threaded
  environments.
- **Complex Object Creation**: Builder pattern is particularly useful when dealing with complex objects that require
  multiple steps to be constructed or have optional parameters. By breaking down the construction process into smaller,
  manageable steps, builders simplify the creation of complex objects.

### Limitations of builder design pattern

- **Overhead**: Implementing the Builder pattern may introduce additional overhead compared to creating objects
  directly, especially for objects with simple construction requirements. This overhead comes from the additional
  builder class and the need to define multiple steps for object construction.
- **Increased Complexity**: Builder pattern adds complexity to the codebase, as it requires the definition of separate
  builder classes for each complex object. This complexity may make the code harder to understand, especially for
  developers unfamiliar with the pattern.
- **Potential for Inconsistency**: If the builder class is not properly implemented or used incorrectly, it may lead to
  inconsistencies in the constructed objects. For example, if mandatory parameters are not set before object
  construction, the resulting object may be incomplete or invalid.
- **Limited Usefulness for Simple Objects**: Builder pattern is most beneficial for constructing complex objects with
  many configurable parameters or optional features. For simple objects that can be created with a single constructor
  call, the overhead of using a builder may outweigh the benefits.
- **Dependency Injection Challenges**: When using dependency injection with builder pattern, injecting dependencies into
  the builder class and passing them to the constructed object may introduce additional complexity and boilerplate code.
  This can make the code harder to maintain and test.

### Most suitable problem contexts to use builder design pattern
- When creating objects with many optional parameters.
- When constructing immutable objects.
- When object construction involves complex validation or steps.
- In scenarios where the object’s construction process needs to be flexible and reusable.

### When NOT to use builder design pattern
- For simple objects with a few attributes.
- When the object’s structure is unlikely to change or when all attributes are always mandatory.