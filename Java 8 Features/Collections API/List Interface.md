## List Interface

Java Lists contain the following features.

- Maintain the insertion order.
- Uses index based methods to insert, update, delete and search elements.
- Can have duplicate elements.
- Can have `null` elements.
- Provides control over position of next insertion.
- List index starts from `0`.
- Implementation classes 
       
  - ArrayList
  - LinkedList
  - Vector
  - Stack
  - CopyOnWriteArrayList
---
  
## ArrayList

Dynamic array for storing elements. It is not synchronized. (Not Thread Safe). We cannot create ArrayLists for primitive data types, will have to use relevant wrapper class.

Java new generic collection allows you to have only one type of object in a collection. Now it is type-safe, so typecasting is not required at runtime.

```java 
ArrayList myList1 = new ArrayList(); // Non Generi Arraylist (Old)
ArrayList<String> myList2 = new ArrayList<>(); // Generic arraylist (New)
```

### Q&A
1) What are the major differences between `Array` and `ArrayList`?
- Fixed Size vs Dynamic Size (Resize depending on capacity & Load factor)
- Cannot Store primitives in `ArrayList`.
- Can create without specifying size.

2) How can you remove duplicates from a ArrayList?
- You can convert ArrayList into a `set`; if the order is required as well, you can convert to a `LinkedHashSet`
3) Which is faster? `Array` or `ArrayList`?
   - `Arrays` are faster because they are low-level data structions in java that can be accessed directly from memory. Since Arraylists are built on top of arrays it's required additional overhead to manage dynamic resizing of arrays.
   - When an Array is created block of memory is allocated to store the elements which makes the accessing of individual elements very fast. Direct access to memory is not possible with ArrayLists since they are implemented via a array.