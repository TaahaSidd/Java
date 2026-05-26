# Part - 11 - Static Block

**Static blocks** :
1. Whenever we are using static keyword and associate it with block then that block is referred to as a static block.
2. Java supports static block(also called static clause) that can be used for static initialization of a class.
3. This code inside the static block is executed only once, the first time the class is loaded into memory.
4. A class can have any number of static block, and they can appear anywhere in the class body.
5. The runtime system guarantees that static initialization blocks are called in order that they appear in source code.
6. Static blocks can also be executed before constructors.

**Calling of static block** :

In order to call any static block, there is no specific way as static block executes automatically when the class is loaded into memory.

**Printing something on console without creating a main() method** :

Yes, we can print if we are using JDK version 1.6 or previous and if after that it will throw an error.

```
Eg - Running on JDK 1.6

class Test{
    
    static {
        Sop("Static block");
    }
}

O/P -> Static block

Eg- Running on JDK 1.6 and later

class Test{

    static{
        Sop("Static block");
    }
}

O/P -> Main method not found in class Test....
```

**Static Control Flow with Inherited Classes** :

**Class loading** : Refers to reading the .class file and loading it into the memory (JVM). Java loads classes dynamically, that is classes are loaded on demand only when they are referred.

**Class initialization**: Refers to executing and initializing all the static members of a class. Class initialization occurs after the class is loaded into memory. Class initialization takes places in following scenarios :
    
    a. When a Class is instantiated.
    b. When a static field of the class is accessed(not final).
    c. When a static method is invoked.


**Static flow in derived class** :

1. When a derived class is referred to in a program, it invokes the initialization of the base class followed by the initialization of derived class.
2. Steps involved in static control flow in derived class:

   a. Identification of static members from parent to child class
   b. Execution of static blocks and assignment of static variables from parent class to child class.
   c. Execution of statement that invoked the static control flow.

**Key points regarding static control flow in derived class** :

1. If the derived class (Child class) is instantiated, the initialization of the base class (Parent class) takes place before the initialization of the derived class.
2. If the final static field is accessed, it doesn't cause the initialization of class.
3. If a static field of base is accessed or a static method of the base class is invoked using the derived class type, it doesn't cause initialization of the derived class. Only the base class(which contains the field or method) is initialized.
4. If the static feild of the derived class is accessed or the static method of the derived class is invoked using the derived class type, both base and derived classes are initialized.