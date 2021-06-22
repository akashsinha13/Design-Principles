# Interface Segregation Principle (ISP)

> It states that the client should never be forced to depend on an interface they aren't using in its completly.

For example, a Pizza interface shouldn't be required to implement an addPepperoni() method, because this doesn't have to be available for every type of pizza.

```java
public interface Pizza {
    void addSauce();
    void bake();
}

public class VegPizza implements Pizza {
    public void addMushrooms() {System.out.println("Adding mushrooms");}

    @Override
    public void addSauce() {System.out.println("Adding sauce");}

    @Override
    public void bake() {System.out.println("Baking the vegetarian pizza");}
}

public class PepperoniPizza implements Pizza {
    public void addPepperoni() {System.out.println("Adding pepperoni");}

    @Override
    public void addSauce() {System.out.println("Adding sauce");}

    @Override
    public void bake() {System.out.println("Baking the pepperoni pizza");}
}
```

The VegPizza has mushrooms whereas the PepperoniPizza has pepperoni. Both, of course, need sauce and need to be baked, which is also defined in the interface.

If the addMushrooms() or addPepperoni() methods were located in the interface, both classes would have to implement them even though they don't need both, but rather only one each.