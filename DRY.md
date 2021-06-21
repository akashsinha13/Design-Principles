# Don't Repeat Yourself (DRY) Principle

> Every piece of knowledge or logic must have a single, unambiguous representation within a system.

### In terms of Inheritance
Whenever there's a functionality common across classes, it either might make sense to abstract them away into a common parent class or use interfaces to couple their functionality.

Suppose we have 2 classes Dog and Cat which extends Animal class. Both Dog and Cat need to eat food, but they speak differently. Since eating food is a common functionality for them, we can abstract it into the parent class Animal.

### In terms of Constants
Whenever there's a constant that's used multiple times, it's good practice to define it as a public constant.
Example:
```
public static final LOG_LIMIT = 1000;
```

### Why to Use?
To ensure easy maintenance of code, because when a functionality or a constant changes we have to edit the code only in one place.

## Voilation of DRY Principle
Often referred to as [WET solutions](https://en.wikipedia.org/wiki/Don't_repeat_yourself#DRY_vs_WET_solutions).

WET solutions aren't always bad, as repetition is sometimes advisable in inherently dissimilar classes, or in order to make code more readable, less inter-dependent, etc.
