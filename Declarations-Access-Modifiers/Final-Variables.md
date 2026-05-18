# Part - 8 - Final Variables

**Final Variables** :

A variable that can be assigned a value exactly once. Once assigned its value cannot be changed or reassigned during the program's execution.

**Final instance variables** :

1. if the value of a variable is varied from object to object such type of variables are called instance variables.
2. For every object a separate copy of instance variable will be created.
3. For instance variable we are not required to perform initialization explicitly JVM will always provide default values.

```
class Test{
    int x;

    public static void main(String[] args){
        Test t = new Test();
        Sop(t.x); -> OUTPUT 0
    }
}
```
4. If the instance variable is declared as final then initialization is compulsory, otherwise we will get compile time error

```
class Test{
    final int x;
}

Variable x might not have been initialize.
```
5. The following are various places for initialization of final instance variable:

```

1- At time of declaration:

    class test{
        final int x = 10;
    }

2- Inside instance block:

    class test{
        final int x;
        {
            x = 10;
        }
    }

3- Inside constructor:

    class test{
        final int x;

        Test(){
            x = 10;
        }
    }
```

**final static Variables** :

1. If a value of variable does not vary from object to object such types of variables are not recommended as instance variables. We have to declare these variables at class level by using static modifiers.
2. In the case of instance variable for every object a separate copy will be created but in the case of static variables a single copy will be created at class level and shared by every object of that class.
3. For static variables explicit initialization is not required, JVM will always provide default values.

```
class test{
    Static int x;

    public static void main(String[] args){
        Sop(x); -> OUTPUT 0
    }
}
```
4. If the static variable is declared as final then explicit initialization is compulsory otherwise we will get compile time error and JVM wont provide any default values

```
class test{
    final static int x;

} Error -> Variable x might not have been initialized.
```

5. For final static variables initialization should be perform before class loading completion, the following are various places for initialization for final static :

```
1- At the time of declaration:

class test{
    final static int x = 10;
}

2- Inside static block:

class test{
    final static int x;

    static{
        x = 10;
    }
}
```

**final local variables** :

1. Sometimes to meet temporary requirements of programmer we have to declare variables inside a method or block or constructor such types of variables are called local variables.
2. Local variables are also known as temporary variables, stack variables or automatic variables.
3. For local variables JVM doesn't provide any default values, hence explicit initialization is compulsory before using that local variables.
4. If we are not using local variables then it is not required to initialize local variable.
5. Even though local variable is final before using only we have to perform initialization if we are not using then its not required to perform initialization even though it is final.

```
class Test{
    public static void main(String[] args){
        final int x;
        Sop("Hello");
    }
} O/P -> HELLO
```
6. The only applicable modifiers for local variable is final and if we try to use any other modifiers then we will get Compile time error.

```
class Test{
    public static void main(String[] args){
        public int x = 10; -> C/E - illegal start of expression.
        final int x = 10; -> VALID
    }
}
```
7. If we are not declaring any modifiers then it by default its default, but this rule is applicable only for instance and static variables but not for local variables.

**Formal Parameters** :

1. Formal parameters of a method simply acts as local variables of that method hence formal parameters can be declared as final.
2. If formal parameters declared as final then within the method we cant perform reassignment