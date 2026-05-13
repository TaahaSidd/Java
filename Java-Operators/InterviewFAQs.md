# Part - 7 - Interview FAQs.

**new VS newInstance()**
1. **new** operator is used to create an object if we know class name at the beginning
```
   eg -
    Test t = new Test();
    Student stud = new Student();
    Customer cust = new Customer();

```

2. **newInstance()** is a method present in java.lang.Class. we can use newInstance() to create object if we don't know class name at the beginning and it is available dynamically at runtime.
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

But newInstance() method internally call no-arg constrictor hence to use newInstance() compulsory corresponding class should contain no-arg constructor otherwise we will get RuntimeException (InstantiationException)

While using new operator at runtime if the corresspoding .class file is not available then we will get RuntimeException->
NoClassDefFoundError : test

While using newInstance() at runtime if the corresponding .class file is not available then we will get RunTimeException -> ClassNotFoundException


**Diff b/w ClassNotFoundException VS NoClassDefFoundError**

For hardcoded class names, at runtime if the corresponding .class file is not available then we will get RunTimeException -> NoClassDefFoundError, which is unchecked.
```
    eg - Test t = new Test(); - at runtime if test.class file is not available then we will get R/E -> NoClassDEfFoundError : Test
```

For dynamically provided class names, at runtime if the coressponding .class file is not available then we will get R/E -> ClassNotFoundException, which is checked exception.
```
    eg - Object o = Class.forName(args[0]).newInstance(); - Java test Student (passing this) - R/E -> ClassNotFoundException : Student
```

instanceof is an operator in java we can use instanceof to check whether the given object is a particular type or not and we know the type at the beginning.
```
    eg -

        Thread t = new Thread();
        Sop(t instanceof Runnable);
        Sop(t instanceof Object);

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