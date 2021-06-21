# Open Closed Principle

> It states that classes and methods should be open for extension, but closed for modifications.

We should design our classes with possible future updates in mind, so they should have a generic design that we won't need to change the class itself in order to extend their behavior.

We can add more fields or methods, but in such a way that we don't need to rewrite old methods, delete old fields and modify the old code in order to make it work again.

This principle is important in order to ensure **backwards compatibility and prevent regressions**.

Example: Suppose we have a method to find area and currently we support to find area of rectangle. In future if we need to find the area of circle we need to update the method like we can add if else condition or switch case based on type.
Instead of doing this we can create an interface with method area and let respective classes define its own way to calculate area. We just need to pass the interface to the area method and based on it will calculate area. In this way area method will be close for modification.