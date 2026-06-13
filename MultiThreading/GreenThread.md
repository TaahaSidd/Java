# Part - 14 - Green Thread.

Multi threading concept is implemented by using the following two models.

1. Green Thread model.
2. Native Thread model.

**Green Thread model** :
 
1. In this model, threads are completely managed by JVM without any kind of underlying OS support.
2. These threads are implemented at the application level and managed in user space.
3. They are also called cooperative (user-level) threads.
4. Only one green thread can be processed at a time, Hence, this model is considered many-to-one model. Because of this green threads can run on multi-core processors but cannot take advantage of multiple cores.
5. Synchronization and resources sharing is easier for green threads and hence execution time is also less.

**Native Thread Model** :
1. Threads in this model are managed by the JVM with the help of underlying OS support.
2. These threads are implemented at the OS level (by using OS multithreading API) and managed in kernel space.
3. They are also called non-green (kernel level) threads.
4. Multiple native threads can coexists. Therefore is it also called many-to-many model. Such characteristic of this model allows it to take complete advantage of multi-core processors and execute threads on separate individual core concurrently.
5. Since this model allows multiple threads to be executed simultaneously, thread synchronization and resource sharing become complicated. This increases execution time of threads.
6. All the windows based OS provide support for Native thread model.

Because of its limitations, the Green thread model is deprecated and no longer used. Native Thread model has replaced Green Thread model and it is used widely today. 

Apart from this Thread class in Java has some methods which are deprecated.
1. ```public void stop()``` : This method is deprecated because it is inherently unsafe to use. For example suppose a thread has opened a file and is writing into the file suddenly, if we call stop() method on this thread, then the thread will terminate abruptly and the file will remain open.
2. ```public void suspend()``` : Is is deprecated because it is deadlock prone. Example where a primary thread holds a lock on a object and that threat is suspended. No other thread can get that object level lock until that threat is resumed.
3. ```public void resume()``` : since suspend() is deprecated, resume() is also v.
   

   