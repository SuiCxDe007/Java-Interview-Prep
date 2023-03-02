## Java Interfaces

`Interface` is a reference type in Java. It's another way to achieve 100& abstraction.

- Interfaces only provide method signatures.
- While a java class can only inherit from one super class at a time, interfaces can be implemented by multiple classes.
- Class can implement multiple interfaces. (Not Extended, only implemented)
- Interface can only have public methods (Implicitly Public).
- Interface cannot have a constructor.
- Interfaces are implicitly abstract, does not need to add abstract keyword.
- When an interface declares a method that throws a checked exception, any class that implements that interface should handle or declare that it throws the exception as well. (Due to method signatures should match)
