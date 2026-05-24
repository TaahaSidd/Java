# Part - 5, 6 Class level modifiers

**Class level modifiers** :

1. Whenever we are writing our own classes we have to provide some information about our class to the JVM like.

```
    a. Whether this class can be accessible from anywhere or not.
    b. Whether child class creation is possible or not.
    c. whether object creation is possible or not.
```
2. We can specify this information by using appropriate modifiers.

3. The only applicable modifiers for top-level classes are:

```
    a. public
    b. <default>
    c. final
    d. abstract
    e. Strictfp
```
But for inner class the applicable modifiers are:

```
    a. public
    b. <default>
    c. final
    d. abstract
    e. strictfp
    f. private
    g. protected
    h. static
```
4. If we try to use any non-applicable modifier on top-level classes we will get compile time error.

```
    private class Test{
        
        public static void main(String[] args){
            Sop("Hello");
        }
    }

    Compile time error -> modifier private not allowed here.
```

**Access specifier Vs Access modifiers** :

public, private, protected, default are considered as specifiers except these remaining are considered as modifiers. But this rule is only applicable for old languages like C++ but not in java.

In java all are considered as modifiers only theres no word like specifiers.

**Public Classes** :

1. If a class declared as public then we can access that class from anywhere.
2. If class A is not public then compiling B class we will get compile time error saying -> pack.A is not public in pack1; cannot be accessed from outside package.

```
eg -
    package pack1;

    class A{
        public void m1(){
            System.out.print("Hello");
        }
    }

    package pack2;
    import pack1.A;

    class B{
        public static void main(String[] args){
            A a = new A();
            a.m1();
        }
    }

    In here will get get error mentioned above and if we just add public to class A then no errors while compiling class B.
```

**Default Classes** :

1. If a classes is declared as default then we can access that class only within the current package i.e from outside package we cant access.
2. Default access is also known as package level access.

**Final Modifiers** :

1. Final is the modifier applicable for classes, methods and variables.

    **Final Methods** :

    1. Whatever method parent has by default it is available to child by inheritance if the child is not satisfied with parent method implementation then child is allowed to redefine the method based on its requirement this process is called overriding.
    2. If the parent class method is declared as final then we cant over ride the method in child class because its implementation is final.
    
    ```
        eg -  class P {
            public void Property(){
                Sop("Cash + land + gold");
            }

            public void marriage(){
                Sop("Maxim");
            }
        }

        class C extends P {
            public void marriage(){
                Sop("Mark");
            }
        }

        And if we declare marriage method as final and then try to override it in Child class we will get compile time error.
    ```

    **Final Class** :

    1. If a class declared as final we cant extend the functionality of that class i.e we cant create child class for that class.
    2. Inheritance and polymorphism is not possible for final classes.
    
    ```
        eg - final class P{

        }
        class C extends P{

        }

        We will get compile time error -> cannot inherit from final class p.
    ```

    3. In a final class methods cannot be overridden because child class creation itself is not possible, but every variable present inside final class is not final.
    4. The main advantage of final keyword is we can achieve security and we can provide unique implementation, but the main disadvantage of final keyword is we are missing key benefits of OOPs (inheritance, polymorphism) if theres no specific requirement  then its not recommended to use final keyword.

    **Final variables** :
    1. Once assigned, its value cannot be changed.
    2. For primitive the value cannot change.
    3. For reference variable, reference cannot change but object contents can change.
    
    ```
    final int x = 10;
    x = 20; -> Compile time error.
    
    final ArrayList l = new ArrayList();
    l.add("A"); -> VALID
    l = new ArrayList(); -> INVALID
    ```
   
**Abstract Modifiers** :

1. Abstract is a modifier applicable for classes and method but not for variables.
   
   **Abstract Method** :

    1. Even though we don't know about implementation still we can declare a method with abstract modifier i.e for abstract methods only declarations is available but not implementation hence abstract method abstract method contain only declaration and no implementation, hence they end with ";".
    
    ```
    eg -
        public abstract void m1(); -> VALID
        public abstract void m1(){

        } -> INVALID
    ```
    
    2. Child class is responsible to provide implementation for parent class abstract methods.
    3. By declaring abstract method in parent class we can provide guidelines to child classes such that which methods are compulsory child has to implement.
    4. Abstract method never talks about implementation if any modifiers talk about implementation then it forms illegal combination with abstract modifiers, the following are illegal combinations of modifiers for method with respect to abstract.
    
    ```
    eg -
        final
        synchronized
        static
        private
        strictfp

        all of these modifiers cannot be used with abstract. and if we try to use them with abstract we will get Compile time error -> illegal combination of modifier.
    ```
    5. If child class does not implement, then compile-time error occurs unless child is also abstract.

    **Abstract Class** :
    
    6. For any java class if we are not allowed to create an object (partial implementation) such type of class we have to declare with abstract modifier.
    7. For abstract classes instantiation is not possible.

    **Abstract class VS Abstract method** :

    8. If a class contains at least one abstract method then compulsory we should declare class as abstract otherwise we will get compile time error.
        
         **Reason** - IF a class contains at least 1 abstract method then implementation is not complete and hence it is not recommended to create object, to restrict object instantiation compulsory we should declare class as abstract.
    
    9. Even though class doesn't contain any abstract method still we can declare class as abstract if we don't want instantiation i.e abstract class can contain 0 number of abstract methods also.
    10. If we are extending abstract class then for each and every abstract method of parent class child class should provide implementation otherwise we have to declare child class as abstract.
    11. Abstract class can contain :
       
        a. abstract methods.
       
        b. concrete methods.
       
        c. constructor.
       
        d. variables.
       
        e. static methods.
       
        f. final methods.
        
        ```
        abstract class Test{
            Test(){
                Sop("Constructor");
            }
            
            final void m1(){
                Sop("final method");
            }
            
            static void m2(){
                Sop("static method");
            }
            
            abstract void m3();
        }
        ```

**Final VS Abstract** :

1. Abstract methods compulsory we should override in child classes to provide implementation whereas we cant override final methods hence final abstract combinations is illegal for methods.
2. For final classes we cant create child class whereas abstract classes we should create child class to provide implementation hence final abstract combination is illegal for classes.
3. Abstract class can contain final method whereas final class can't contain abstract method.

```
abstract class Test{
    public final void m1(){

    }
} -> VALID


final class Test{
    public abstract void m1();
} -> INVALID

```

**Missing Modifier Combination Rule** :

Illegal Modifier combinations for class

```
final abstract class Test{

}

INVALID because :
abstract -> child class required.
final -> child class not allowed.
```

**Constructors cannot be abstract** :

1. Constructor is used for object initialization.
2. Abstract methods are incomplete methods.
3. Constructors can never be overridden.

