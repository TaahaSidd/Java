# Part - 10 - Static control flow.

**Static control flow** :

1. Refers to the precise sequence of steps the Java virtual machine (JVM) follows to initialize a class when it is first loaded into memory.
2. It determines the order in which static variables are assigned, static blocks are executed, and the main method is called.

**Steps of Static Control flow** :

1. Identification of Static members : The JVM scans the class from top to bottom to identify all static variables, static methods and static blocks.
2. Execution of Assignments and Blocks : The JVM executes static variables assignments and static blocks in the exact order they appear in the source code (top to bottom).
3. Main method Execution : Finally the public static void main(String[] args) method is executed.

**Direct and Indirect Reference** :

1. If we try to read and display the value of a variable inside the static block, that read operation is called a direct read. If we call a method from a static block, and within that method if we are trying to read a variable that read operation is called indirect read.
```
class Test{
    static int i = 10;

    static{
        m1();
        Sop(i); -> Direct Read
    }

    public static void main(String[] args){
        Sop(i); -> Indirect Read
    }
}
```
2. If a variable is identified by the JVM and not yet initialized by its original value. In that case the variable is said to be Read Indirectly Write Only (RIWO) state.

**RIWO state** :

1. When a java class is getting executed there are few steps which JVM performs sequentially.
    a. Identify the static members from top to bottom.
    b. Executes static variables assignments and static blocks from top to bottom.
    c. Executes the main method.

2. During these phases, there is no such state called RIWO for a static variable.
3. During RIWO a variable cannot be accessed directly with its reference. Instead we need to use an indirect way to call certain variables.

```
class RIWO{
    static int i = 10;
    
    static{
        Sop(i);
    }
}

O/P -> 10
```
