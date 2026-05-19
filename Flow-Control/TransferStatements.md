# Part - 6 - Transfer Statements.

**Transfer Statements** :

1. Also known as jump statements.
2. Are used to transfer execution control from one part of  program to another.

**break** :

A flow control statement used to immediately terminate a loop or switch statement, when compilier encounters a break it stops executing the current block and jumps to the first line of code directly following that block.

We can use break statement in the following places.

1. inside switch to stop fall-through

```
   eg - int x = 0;
        switch(x){
            case 0:
                Sop(0);
            case 1:
                Sop(1);
                break;
            case 2:
                Sop(2);
            default :
                Sop("def");

        }

    Output -> 0,1 - because theres no break in case 0, so execution falls through.
```
2. Inside loop to break loop execution based on some conditions.

```
    eg - for(int i = 0; i<10;i++){
        if(i == 5){
            break;
        }
        Sop(i);
    }

    Output -> 0,1,2,3,4
```
3. Inside label blocks - to break block execution based on some conditions.

```
    eg -
    class test{
        public static void main(String[] args){
            int x = 10;

            l1:{
                Sop("begin");
                if(x==10){
                    break l1;
                }
                Sop("end");
            }
            Sop("hello");
        }
    }
```
4. If we are using break anywhere else we will get compile time error -> break outside switch or loop.

**continue** :

1. We can use continue statement inside loops to skip current iteration and continue for the next iteration.

```
eg - for(int i=0;i<10;i++){
    if(i % 2 == 0){
        continue;
    }
        Sop(i);
}

Output -> 1, 3, 5, 7, 9
```
2. We can use continue statement only in loops, if we use continue statement anywhere else we will get compile time error -> continue outside of loop.

**Labeled continue** :
1. Used within nested loops to skip the current iteration of an outer loop and jump directly to its next iteration.
2. While a standard continue only affects the loop it is immediately inside, the labeled version allows us to control a specific loop by name.

```
outer:
    for(int i = 0; i < 3; i++){
        for(int j = 0; i < 3; j++){
            if(j == 1){
                continue outer;
            }

            Sop(i + " " + j);
        }
    }
```

**Difference b/w break and continue** :

**break** :
1. It terminates loop/switch.
2. It controls moves outside loop.

**continue** :
1. Skips current iteration.
2. It controls moves to next iteration.

