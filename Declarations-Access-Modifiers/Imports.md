# Part - 2, 3 - Imports and different types.

**Import Statements** :

1. Import statements in java is helpful to take a class or all classes visible for a program specified under a package, with the help of a single statement.
2. It is used to bring classes, interfaces, or entire packages into your code space.

**Types of import statements** :

1. Explicit Class Import
2. Implicit Class Import
<br>

**Explicit Class Import** :

1. A statement that imports a single, specific class from a package by providing its fully qualified class name and path.

```
eg - import java.util.ArrayList;
```

2. It is highly recommended because it improves readability of the code.

**Implicit Class Import** :

1. It makes all classes and interfaces of that package available using wildcard asterisk (*).
2. It is also known as Wildcard import.
```
eg - import java.util.*
```
3. It is not recommended as it reduces readability.

**Note** :

1. Whenever we are using fully qualified name we are not required to write import statement and vice-versa.
2. While resolving class name compiler will always give the precedence in following order.

```
    a. Explicit class import.
    b. Classes present in current working directory (CWD) (default package).
    c. Implicit class import.
```
3. Whenever we import a package, all classes and interfaces present in that package become available, but subpackage classes are not available automatically. If we want to use sub package class then we should write import until sub package level.

![text](../Images/DefaultClasses.png)

To use pattern class in our program the import statement required is ```import java.util.regex.*```;

4. All classes and interfaces present in the following packages are by default available to every java program hence we are not required to write import statement.

```
    a. java.lang
    b. default package(CWD)
```
5. Import Statements are compile-time related concepts but they do not affect runtime performance.
6. Import Statements is optional in Java because we can use fully qualified names directly.

```
java.util.ArrayList list = new java.util.ArrayList();
```

**Diff b/w C lang #include and java lang import statement** :

1. in the case of C lang #include all input output header files will be loaded at the beginning only (at translation time) hence it is static include.
2. But in the case of java import statements no .class file will be loaded at the beginning, whenever we are using a particular class then only corresponding .class file will be loaded this is like dynamic include or load on demand or load fly.

**Static imports** :

1. Introduced in 1.5v.
2. According Sun enterprise usage of static import reduces length of the code and improves readability but according to world wide programming experts usage of static import creates confusion and reduces readability hence if theres no specific requirement then its not recommended to use static import.
3. Usually we can access static members by using class name, but whenever we are writing static import we can access static members directly without class name.

**Explanation about System.out.println()**

```
class test{
    Static PrintStream out;
    .
    .
    .
    .
}

System.out.println()

Here System is a class present in java.lang.package.
Out is a static variable in System class of the type PrintStream.
println() is a method present in PrintStream class.

```
4. While resolving static members compiler will always consider the priority in following order.

```
    a. Current Class static members.
    b. Explicit static imports.
    c. Implicit static imports.

eg -
    import static java.lang.Integer.MAX_VALUE;
    import static java.lang.Byte.*;

    public class Test{
        static int MAX_VALUE = 999;

        public static void main(String[] args){
            Sop(MAX_VALUE);
        }
    }

OUTPUT -> 999
```

5. Two packages contains a class or interfaces with same name is very rare and hence ambiguity problem in normal imports, but two classes and interfaces contains a variable or method with a same name is very common and hence ambiguity is also very common problem in static import.

```
import java.util.Date;
import java.sql.Date;

class Test{

}

O/P -> Compile time error : reference to Data is ambiguous.
```

6. Usage of static import reduces readability and creates confusion and hence if theres no specific requirement then it is not recommended to use static import.

