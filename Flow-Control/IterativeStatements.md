# Part - 4, 5 - Iterative Statements

**Iterative Statements**

**while()**

1. If we don't know the number of iteration in advance then we should go for while() loop 

```
syntax -
    while(condition){
        
    }
```
2. The argument should be boolean type if we try to provide any other type then we will get compile time error.
```
while(1){
    Sop("Hello");
}

here the argument (1) passed will result in a error -> incompatible types found: int required: boolean
```
3. Curly braces are optional and without them we can take only 1 statement under while which should not be declarative statement.
```
while(true)
    Sop(Hello); -> VALID

while(true); -> VALID
    
while(true) -> INVALID
    int x = 10;

while(true){ -> VALID
    int x = 10;
}
```

**Note**
1. Every final variable will be replaced by the value at compile time only
```
eg -
    final int a = 10;
    int b = 20;

    Sop(a);
    Sop(b);

After compilation the Sop(10), Sop(b)
```
2. If every argument is a final variable(compile time constant) then operation should be performed at compile time only.
```
eg -
    final int a = 10, b = 20;
    int c = 30;

    Sop(a + b); At compile time -> Sop(30)
    
    Sop(a + c); At compile time -> Sop(10 + c)

    Sop(a < b); At compile time -> Sop(true)
    
    Sop(a > b); At compile time -> Sop(10 < c)

```

**do-while()** :

1. if we want to execute loop body at least once then we should go for do-while.

```
syntax - 
    do{
        body
    }while(condition);

; -> is mandatory, and condition should be boolean type
```
2. Curly braces are optional and without them we can take only one statement between **do** and **while** which should not be declarative statement
```
do
    Sop("hello"); -> VALID
while(true);

do;
while(true); -> VALID

do
    int x = 10; -> INVALID
while(true);

do{
    int x = 10; -> VALID
}while(true);

do
while(true); -> INVALID

```

**for-loop** :
1. For loop is the most commonly used loop in java
2. If we know number of iteration in advance then for loop is the best choice
```
syntax -
    for(initialization; condition; update){

    }
```
3. Curly braces are optional and without curly braces we can take only 1 statement under for loop, which should not be declarative statement
```
for(int i = 0; i < 0; i++) -> VALID
    Sop("Hello");

for(int i = 0; i < 0; i++); -> VALID

for(int i = 0; i < 0; i++) -> INVALID
    int x = 10;

```
**Initialization Section** :
1. This part will be executed only once in loop life cycle
2. Here we can declare and init local variables of for loop
3. Here we can declare any numbers of variables but they should be for the same type. If any diff data type variable is declared then we will get Compile time error.
```
eg - 
    int i = 0, j = 0; -> VALID

    int i = 0; String s = "durga"; -> INVALID
    
    int i = 0, int j = 0; -> INVALID
```
4. in the init section we can take any valid java statement including System.out.print.
```
eg - 
    int i = 0;
    for(Sop("Hello"); i <3; i++){
        Sop("Hi");
    }

    O/P -> Hello
           Hi
           Hi
           Hi
```

**Conditional Check** :
1. Here we can take any valid java expression but should be boolean type.
2. This part is optional and if we are not taking anything then compiler will always place "true"/
```
eg -
    for(int i = 0; ; i++){

    }
```

**Increment or Decrement Section** :
1. In this section we can take any valid java expression including System.out.print
```
eg -
    int i = 0;
    for(Sop("Hello"); i < 3 ; Sop("Hi")){
        i++;
    }

    O/P -> Hello
           Hi
           Hi
           Hi
```

**Notes**:

All three parts of for loop are independent of each other and optional
```
eg - 
    for(; ;){
        Sop("Hello");
    }

    for(; ; ); 

Both of these loops are valid and they are infinite loops.
```

**for-each loop(enhanced for loop)** :
1. Introduced in 1.5v
2. It is specially designed loop for retrieve elements of arrays and collections
3. To print elements of 1-d array:

```
int[] x = {10,20,30}

for(int x1 : x){
    Sop(x1);
}
```
4. To print elements of 2-d array

```
int[][] x = {{10,20,30} ,{40,50}}

for(int[] x1 : x){
    for(int x2 : x1){
        Sop(x2);
    }
}
```
5. For each loop is the best choice to retrieve elements of arrays and collections but its limitations is it is applicable for array and collection and its not a general purpose loop.
6. By using normal for loop we can print array elements either in original order or in reverse order but by using for each loop we can print array elements only in original order.

**Iterable(I)** :
```
syntax -
    for(eachitem x : target){

    }
```
1. The target element in for-each loop should be iterable object.
2. An object is said to be iterable if and only if corresponding class implements java.lang.iterable(I)
3. iterable(I) it was introduced in 1.5v and it contains only 1 method Iterator
```
syntax - public Iterator iterator()
```
4. All array related classes and collection implemented classes already implements iterable(I) being a programmer we are not req to do anything. we should be just aware of this.


**Diff b/w Iterator(I) & Iterable(I)** :

**Iterator**
1. It is related to collections
2. We can use this to retrieve elements of collection one by one.
3. It comes under java.util package.
4. It contains three methods:
   
   eg - hasNext()
        next()
        remove()

**Iterable()**
1. It is related to for-each loop.
2. The target element in for-each loop should be iterable.
3. it comes under java.lang package.
4. It contains only 1 method:
   
   eg - iterator()