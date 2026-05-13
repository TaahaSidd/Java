# Part - 16 - Java Coding Standards

When ever we are writing java code it is highly recommended to follow coding standards, whenever we are writing any component its name should .reflect the purpose of the components(Functionality) the main adv of this approach is readability and mailability

**Coding Standard for Classes** :

1. Usually class names are nouns
2. it should start with uppercase character and if it contains multiple words every inner word should start with uppercase character

    eg - StringBuffer

**Coding Standards for Interfaces** :

1. Interface names are adjective
2. Should start with uppercase characters and every inner words should start with uppercase characters

**Coding Standards for Methods** :

1. Usually methods names are verbs or verb-noun combinations.
2. Should starts with lowercase caricature and if it contains multiple words then inner word should be uppercase(camel case convention)
   
   eg - addSum();

**Coding Standards for Variables** :

1. Usually variables names are nouns
2. Should starts with lowercase character and if it contains multiple words then every inner word should be camel case.

**Coding Standards for Constant** :

1. Usually constant names are nouns
2. Should contain only uppercase characters and if it contains multiple words then these words are seperated with ( _ ).
    
    eg- MAX_VALUE
        MIN_VALUE

**Coding Standards for Java Bean** :

1. A java bean is a simple java class with private properties under public getter and setters.
```
   eg - public Class StudentBean{
            private String name;

            public void setName(String name){
                this.name = name;
            }

            public String getName(){
                return name;
            }
   }

```
**Syntax for setter method** :

1. It should be public method
2. the return type should be void
3. the method name should prefixed with "set"
4. it should take some arguments i.e it should be no arguments method

**Syntax for getter method** :

1. It should be public method
2. The return type should not be void
3. The method name should be prefixed with get
4. it should not take any arguments