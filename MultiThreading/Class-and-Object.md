# Part 8 - Class lock and Object lock

**Two types of locks on thread** :

**Object-Level Lock** :

1. Every object in java has a unique lock. Whenever we are using a synchronized keyword then only the lock concept will come into the picture.
2. If a thread wants to execute then synchronized method on the given object. First, it has to get a lock-in that object. Once the thread got the lock then it is allowed to execute any synchronized method on that object.
3. Once method execution completes automatically thread releases the lock.
4. Acquiring and release lock internally is taken care of by JVM and the programmer is not responsible for these activities.

**Class level lock** :

1. Every class in java has a unique lock which is nothing but a class level lock.
2. If a thread wants to executes a static synchronized method, then the thread requires a class level lock. Once a thread got the class level lock, the it is allowed to execute any static synchronized method of that class.
3. Once method execution completes automatically thread releases the lock.

 