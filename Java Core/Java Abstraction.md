##Java Abstraction

`Abstraction` is the process of hiding implementation details and only showing functionality to user.
- There are two ways to achieve abstraction in Java.
  * Abstract Class (0 - 100%)
  * Interface (100%)
---
- When you are driving a vehicle you only see the accelerator. You know when accelerator is pressed vehicle moves faster, but you don't see how it makes the vehicle faster.

`Abstract Classes` in Java can have both abstract and non-abstract methods( _introduced with java 8_ ). **They cannot be used to create objects, must be inherited.**

- **Abstract Methods should not have method bodies, to be implemented in subclasses.**
- Declare with `abstract` keyword.
- Cannot be instantiated.
- They can have static methods, default methods and constructors.
- They can have final methods which will force the subclasses not to change the implementation of that specific method.

Example : 

```java
public class vehicle {

    public static void main(String[] args) {
        Accelerator fastCar = new RaceCar();
        fastCar.accelerate();
        Accelerator slowCar = new Taxi();
        slowCar.accelerate();
    }
}

abstract class Accelerator {
    abstract void accelerate();

    void brake() {
        System.out.println("Vehicle Stopping");
    }
}

class RaceCar extends Accelerator {

    @Override
    void accelerate() {
        System.out.println("RaceCar Accelerates 5ms-2");
    }
}

class Taxi extends Accelerator {

    @Override
    void accelerate() {
        System.out.println("Taxi Accelerates 1ms-2");
    }
}

```
---
###Q&A

1) **Can an abstract method declared as Static?**
- No, static methods belong to a class while abstract methods belong to an instance of the class. An abstract method is intended to be overwritten by a subclass and it doesn't make sense to declare it as static since static methods are NOT overridden by any subclasses.
- There can be static methods inside an abstract class, but they cannot be declared as abstract.
2) **Is it possible to have an abstract method without any abstract methods?**
- Yes

3) **Is it possible to achieve multiple inheritance through abstract class.**
- No
4) **Why Abstract class has a constructor in it even-though we cannot create objects of a abstract class?**
- We **can** create objects from a subclass of an abstract class. The subclass constructor has a super keyword which will call the constructor of the abstract class. Hence, constructor of an abstract class is used by the constructor of a subclass. 
5) **Can abstract methods be private?**
- Abstract methods cannot be private as they are intended to be implemented by a subclass, therefore accessible by the subclass.
- It's possible to have a private method inside an abstract class, but that cannot be defined abstract. 