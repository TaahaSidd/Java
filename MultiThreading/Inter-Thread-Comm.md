# Part - 10 - Inter-thread communication


Inter-thread communication in java enables threads to coordinate their execution by signaling each other during runtime. It is mainly used when multiple threads depend on shared resources or need to work in a specific sequence.
1. Helps avoid busy waiting and improves resource utilization.
2. Ensures proper execution order among dependent threads.
3. Commonly used in producer-consumer type problems.
4. Inter-thread communication is also known as Cooperation in java.

**Polling** :

Polling is the process of repeatedly checking a condition in a loop until it becomes true. Once the condition is satisfied, the required action is performed. It is commonly used when one thread waits for another to produce or update data.

**Problem with Polling** : 
1. Wastes CPU cycles due to continuous condition checking.
2. Reduces efficiency and slows down overall execution.
3. Keeps the thread busy instead of allowing others tasks to run.

**How java handles Multithreading Handle Polling** :

Java avoids polling by using built-in communication methods that allow threads to wait efficiently instead of continuously checking a condition. These methods are defined in the object class and must be used within a synchronized context.

1. wait() : Releases the lock and puts the thread into a waiting state until notified.
2. notify() : Wakes up one waiting thread (does not release the lock immediately).
3. notifyAll() : Wakes up all waiting threads on the same object.

These methods should only be called in synchronized area to avoid an ```IllegalMonitorStateException```

**Why wait(), notify() and notifyAll() are in Object class rather than Thread class.** :

1. Object-Level Locking : In java every object has a lock associated with it. When a thread needs to perform inter-thread communication, it must interact with the monitor lock of the specific object being shared.
2. Versatility : Threads may need to call these methods on any java objects, not just objects of a specific Thread subclass. By placing these methods in the Object class, they become available for every object in Java language.
3. Comparison with Thread-specific methods : Methods like start() or join() are specific to the lifecycle of a thread and are called only on thread objects, which is why they belong in the thread class. In contrast, wait() and notify() are mechanisms for communication between threads about the state of any arbitrary object, making the object class the most appropriate location for them