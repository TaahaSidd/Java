# Part 4 - Packages

**Packages** :
1. It is a encapsulation mechanism to group related classes and interfaces into a single unit, which is nothing but package.
```
eg 1 - All classes and interfaces which are required database operations are grouped into a single module/package which is nothing but java.sql package

eg 2 - All classes and interfaces which are useful for file input output (io) operations are grouped into a separate package which is -> java.io package

```
2. The main advantage of packages are :
```
    a. To resolve naming conflicts(unique identification of components)
    b. It improves modularity of the application.
    c. It improves maintainability of the application.
    d. It provides security for our components.
```
3. Theres one universally accepted naming convention for packages that is to use internet domain name in reverse.
```
eg - com.icicibank.loan.housing.Account

com.icicibank -> client internet domain name in reverse.
loan -> module name.
housing -> sub module name.
Account -> class name.
```

**Conclusion** :
1. In any java source file there can be at most one package statement i.e more than one package statement is not allowed otherwise we will get compile time error 
```
package pack1;
package pack2; -> Error - class, interface or enum expected

public class A {

}
```
2. In any java program the first non-comment statement should be package statement (if its available) otherwise we will get compile time error
```
import java.util.*;
package pack1; -> Compile time Exception - class, interface or enum expected

public class A{

}
```

3. the following is valid java source file structure:
```
eg -
    package Statement; -> At least one
    import Statements; -> Any number.

    class/interface/enums -> Any number.
```

**Note**
1. An empty source file is valid java program hence the following are valid java source files: 

![alt text](../Images/ValidJavaSourceFiles.png)
