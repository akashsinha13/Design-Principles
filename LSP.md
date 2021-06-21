# Liskov Substitution Principle (LSP)

> Derived classes should be able to substitute their base classes without the behavior of our code changing.

## Problem it will try to fix

Suppose we have a class rectangle

```java
public class Rectangle {
    protected double a;
    protected double b;

    public Rectangle(double a, double b) {
        this.a = a;
        this.b = b;
    }

    public void setA(double a) {
        this.a = a;
    }

    public void setB(double b) {
        this.b = b;
    }

    public double calculateArea() {
        return a*b;
    }
}
```

Now let's try inheriting it for Square

```java
public class Square extends Rectangle {
    public Square(double a) {
        super(a, a);
    }

    @Override
    public void setA(double a) {
        this.a = a;
        this.b = a;
    }

    @Override
    public void setB(double b) {
        this.a = b;
        this.b = b;
    }
}
```

Let's say we initialized our Square and applied polymorphism to contain it within a Rectangle variable

```java
Rectangle rec = new Square(5);
```

Assume other programmer who has nothing to do with implementing these classes, decides that he wants to resize his rectangle. He may try something like this:

```java
rec.setA(6);
rec.setB(3);
```

He will see 9 as an answer. I guess we know why??

So when we're inheriting we have to keep in mind the behavior of our classes and are they really functionally interchangeable within the code, rather than just the concepts being similar outside of the context of their usage in the program.