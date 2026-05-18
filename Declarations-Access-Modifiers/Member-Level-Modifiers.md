# Part - 7 - Member Level Modifiers

**strictfp** :

1. Strict floating point.
2. Introduced in 1.2v.
3. We can use strictfp for classes and methods but not for variables.
4. Usually the result of floating point arithmetic vary from platform to platform, if we want platform independent results for floating point arithmetic then we should go for strictfp modifiers.

**strictfp Method** :

1. If a method is declared as strictfp all floating points calculations in that method have to follow IEEE 754 so that we get platform independent results.
2. Abstract modifier never talks about implementation whereas strictfp always talk about implementation hence abstract strictfp combination is illegal for methods.

**strictfp Class** :

1. If a class is declared as strictfp then every floating point calculation present in concrete method (a standard method that has complete implementation) has to follow IEEE 754 standard so that we will get platform independent results.
2. We can declare abstract strictfp combination for classes i.e abstract strictfp combination is legal for classes but illegal for methods.
```
abstract strictfp class Test{

} -> VALID

abstract strictfp void m1(); -> INVALID Compile time error - illegal combination of modifiers abstract and strictfp
```
**Member modifiers** :
1. Modifiers that control the accessibility and behavior of class members such as fields, methods.

    **public members** :
    1. If a member is declared as public then we can access that member from anywhere but corresponding class should be public, before checking member visibility we have to check class visibility.
    ```
    eg -
        package pack1;

        class A{
            public void m1(){
                Sop("A class method");
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

        While compiling class B we will get Compile time error -> pack1.A is not public in pack1; cannot be accessed from outside package.
    ```
    2. If both class and method are public then only we can access the method from outside package.

    **Default Members** :
    1. If a member is declared as default then we can access that member only within the current package, it cannot be accessed from outside package.
    2. Default access is also known as package level access

    **Private Members** :
    1. If a member is private then we can access that member only within the class, and from outside of the class it cannot be accessed.
    2. Abstract method should be available to the child classes to provide implementation whereas private methods are not available to the child classes to provide implementation. Hence private abstract combination is illegal for methods.

    **Protected Members** :
    1. If a member is declared as protected then we can access that member anywhere in the current package and only in child classes outside package.
    ```
    protected = <default> + child
    ```
    2. We can access protected members within current package anywhere either by using parent reference or by using child reference but we can access protected members in outside package only in child classes and we should use child reference only. Parent reference cannot be used to access protected members from outside package.
    ```
    package pack1;
    import pack1.A;

    class C extends A{
        public static void main(String[] args){
            A a = new A();
            a.m1(); -> INVALID - m1 has protected access in pack1.A
            
            C c = new C();
            c.m1(); -> VALID
            
            A a1 = new C();
            a1.m1(); -> INVALID - m1 has protected access in pack1.A
        }
    }
    ```