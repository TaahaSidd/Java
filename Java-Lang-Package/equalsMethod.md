# Part - 3 , Equals() method.


**equals() method** : 

IN java equals() method is used to compare equality of two Objects. The equality can be compared in two ways :

**Shallow comparison** : The default implementation of equals method id defined in Java.lang.Object class which simply checks if two Objects references (say x and y) refer to the same Object. i.e it checks if x==y. Since Object class has no data members that define its state, it is also known as shallow comparison.

**Deep Comparison** : Suppose a class provides its own implementation of equals() method in order to compare the Objects of that class w.r.t state of the Objects. That means data members of Objects are to be compared with one another.

```
Syntax :

public boolean equals (Object obj)

// This methods checks if some other Object passed to it as an argument is equal to the object on which is is invoked.
```

**Some principles of equals() method** : If some other object is equal to a given object, then it follow these rules

1. **Reflexive** : for any reference value, a a.equals(a) should return true.
2. **Symmetric** : for any reference values a and b, if a.equals(b) should return true then b.equals(a) must return true.
3. **Transitive** :  for any reference values a, b and c, if a.equals(b) returns true and b.equals(c) returns true, then a.equals(c) should return true.
4. **Consistent** :  for any reference values a and b, multiple invocations of a.equals(b) consistently return true or consistently return false, provided with no information used in equals comparisons on the object is modified.

**Note** : 
For any non-null reference value a, a.equals(null) should return false.

**Object Class Implementation** :
The source code inside the ```Object``` class is written like this :

```
public boolean equals(Object obj){
    return (this == obj);
}
```

**Address Comparison** : It uses ```==``` operator under then hood, the default ```equals()``` method returns ```true``` only if both reference variables point to the exact same object in heap memory. 

**Overriding for Content Comparison** :

Based on real-world requirements, we don't care if the objects are at different memory locations; we care if their data matches. We override the method to perform Content Comparison.

**How to Properly Override ```equals()``` for Custom Classes** :

When overriding ```equals()``` for a custom class (like ```Student```), we must proactively handle three specific edge cases to prevent crashes.

1. **Self-Comparison Check** : if both variables point to the same memory location (```this == obj```), return ```true``` immediately to save processing time.
2. **```NullPointerException``` (NPE) Protection** : If some one passes a ```null``` argument into your method, it should return ```false```, not crash.
3. **```ClassCastException``` (CCE) Protection** : If someone passes an object of a completely different class type (a ```Student``` to a ```String```), you must return false instead of allowing a bad cast to crash the application. Use ```instanceOf``` or ```.getClass``` to verify the type.

**The ```==``` Operator vs. ```equals()``` Method** : 

- If ```r1==r2``` is true, then ```r1.equals(r2)``` will always be ```true```. (If they share the same memory sport, their data is guaranteed to be identical).
- If r1.equals(r2) is true, we cannot make any conclusions about r1==r2. It could be ```true``` or ```false``` (Two distinct objects in memory can contain the exact same internal text or values).

**The ```equals()``` and ```hashCode()``` Contract** :

If two objects are equal according to the equals() method, their hash codes must be equal.

If you override ```equals()```, you must override ```hashCode()```
