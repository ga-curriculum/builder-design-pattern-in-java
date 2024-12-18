<h1>
  <span class="headline">Builder Design Pattern in Java</span>
  <span class="subhead">Builder Design Pattern in Action</span>
</h1>

**Learning objective:** By the end of this lesson, you'll be able to practice implementing the builder design pattern to construct complex objects with a controlled configuration. 

## Code along : Builder design pattern in action

### Step 1: Creating a product class with it's private static builder class

```java
public class Pizza {
    private String size;
    private String crust;
    private String toppings;

    // Private constructor
    private Pizza(PizzaBuilder builder) {
        this.size = builder.size;
        this.crust = builder.crust;
        this.toppings = builder.toppings;
    }

    @Override
    public String toString() {
        return "Pizza [Size: " + size + ", Crust: " + crust + ", Toppings: " + toppings + "]";
    }

    // Static Builder Class
    public static class PizzaBuilder {
        private String size;  // Required parameter 
        private String crust; // Optional parameter
        private String toppings; // Optional parameter

        public PizzaBuilder(String size) { // Mandatory parameter
            this.size = size;
        }

        public PizzaBuilder crust(String crust) {
            this.crust = crust;
            return this;
        }

        public PizzaBuilder toppings(String toppings) {
            this.toppings = toppings;
            return this;
        }

        public Pizza build() {
            return new Pizza(this);
        }
    }
}

```

### Step 2: Using the Builder to create pizzas
```java
public class PizzaShop {
    public static void main(String[] args) {
        // Build a simple pizza
        Pizza margherita = new Pizza.PizzaBuilder("Medium")
                .crust("Thin")
                .toppings("Cheese")
                .build();

        // Build a fully customized pizza
        Pizza meatLovers = new Pizza.PizzaBuilder("Large")
                .crust("Stuffed")
                .toppings("Chicken, Pepperoni, Sausage")
                .build();

        System.out.println(margherita);
        System.out.println(meatLovers);
    }
}

```


In this example, `Pizza` represents the complex object we want to build. The `PizzaBuilder` class provides a
step-by-step approach to constructing a `Pizza` object. Users can set the `size`, `crust`, and `toppings` of the pizza using setter methods, and finally call the `build()` method to obtain the desired `Pizza` object.

This allows us to create different variations of `Pizza` objects without exposing its construction details, making the code more maintainable and flexible.
