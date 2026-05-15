# Part - 6 - Transfer Statements.

**Transfer Statements** :
1. Also known as jump statements.
2. Are used to unconditionally redirect the flow of program execution from one part to another.

**break** :

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

    Output -> 0,1
```
2. Inside loop to break loop execution based on some conditions.
```
    eg - for(int i = 0; i<10;i++){
        if(i == 5){
            break;
        }
        Sop(i);
    }

    Output -> 0,1,2,4
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
        Sop(i);
    }
}

Output -> 1, 3, 5, 7, 9
```
2. We can use continue statement only in loops, if we use continue statement anywhere else we will get compile time error -> continue outside of loop.
