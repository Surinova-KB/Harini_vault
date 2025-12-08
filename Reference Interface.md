
  A **reference interface** is a **memory location exposed by a controller** where another controller can write its **desired commands** (references) directly, instead of sending them via a topic.

- It's analogous to a **direct input port** for the controller.
    
- The controller **reads from it each update cycle** instead of reading from a subscriber.