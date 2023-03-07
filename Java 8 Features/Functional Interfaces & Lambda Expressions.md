## Java Functional Interface (Single Abstract Method (SAM) Interfaces)

A `Functional Interface` is an interface that only contains one abstract method. The purpose of this is to simplify the development of `functional programming` of java.

- Java provides several inbuilt functional interfaces in the `java.util.function` package such as `predicate, consumer, supplier`

### Functional Interfaces and Lambda Expressions.

Using an `interface` we can implement the following, as usual.

```java
public class A  {
    public static void main(String[] args) {
        MyInterface obj = new MyClass();
        obj.show();
    }
}

interface MyInterface {
    void show();
}

class MyClass implements MyInterface{
    public void show(){
        System.out.println("Saying Hi!");
    }
}
```

After Introduction of `Functional Interfaces` we can simplify the above using functional interfaces & lambda functions.

```java
public class A  {
    public static void main(String[] args) {
        MyInterface obj = ()-> {System.out.println("Hello")};
        //It's important that we call the method since the above code line will not call the function.
        obj.show();
    }
}
@FunctionalInterface
interface MyInterface {
    void show();
}
```

For functions with return types we can use the same, if it's a single line expression we can get rid of `return` keyword as well.

```java 
@FunctionalInterface
interface Adder {
    int add(int x, int y);
}

public class Mathematics {

    public static void main(String[] args) {
        Adder addition = (n1, n2) -> n1 + n2;
        addition.add(2, 4);
    }
}
```

### Q&A
1) Can you add a `toString` method in a Functional Interface?
- Yes, Because every class in Java Extends` Object class `and `toString` method is included in it.
```java
@FunctionalInterface
interface ExIntFace {
    void sayHi();
    String toString();
}
```

2. Why is there only a single method in Functional interfaces?
- When we are using lambda functions, if there were multiple methods compiler will not know which method to call & will lead to a confusion. 