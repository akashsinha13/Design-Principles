# Dependency Inversion Principle (DIP)

> If two classes are dependent, their features should be abstracted away and they should both depend on the abstraction, instead of on each other.

```java
enum OutputDevice {printer, disk};

void copy(OutputDevice dev){    
    int c;    
    while ((c = ReadKeyboard()) != EOF)
    { 
        if (dev == printer) 
            writePrinter(c); 
        else 
            writeDisk(c);    
    }
}
```

Consider above example, here code will be executed based on OutputDevice type. Suppose in future if new type will come, then we need to update the copy method.

```java
interface Reader {
    char read();
}    
interface Writer {
    char write(char ch);
}    

void copy(Reader r, Writer w){    
    char ch;    
    while((ch = r.read())!=EOF) 
    { 
        w.write(ch);    
    }
}
```

This way copy method is independent of reader and writer.


This principle is important because it decouples modules, making the system less complex, easier to maintain and update, easier to test, and more reusable. 