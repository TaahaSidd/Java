# Part - 12 - Instance Control Flow.

**Instance Control Flow** :

1. Whenever we are executing a java .class file, 1st Static control flow will be executed.
2. In the static control flow, if we creating an object the following sequence of steps will be executed as part of instance control flow :
   a. Identification of instance member from top to bottom.
   b. Execution of instance variable assignments and instance blocks from top to bottom.
   c. Execution of constructor.
3. Instance control flow is not a one-time activity for every object creation will be executed.

**Instance Control flow in Parent To Child Relationship** :
Whenever we are creating a child class object the following sequence of events will be executed automatically.
    1. Identification of instance members from Parent to Child.
    2. Execution of instance variable assignments and instance blocks only in Parent class.
    3. Execution of parent constructor.
    4. Execution of instance variable assignments and instance block in child class.
    5. Execution of Child class constructor.

**Direct and indirect Reference** :
1. Inside instance block, if we are trying to read a variable that read operation is called Direct Read.
2. Inside instance block, if we are calling a method and within that method, if we are trying to read a variable that operation is called indirect read.
```
class Test{
    int i = 10;

    //instance block
    {
        methodOne(); //Indirect Read
        Sop(i); // Direct Read
    }

    // instance method
    public void methodOne(){
        Sop(i);
    }

}
```

**RIWO** :

1. If a variable is just identified by the JVM and the original value is not assigned then the variable is said to RIWO(Read Indirectly Write Only) state.
2. If a variable is in RIWO state then we cant perform Direct Read but we can perform Indirect Read.
3. If we are trying to read directly then we will get a compile time error : illegal forward reference.

