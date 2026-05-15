# Part - 7 - Interview FAQs.

**new VS newInstance()**
1. **new** operator is used to create an object if class information is known at compile time.
```
   eg -
    Test t = new Test();
    Student stud = new Student();
    Customer cust = new Customer();

```
new operator is used for object creation, constructor invocation and memory allocation

1. **newInstance()** is a method present in java.lang.Class. we can use newInstance() to create object if class information is available dynamically at runtime.
```
   eg -
    class test{
        public static void main(String[] args) throws Exception{
            Object o = Class.forName(args[0]).newInstance();
            SOp("Object Created for :" + o.getClass().getName());
        }
    }

```
in the case of new operator based on our req we can invoke any constructor
```
    eg -
        Test t = new Test();
        Test t = new Test(10);
        Test t = new Test("durga");
```

But newInstance() internally invokes the no-arg constrictor. Hence the corresponding class should contain a no-arg constructor otherwise we may get InstantiationException.

While using new operator at runtime if the corresponding .class file is not available then we will get NoClassDefFoundError, which is an unchecked error.

While using newInstance() at runtime if the corresponding .class file is not available then we will get CheckedException -> ClassNotFoundException

Class.newInstance() is deprecated from Java 9 onwards, because it cannot properly handle constructor exceptions.


**Modern approach** :

```
Class.forName(args[0])
    .getDeclaredConstructor()
    .newInstance();
```

**Diff b/w ClassNotFoundException VS NoClassDefFoundError**

For hardcoded class names, at runtime if the corresponding .class file is not available then we will get RunTimeException -> NoClassDefFoundError, which is unchecked.
```
    eg - Test t = new Test(); - at runtime if test.class file is not available then we will get Error -> NoClassDefFoundError : Test
```

For dynamically provided class names, at runtime if the corresponding .class file is not available then we will get R/E -> ClassNotFoundException, which is checked exception.

```
    eg - Object o = Class.forName(args[0]).newInstance(); - Java Test Student (passing this) - R/E -> ClassNotFoundException : Student
```

instanceof is an operator in java we can use instanceof to check whether the given object is a particular type or not and we know the type at the beginning.

```
    eg -

        Thread t = new Thread();
        Sop(t instanceof Runnable);
        Sop(t instanceof Object);

```
```
null instanceof Object

Output -> false
```

isInstance() is a method present in java.lang.Class we can use this method to check whether the given object is of particular type or not and we don't know the type at the beginning and it is available dynamically at runtime.
```
    eg -
        class test{
            public static void main(String[] args) throws Exception{
                Thread t = new Thread();
                Sop(Class.forName(args[0]).isInstance(t))
            }
        }

```
isInstance() is dynamic version of instanceof.

**Reflection** :

1. It is a feature in java that allows inspection and manipulation of classes, methods, constructor and fields dynamically at runtime.
2. It is used heavily in:
```
   a. Spring Framework
   b. Hibernate
   c. JDBC
   d. Testing frameworks
```