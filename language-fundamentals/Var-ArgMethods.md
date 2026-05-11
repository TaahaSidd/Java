# Part - 12 - Var-Arg methods

A  method that can take variable number of arguments is called var-arg methods

We can declare V-A method as follows
    
    eg -
        m1(int... x); ->  We can call this method by passing any number int values including (0)

        m1(); -> no arguments

        m(10); -> 1 arguments

        m1(10,20); -> 2 arguments

        m1(10,20,30); -> 3 arguments

Internally var-arg parameter will be converted into 1-D array, hence within the V-A method we can access var-arg values by array indexing or loop.

We can mix var-arg parameter with normal parameter
    
    eg - m (int x, int... y);

         m (String s, double... y);

We cannot mix var-arg with normal parameter if var-arg isn't at the last - this is invalid because compiler cannot determine where var-args end, where normal parameter ends.
    
    eg - m(int... x, String s);

Inside var-arg method we can take only 1 var-arg parameter, any more that 1 would give errors.

    eg - m(int...x, double... d);

Inside a class we cant declare var-arg method and the corresponding 1-D array method simultaneously otherwise we will get compile time errors.

```
    eg - class Test{
        
        public static void m1(int... x){
            Sop("var-args");
        }

        public static void m1(int[] x){
            Sop("array");
        }
    }

    this will result in Compile time error -> Cannot declare both m1(int[]) and m1(int...) in Test.

```

**Overloading priority** :

```
    eg -
        void m1(int x);
        void m1(int... x);

    m1(10); -> calling the method.

    Output -> normal method get priority because exact match preferred over var-arg match.

```

**Array Passing** :

We can directly pass array to var-arg method
```
    eg - int[] arr = {10,20,30}
    m1(arr);

    Its valid because var-args are internally arrays.
```