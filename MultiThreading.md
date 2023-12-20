## Java Memory Management 
>> 1) Heap : When a new keyword is used, object is assigned a space in heap, but the reference of the same exists onto the stack
   2) Method Area : The Method Area is used to store class structures, method data, and static fields.
   3) JVM Stack : The Stack is used for managing method calls and storing local variables and parameters also. The references to the objects are also stored onto the stack.
   4) Native Method Stack : Native method are basically the methods which are written in languages other than Java like C, C++ and interact directly with the OS. Native Method Stack is similarly like JVM Stack but it is specifically used for Native Method Calls.
   5) PC Registers : It stores the address of the next instruction thats gonna get executed. It keeps track of the next instruction to be executed.


## Thread 
>> Threads are light weight processes within a process.

## Thread Life Cycle :  
``` 
(1) New: This is the initial state when a thread is created but not yet started.
     You create a new thread by instantiating a Thread object, but it doesn't start running until you call its start() method.
(2) Runnable: A thread enters the runnable state when the start() method is called.
          In this state, the thread is ready to run, but the operating system has not yet selected it to be the running thread.
(3) Blocked: A thread moves to the blocked state when it wants to access an object that another thread has locked.
         The thread will remain in this state until the lock is released by the other thread.
(4)Waiting: A thread enters the waiting state when it waits for another thread to perform a particular action.
         For example, a thread can enter the waiting state by calling the wait() method, waiting for another thread to notify it.
(5)Timed Waiting: A thread enters the timed waiting state when it calls a method with a specified waiting time.
               For instance, calling sleep() or join() with a timeout puts the thread in this state.
(6)Terminated: A thread enters the terminated state when its run() method completes, or when the stop() method is called.
               Once a thread is terminated, it cannot be started again.

```
## Multithreading :
```
- Multithreading in Java enables the concurrent execution of multiple threads, improving performance and responsiveness. Threads can run independently, doing different tasks simultaneously.
- In Java, multithreading can be achieved by extending the Thread class or implementing the Runnable interface.
- When we extend a Thread class, we have to override run() method and when we implement Runnable Interface, we have to implement run() method.

```
