# Errors

**PLP - Possible loss of precision.**

Possible Loss of Precision (PLP) occurs when a larger or more precise data type is assigned to a smaller or less precise data type, because some data may be lost during conversion.

```
eg - byte b = 128;

eg - int x = 10L;
```

**Null Pointer Exception**

Any operations performed with null with result in (NPE)

**NegativeArraySizeException**

This is caused when an negative value is passed as size for arrays

This is a RunTimeException

```
eg = int[] x = new int[-5];
```

**ArrayIndexOutOfBoundsException**

This is caused when we pass a out of range rather than whats defined for the array.

```
eg = int[] x = new int[3];

sop(x[5]) -> This will cause the error to come.
```

**NoSuchMethodError**

This is caused when JVM tries to call a method that was available during compilation but cannot find at runtime.

This is a RunTimeError.

**Arithmetic Exception**

This is a runtime exception.

It is only possible only in integral arithmetic but in floating point arithmetic.

The only operators which can cause this exception are : "/" & "%".