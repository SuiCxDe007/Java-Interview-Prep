## Java Interfaces

`Interface` is a reference type in Java. It's another way to achieve 100& abstraction.

- Interfaces only provide method signatures.
- While a java class can only inherit from one super class at a time, interfaces can be implemented by multiple classes.
- Class can implement multiple interfaces. (Not Extended, only implemented)
- Interface can only have public methods (Implicitly Public).
- Interface cannot have a constructor.
- Interfaces are implicitly abstract, does not need to add abstract keyword.
- When an interface declares a method that throws a `checked exception`, any class that implements that interface should handle or declare that it throws the exception as well. (Due to method signatures should match)

---
### Diamond Problem

```java
class A {
  public void foo() {
    System.out.println("from Class A");
  }
}

class B extends A {
}

class C extends A {
}

class D extends B, C {
}

public static void main(String[] args) {
  D d = new D();
  d.foo();
}

```
Since D extends B & C classes, compiler is unable to determine which implementation od foo it should use. Hence, this is called `diamond problem` where inheritance takes a form of a diamond.

To avoid this, Java Provides multiple inheritance through interfaces, which in any case there are multiple inheritance, each will have their own implementation.

### Q&A

1) Can interfaces have static methods?
- Yes, from Java 8 it is allowed. However, they cannot be overridden 
2) What are `tagging interfaces`?
- Tagging interfaces/marker interfaces are interfaces that does not have any methods but serves as a marker to inform compiler that a class implements a certain behaviour or attribute. 
- It helps to create 
  - A Common parent so that compiler knows that perticular interface is going to be used in certain scenario. (Ex - `java.util.EventListner`)
  - Adds a data type to a class  
3) Can we declare reference variable with type interface (Ex - We have interface A, `A a`)
- Yes.
- In Java, a reference variable is a variable that holds the memory address of an object. When we declare a reference variable with a specific type, we are telling the compiler what type of object the variable can refer to.
In the case of an interface, declaring a reference variable with the interface type allows us to refer to any object that implements the interface. This is because an interface defines a set of methods that an implementing class must provide, and any class that implements the interface can be treated as an instance of that interface.
```java 
public interface MyInterface {
    void myMethod();
}

public class MyClass implements MyInterface {
    public void myMethod() {
        // implementation of myMethod
    }
}

public static void main(String[] args) {
    MyInterface a = new MyClass();
    a.myMethod(); // call the myMethod method on the MyClass object
}
```

- In this example, we declare a reference variable a with the type `MyInterface`. We then create a new instance of the `MyClass` class, which implements `MyInterface`, and assign it to `a`. We can then call the `myMethod` method on the `a` reference variable, which will call the implementation of `myMethod` provided by `MyClass`.
4) Can an interface extend another interface?
- Yes, But they cannot `implement`
5) Can you define a class inside a interface?
- Yes.
6) Can a interface method be declared as final?
- No, Final methods cannot be overridden.
7) Can we define variables in interfaces?
- Yes, They will be implicitly static and final.