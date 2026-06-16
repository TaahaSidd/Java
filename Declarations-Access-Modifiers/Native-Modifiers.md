# Part - 10 - Native, Static, Transient Modifiers.

**Native Modifiers**:

1. native is a modifier that is only applicable to methods and we cant apply it anywhere else.
2. The methods which are implemented in non java (mostly C/C++) are called native methods or Foreign methods.
3. The main objectives of native keyword are to improve performance of the system, to achieve machine level or memory level communication, to use already existing legacy non java code.
4. For native methods implementation is already available in their native languages and we are not responsible to provide implementation hence native method declaration should ends with ;

```
public native void m1(); -> VALID

public native void m1(){

} -> INVALID
```

5. native and abstract combinations is illegal. abstract -> Java provides implementation later, native -> Implementation already exists in its native language.
6. We cant declare native method as strictfp.
7. The main advantage of native method is performance will be improved but the main disadvantages it break platform independent nature of java language.

```
Common examples of native method

1. System.arraycopy()
2. Thread.start0()
3. Object.hashCode()
```

**Pseudo code to use native keyword in java** :

1. Load native libraries.
2. Declare a native method.
3. Invoke a native method.

**transient Modifier** :

1. It is a modifier only applicable for variables.
2. We can use transient keyword in serialization context.
3. At the time of serialization if we don't want to save the value of a particular variable to meet security constraint then we should declare that variable as transient.
4. At the time of serialization JVM ignores the original value of transient variables and saves default values to the file.
5. Transient means not to serialize.
6. Transient is only used when class implements, transient has effect only during serialization/deserialization. In practice that means the class must participate in serialization(usually by implementing ```Serializable```).

```
implements Serializable
```

**volatile Modifier** :

1. It is only applicable only for variables.
2. If a value of a variable keep on changing by multiple threads then there may be a chance of data insistency problem we can solve this problem by using volatile modifier.
3. It does not create a separate per thread. Thread may cache values, but volatile forces reads and writes to be visible through main memory.
4. It guarantees visibility, not atomicity.
5. It is not deprecated and is still used in modern Java(flags,shutdown etc).
6. All threads share main memory, But threads may cache values locally.
7. ```volatile``` ensures every read/write happens from main memory.