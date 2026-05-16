# Part - 5, Class level modifiers

**Class level modifiers** :

1. Whenever we are writing our own classes we have to provide some information about our class to the JVM like

```
    a. Whether this class can be accessible from anywhere or not.
    b. Whether child class creation is possible or not
    c. whether object creation is possible or not.
```
2. We can specify this information by using appropriate modifiers

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
    e. Strictfp
    f. private
    g. protected
    h. static
```
4. If we try to any non applicable modifiers on top-level classes we will get error

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

In java all are considered as modifiers only theres no word like specifiers

**Public Classes **: 