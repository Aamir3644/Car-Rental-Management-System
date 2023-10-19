## Java Memory Management 
>> 1) Heap : When a new keyword is used, object is assigned a space in heap, but the reference of the same exists onto the stack
   2) Method Area : The Method Area is used to store class structures, method data, and static fields.
   3) JVM Stack : The Stack is used for managing method calls and storing local variables and parameters also. The references to the objects are also stored onto the stack.
   4) Native Method Stack : Native method are basically the methods which are written in languages other than Java like C, C++ and interact directly with the OS. Native Method Stack is similarly like JVM Stack but it is specifically used for Native Method Calls.
   5) PC Registers : It stores the address of the next instruction thats gonna get executed. It keeps track of the next instruction to be executed.


## Thread 
>> Threads are light weight processes within a process.