# Part - 16 - Java Coding Standards

When ever we are writing java code it is highly recommended to follow coding standards, whenever we are writing any component.
Identifiers should clearly represent the functionality or responsibility of component, the main adv of this approach is readability and maintainability

**Coding Standard for Classes** :

1. Usually class names are nouns
2. They follow PascalCase naming convention.
```
    eg -

        StringBuffer
         
         Student
         
         ArrayList
```

**Coding Standards for Interfaces** :

1. Interface names are adjective
2. Should start with uppercase characters and every inner words should start with uppercase characters

**Coding Standards for Methods** :

1. Usually methods names are verbs or verb-noun combinations.
2. Should starts with lowercase character and if it contains multiple words then inner word should be uppercase(camel case convention)

```
   eg - addSum();
```

**Coding Standards for Variables** :

1. Usually variables names are nouns
2. Should starts with lowercase character and if it contains multiple words then every inner word should be camel case.

**Coding Standards for Constant** :

1. Usually constant names are nouns
2. Should contain only uppercase characters and if it contains multiple words then these words are separated with ( _ ).

```
    eg- MAX_VALUE
        MIN_VALUE
```

**Coding Standards for Java Bean** :

1. Java bean is reusable java class with private properties, public getter/setter methods & no-arg constructor .

```
   eg - public class StudentBean{
            private String name;

            public void setName(String name){
                this.name = name;
            }

            public String getName(){
                return name;
            }
   }

```
2. Frameworks like spring and hibernate use JavaBeans because private properties with public getter/setters make object management,dependency injection easier

**Syntax for setter method** :

1. It should be public method
2. the return type should be void, because setter methods generally returns nothing.
3. the method name should prefixed with "set"
4. it should take some arguments i.e it should take one arguments

```
   eg - setName(String name);
```

**Syntax for getter method** :

1. It should be public method
2. Getter methods are used to read/access private variables values
3. The return type should not be void
4. The method name should be prefixed with get
5. it should not take any arguments
6. for boolean properties getter can be **isActive()** instead of **getActive()**