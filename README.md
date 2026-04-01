<h1>
  <span class="prefix"></span>
  <span class="headline">Builder Design Pattern in Java</span>
</h1>

## About

We know Java constructors can be used to create and initialize objects. However, constructors simplify this task only for simple objects which have limited and straight-forward properties (like creating a green color tennis ball), and can be created in a single method call.

However, not all real-world objects are that simple. Think about how we will order a pizza. We need to mention the size, the kind of crust, then extra toppings, if any, and so on. But programmatically there can be only one class called `Pizza`. Things get complicated for constructors if the class has properties that:

- Are customizable during object initialization.
- Have a combination of mandatory and optional properties.
- Should be initialized in a sequence of steps rather than a single shot because of dependencies on other properties.

This is where a creational pattern called builder design pattern help us.

In this module, we'll explore what the builder pattern is and how to implement it in Java.

## Content

| Lesson | Est. Delivery Time | Skills |
| ------ |:------------------:| ------ |
| [Setup](./setup/README.md)                                                       |      10 min | Set up the development environment.                                                                     |
| [Builder Design Pattern](./builder-design-pattern/README.md)                     |      30 min | Describe builder design pattern and identify appropriate scenarios where it can be applied.             |
| [Builder Design Pattern in Action](./builder-design-pattern-in-action/README.md) |      30 min | Implement the builder design pattern to construct complex Java objects with a controlled configuration. |
| **Total content**                                                                | 1 hr 10 min |                                                                                                         |

## References

📖 [Reference Materials](./references/README.md)

## Internal

### Prerequisites

- None

### Course landing pages

- [JCD - Java Career Development Program](https://ga-curriculum.github.io/builder-design-pattern-in-java/canvas-landing-pages/jcd.html)
- [JSC - Java Short Course](https://ga-curriculum.github.io/builder-design-pattern-in-java/canvas-landing-pages/jsc.html)
- [Fallback](https://ga-curriculum.github.io/builder-design-pattern-in-java/canvas-landing-pages/fallback.html)

### Resources

✏️ [Instructor Guide](./internal-resources/instructor-guide.md)

🎥 [Video Hub](./internal-resources/video-hub.md)

🏗️ [Release Notes](./internal-resources/release-notes.md)

---

**Find a 👾 bug 👾 or have suggestions? [Let us know](https://ga-curriculum.github.io/universal-resources-internal/module-feedback.html)!**
