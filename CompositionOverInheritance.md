# Composition Over Inheritance Principle

> If our class is going to implement all of the functionalities and our child class can be used as a substitute for our parent class, use inheritance.

> If our class is going to implement some specific functionalities, use composition(interface).

Sometimes when child classes are inherited from their parent classes and if we need a feature from others parent class then either we hit diamond shape problem or we voilate DRY principle. So whenever possible use composition over inheritance.

This also resolves the problem of dependencies destroying important functionalities and causing a chain reaction throughout our code. 

If we happen to need exact same functionality in multiple classes, we can implement it using a default method in our interface, to avoid violating DRY.