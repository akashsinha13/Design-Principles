# Single Responsibility Principle (SRP)

> It states that there should never be two functionalities in one class.

This principle makes it easier to deal with bugs, to implement changes without confusing co-dependencies, and to inherit from a class without having to implement or inherit methods our class doesn't need.

For example, we can have classes such as ProductService that would fetch the product from the database, a ProductController to process the info and then we'd display it in a presentation layer using HTML.