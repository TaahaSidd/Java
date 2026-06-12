# Part  - 13 - Daemon Thread

A daemon thread is a background thread in Java that supports user threads and does not prevent the JVM from exiting when all user threads finish. It is ideal for background tasks like monitoring, logging and cleanup.
1. Runs in the background to support user(non-daemon) threads.
2. JVM exits automatically when all user threads finish.
3. Created using the Thread class and marked as daemon with setDaemon(true).
4. setDaemon(true) must be called before starting the thread, or it throws IllegalThreadStateException.
5. Common examples: Garbage Collector (GC) and Finalizer Thread.
```
class DaemonThread extends Thread{
    public void run(){
        Sop(getName() + "is running as a daemon thread.");
    }
}

public class test{
    public static void main(String[] args) throws InterruptedException{
        DaemonThread t1 = new DaemonThread();
        t1.setDaemon(true); //marking as Daemon
        t1.setName("Daemon-1");
        t1.start();


        Thread.sleep(100); //giving JVM some time to run daemon thread
    }
}

O/P -> Daemon-1 is running as daemon thread.
```
**Explanation** :
1. t1 is marked as daemon thread using setDaemon(true)
2. Once the main threads ends, the JVM terminates all daemon threads automatically.

**Methods Used** :
1. void ```setDaemon(boolean on)```: Marks a thread as daemon or user thread. Must be called before start().
2. boolean ```isDaemon()``` : Checks whether a thread is daemon.


**Notes** :
1. A thread inherits the daemon status of the thread that creates it.
2. Daemon threads should not be used for tasks requiring completion, such as writing to a file or updating a database.
3. JVM terminates all daemon threads abruptly without performing cleanup operations.
4. 