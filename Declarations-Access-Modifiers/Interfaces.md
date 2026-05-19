# Part - 11, 12, 13, 14 - Interfaces.

**Introduction** :

1. It is a blueprint that defines a set of methods a class must implement without providing full implementation details.
2. Inside interface every method is always abstract whether we are declaring or not hence interface is considered 100% pure abstract class.
3. Any service requirement specification (SRS) is considered as interfaces.
4. Whenever we are implementing an interfaces for each and every method of that interfaces we have to provide implementation otherwise we have to declare class as abstract, then next level child class is responsible to provide implementation.
5. Every interfaces method is always public and abstract whether we are declaring or not hence whenever we are implementing an interface method compulsory we should declare as public otherwise we will get compile time error.

**Extends VS Implements** :

1. A class can extends only one class at a time
2. An interfaces can extends any number of interfaces simultaneously

```
interface A{

}

interface B{

}

interface C extends A,B{

}
```
3. A class can implement any number of interfaces simultaneously.
4. A class can extends another class and can implements any number of interfaces simultaneously.

```
class A extends B implements C, D, E{

}
```

**Interfaces methods** :

1. Every method present inside interfaces is always public and abstract whether we declare it or not.
2. Interfaces methods are defined public so that the method is available to every implementation class. and it is abstract because implementation class is responsible to provide implementation.
3. The following method declarations are equal:

```
void m1();

public void m1();

abstract void m1();

public abstract void m1();
```

**Interface variables** :

1. Interface can contain variables the main purpose of interfaces variables is to define requirement level constants.
2. Every interface variable is public static final whether we are declaring or not.

```
interface interf
{
    int x = 10;
}

Here the x variable is public so that it can be available to every implementation class,

x variable is static without existing object implementation class can access this variable,

x variable is final because if one implementation class can change value then it will affect the remaining implementation classes .
```

3. As every interface variable is always public static we cant declare with the following modifiers:

```
private

protected

transient

volatile

```
4. For interface variable compulsory we should perform initialization at the time of declaration otherwise we will get compile time error.

```
interface interf{
    int x;
}

C/E -> = expected
```

5. Inside implementation class we can access interface variables but we cant modify values of implemented variables.

```
class test implements interf{
    public static void main(String[] args){
        x = 777; -> C/E - cannot assign a value to final variable x.
        Sop(x);
    }
}
```

**Interface naming conflicts** :

1. If two interfaces contains a method with same signature and same return type then in the implementation class we have to provide implementation for only one method

```
interface left{
    public void m1();
}

interface right{
    public void m1();
}

class test implements left,right{
    public void m1(){

    }
}
```
2. If two interface contains a method with same name but different argument types then in the implementation class we have to provide implementation for both methods and these methods acts overloaded methods.

```
interface Left{
    public void m1();
}

interface Right{
    public void m1(int i);
}

class test implements Left,Right{
    public void m1();

    public void m1(int i){

    }
}
```

3. If two interfaces contains a method with same signature but different return types then it is impossible to implement both interfaces simultaneously (if return types are not co-variant).

```
interface Left{
    public void m1();
}

interface Right{
    public int m1();
}
```

**Interface variable naming conflicts** :

1. Two interfaces can contain a variable with the same name and there maybe a chance of variable naming conflicts but we can solve this problem by using interface names.

```
interface Left{
    int x = 100;
}

interface Right{
    int x = 200;
}

class Test implements Left,Right{
    public static void main(String[] args){
        Sop(x); -> INVALID - C/E reference to x is ambiguous.

        Sop(Left.x); -> VALID
        Sop(Right.x); -> VALID
    }
}
```

