# ![[tktk Module Name] - tktk Microlesson Name](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to practice implementing the builder design pattern to construct complex objects with a controlled configuration. 

### Code along : Builder design pattern in action (20 minutes)

```java
package org.example.codealong.builder;

class Pizza {
    private String size;
    private String crust;
    private String toppings;

    public Pizza(String size, String crust, String toppings) {
        this.size = size;
        this.crust = crust;
        this.toppings = toppings;
    }

    @Override
    public String toString() {
        return "Pizza{" +
                "size='" + size + '\'' +
                ", crust='" + crust + '\'' +
                ", toppings='" + toppings + '\'' +
                '}';
    }
}

```

```java
package org.example.codealong.builder;

public class PizzaBuilder {
    private String size;
    private String crust;
    private String toppings;

    public PizzaBuilder() {
        // Set default values
        this.size = "Medium";
        this.crust = "Thin";
        this.toppings = "Cheese";
    }

    public PizzaBuilder setSize(String size) {
        this.size = size;
        return this;
    }

    public PizzaBuilder setCrust(String crust) {
        this.crust = crust;
        return this;
    }

    public PizzaBuilder setToppings(String toppings) {
        this.toppings = toppings;
        return this;
    }

    public Pizza build() {
        return new Pizza(size, crust, toppings);
    }
}

```

```java
package org.example.codealong.builder;

public class Main {
    public static void main(String[] args) {
        // Create a Pizza using the builder
        Pizza pizza = new PizzaBuilder()
                .setSize("Large")
                .setCrust("Thick")
                .setToppings("Pepperoni, Mushrooms, Olives")
                .build();

        System.out.println(pizza); // Output: Pizza{size='Large', crust='Thick', toppings='Pepperoni, Mushrooms, Olives'}
    }
}

```

In this example, `Pizza` represents the complex object we want to build. The `PizzaBuilder` class provides a
step-by-step approach to constructing a `Pizza` object. Users can set the `size`, `crust`, and `toppings` of the pizza
using setter methods, and finally call the `build()` method to obtain the desired `Pizza` object.

This allows us to create different variations of `Pizza` objects without exposing its construction details, making the
code more maintainable and flexible.