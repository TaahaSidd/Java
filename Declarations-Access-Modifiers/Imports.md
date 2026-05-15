# Part - 2 - Imports and different types.

**Types of import statements** :

1. Explicit Class Import
2. Implicit Class Import
<br>

**Explicit Class Import** :

1. A statement that imports a single, specific class from a package by providing its full name and path.
```
eg - import java.util.ArrayList;
```
2. It is highly recommended because it improves readability of the code.

**Implicit Class Import** :

1. It imports an entire package of classes at once using wildcard asterisk (*).
2. It is also known as Wildcard import.
```
eg - import java.util.*
```
1. It is not recommended as reduced readability.

**Note** :

1. Whenever we are using fully qualified name we are not required to write import statement and vice-versa.
2. While resolving class name compiler will always give the precedence in following order.
```
    a. Explicit class import.
    b. Classes present in current working directory (CWD) (default package).
    c. Implicit class import.
```
3. Whenever we are importing a java classes all classes and interfaces present in the package while default available but not subpackage classes, if we want to use sub package class then we should write import until sub package level.

![text](../Images/DefaultClasses.png)

To use pattern class in our program the import statement required is import java.util.regex.*;

4. All classes and interfaces present in the following packages are by default available to every java program hence we are not required to write import statement.
```
    a. java.lang
    b. default package(CWD)
```