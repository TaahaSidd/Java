# Part - 1, 2, 3 & 4, 5, 6 -  Increment, Decrements & Arithmetic, instanceof...

**Operators & Assignments** :

**Operators** are special symbols or keywords that tell the compiler to perform specific mathematical, logical or relational operations on variables and values called **operands**

1. We can apply increment and decrement operates only on variables but not on constant values.

```
   eg - int x = 10;
        int y = ++x; -> this is valid

        int x = 10;
        int y = ++10; -> this is invalid and it will result in compile time error (unexpected type).

        int x = 10;
        int y = ++ (++x) -> Nesting of increment/decrement operators is not allowed because increment operators can be applied only to variables, but (++x) returns a value and not a variable.

```
2. Nesting of increment and decrement operators are not allowed.
   
```
   eg - int x = 10;
        int y = ++ (++x) -> Nesting of increment/decrement operators is not allowed because increment operators can be applied only to variables, but (++x) returns a value and not a variable.

```

3. For final variables we cannot apply increment or decrement operators.

```
   eg - final int x = 10;
        x++; -> this will result in compile time error (cannot assign a value to variable).

```
4. We can apply increment and decrement operators to every primitive types except boolean.

**Arithmetic operators** (+, -, *, /, %) :

1. If we apply any AO between two variables a & b the result type is always max(int,type of a, type of b)

2. In Integral arithmetic, division by zero is not allowed and causes Runtime Exception(ArithmeticException). However, overflow conditions do not cause exceptions in java.

**String concatenation operator (+)** :

1. The only overloaded operator in java is + operator sometimes it act as arithmetic addition operator and sometime it acts string concatenation operator.

2. If at least one arguments is string type then (+) acts as concatenation operator and if both arguments are number type then (+) acts as arithmetic addition operator.

```
    String a = "durga"
    int b = 10, c = 20, d = 30;

    sop(a + b + c + d) -> output = durga102030
    sop(b + c + d + a) -> output = 60durga
    sop(b + c + a + d) -> output = 30durga30
    sop(b + a + c + d) -> output = 10durga2030
```
**Relational Operator** (<, <=, >, >=) :

1. We can apply relation operator to every primitive data type except boolean
2. We cant apply relational operators to objects types.
```
   eg - Sop("durga12" > "durga") -> this will result in error "operator > cannot be applied to String.
```
4. Nesting of relational operators are not allowed.
```
   eg - Sop(10 < 20 < 30) -> Error -> "operator cannot be applied to boolean, int"
```
**Equality Operators** (==, !=) :

1. We can apply EO for every primitive types including boolean
```
   eg - Sop(false == false) - Output -> true.
```
2. We can apply EO for objects types also, for objects. If both reference variables are pointing to the same object then only EO will give true.
        ![alt text](/Images/EOCompatiablity.png)

3. If we apply EO for objects types then compulsory there should be some relation between qrguuments types (either child to parent, parent to child or same type) otherwise we will get compile time errors.


**Difference b/w == operator & .equals()** :

In general we can EO for reference comparison (address comparison) and .equals() for content comparison

```
        eg -
                String s1 = new String("durga");
                String s2 = new String("durga");

                Sop(s1 == s2) -> Output -> false;

                SOp(s1.equals(s2)) -> Output -> true.
```

**instanceof Operator** :

1. We can use instanceof operator to check whether the given object is a particular type of not.

```
syntax :

        r instanceof x

        here r is object reference, x is class/interface name
```
2. To use instanceof operator compulsory there should be some relation between arguments types. (either child to parent, parent to child or same type) otherwise we will get compile time error - (incompatible types)

```
   eg - Thread t = new Thread();
        
        Sop(t instanceof String); -> Compile time error.

```
3. for any class or interface "x" null instanceof x will always "false"

```
   eg -
        Sop(null instanceof Thread); -> false.
        Sop(null instanceof Runnable); -> false.

```

**Bitwise operators** (&,|, ^):

& - AND -> Returns true if both arguments are true.

| - OR -> Returns true if at least one arguments is true.

^ - X-OR -> Returns true if both arguments are different.
```
eg -
        Sop(true & false); - Output -> false
        Sop(true | false); - Output -> true
        Sop(true ^ false); - Output -> true

```
We can use bitwise operators for integral data types also.
```
        eg - Sop(4 & 5) - Output -> 4
             Sop(4 | 5) - Output -> 5
             Sop(4 ^ 5) - Output -> 1
```

**Bitwise complement operator (~)** :

1. We can apply this operator only for integral types but not for boolean type. if we try to apply then we will get compile time error.

**Boolean complement operator (!)** :
1. We can apply this operator only for boolean types but not for integral types.
```
   eg - Sop(!4); -> Error - operator ! cannot be applied to int
        Sop(!false) -> True - this is valid.
```
**Short-Circuit Operators (&& , ||)** :

1. These are exactly same as Bitwise operators (&, |) except the following diff

**Diff between (&, |) and (&&,||)** :

**(&, |)** :
1. Both arguments will be evaluated.
2. Performance is low.
3. Applicable for both boolean and integral types.

**(&&, ||)** :
1. Second argument evaluation is optional.
2. Performance is high.
3. Applicable for boolean only.

**Note** :
1. x && y = *y* wil be evaluated if *x* is true i.e if *x* is false then *y* wont be evaluated.
2. x || y =  *y* will be evaluated if *x* is false i.e if *x* is true then *y* wont be evaluated.

**Examples** :-
```
int x = 10;

if(++x < 10 && (x/0 > 10)){
        Sop("Hello");
}
else{
        Sop("Hi");
}

Output will be hi. *because we are using && operator and in this case the first arguments is false hence second argument will be skipped and from else block hi will be printed. and if we use & both conditions will be evaluated and the program will result in Runtime Exception -> ArithmeticException : / by zero*
```

**Type-case operator** :

1. Implicit type casting
2. Explicit type casting

**Implicit type casting** :
1. Compiler is responsible to perform implicit type casting.
2. Whenever we are assigned smaller value to bigger data type variable implicit will be performed.
3. It is also known as widening or upcasing.
4. Theres no loss of information in this type casting.

```
eg 1 -
        int x = 'a';
        Sop(x); Output -> 97 (Compiler converts char to int automatically by implicit casting)

eg 2 -
        double d = 10;
        Sop(d); Output -> 10.0 (Compiler converts int to double automatically by implicit casting)

```

**Explicit Type Casting** :

1. It is done by the user.
2. Whenever we are assigning bigger data type value to smaller data type variable then explicitly type is required.
3. Also known ass narrowing or downcasing.
4. there maybe a chance of loss of information.
5. During explicity narrowing conversion, JVM keeps only least significant bits(LSB) and discards remaining higher bits.

```
eg 1 -
        int x = 130;
        byte b = x;
        Sop(b); Output -> Error Compile time error - possible lossy conversion from int to byte

eg 2 -
        int x = 130;
        byte b = (byte) x;
        Sop(b); Output -> -126

Here the output is -126 because JVM keeps only least significant 8 bits.

```

**Assignment Operators** :
There are three types of assignment operators

1. Simple Assignment.

   eg - int x = 10; here = is the operator

2. Chained Assignment.

   eg - a = b = c = d = 10;

3. Compound Assignment.

**Chained Assignment**

1. We cannot perform chained assignments directly at the time of declaration.
```
        eg -
        int a,b,c,d;
        a=b=c=d=20; -> this is valid

        int a=b=c=d=20; -> this is invalid and compiler will give error (cannot find variable), the reason because we are declaring only "a" variable rest aren't declared.

        int b,c,d;
        int b=c=d=20; -> this is valid because here we are declaring every variable.
```
**Compound Assignment**
1. Assignment operator mixed with some other operator such type of assignment operators are called Compound operators
```
        eg -
        int a = 10;
        a += 20;

        Sop(a) -> Output - 30
```

1. Following are possible CA operators in java:

```
   eg -
   
        +=
        -=
        *=
        /=
        %=

        &=
        |=
        ^=

        >>=
        >>>=
        <<=

```

**Conditional Operator** :
1. The only possible ternary operator in java is CO (? :)
```
   syntax
        int x = (10 < 20) ? 30 : 40 -> OUTPUT - 30
```

2. We can perform nesting of CO also.
```
   eg - int x = (10 > 20) ? 30 : ((40 > 50) ? 60 : 70);
   Sop(x) -> OUTPUT - 70
```

**New Operator** :

1. We can use new operator to create objects.
```
   eg - Test t = new Test(); here new operator is used to create an objet.
```
2. After creating an object constructor will be executed to perform init of the object hence constructor is not for creation object and it is only for init of an object

3. In java we have only new keyword but not delete keyword because destruction of objects is the responsibility of JVM garbage collector

**Operator Precedence**
```
1. unary operators

   [], x++, x--
   ++x, --x, ~, !
   new, <type>

2. arithmetic operators

   *, /, %
   +, -

3. shift operators

   >>, >>>, <<

4. Relational operators

   <, <=, >, >=,

4. equality operators

   ==, !=

5. Bitwise operators

   &
   ^
   |

6. Short-circuit operators

   &&
   ||

7. Conditional operators

   ?:

8. Assignment operators

   =, +=, -=, *=

```

**Evaluation order of java operands**

1. In java we have only operator precedence but not operands precedence before applying any operator all operands will be evaluated from (left to right)

```
   eg - class test{
       
        public static void main(String[] args){
       
                Sop(m1(1) + m1(2) * m1(3) / m1(4) + m1(5) * m1(6))
        }

        public static int m1(int i){
                Sop(i);
                return i;
        }
   }

   Output -> 1 2 3 4 5 6 32 - here we got all the evaluated operands first then the final value by evaluating operators
```