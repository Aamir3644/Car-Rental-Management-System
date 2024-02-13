Read This Also : https://www.interviewbit.com/javascript-interview-questions/
For Closure Concept in JS : https://www.w3schools.com/js/js_function_closures.asp

## What is JavaScript ? What is JavaScript Engine ?
>> JavaScript is a programming language that makes static web pages dynamic and interactive.
>> JavaScript Engine is a program present in Web browser that executes JavaScript Code.

## What is difference between var, let and const keyword ?
>> var creates a function scoped variable. 
>> let creates a block scoped variable.
>> const creates a block scoped variable but it can be assigned only once and its value can not be changed afterwards.

## What are Types of Data Types in JavaScript ?
>> Primitive : Number, Strings, Booleans, Undefined, Null
>> Non-Primitive : Object, Array, Function, Date, RegExp

## What is the difference between primitive and non-primitive data types ?
>> Primitive :
```
   Primitive data types can hold only single value.
   Primitive data types are immutable. 
``` 
   ```js
         let age = 25;
         age = 30;
   ```
```
   In above when age is assigned value 25, a memory is allocated to that value 25. When that same age variable is assigned value 30 then the value 25 which is present in previous allocated memory is not updated. A different memory is allocated with value 30 and that age variable will point to it. So that why it is said that primitive data types are immutable.
```
>> Non-Primitive :
```
   Non-Primitive data types can hold multiple value.
   They are mutable and their values can be changed.
```

## What is difference between Spread and Rest Operator in JS ?
>> Spread Operator :
```
   Spread Operator is used to spread or expand elements from an iterable like an array into indivisual elements.
   Spread Operator is Used for : 
   1) Copying an Array
```
```js
      const arr = [1,2,3];
      const arr1 = [..arr]; // this will copy the elements of arr to arr1
```
```
   2) Merging Arrays
```
```js
      const arr  = [1,2,3];
      const arr1 = [4,5,6];
      const mergedArray = [...arr,...arr1];
      console.log(mergedArray); // [1,2,3,4,5,6]
```
```
   3) Passing Multiple Arguments to a function
```
```js
      const arr = [1,2,3,4];
      sum(...arr);
      function sum(a,b,c,d){
         console.log(a+b+c+d);
      }
```

>> Rest Operator :
```
   Rest Operator is used in function parameters to collect all remaining arguments into an array.
```
```js
      display(1,2,3,4,5);
      function display(a, b, ...restElements){
         console.log(a);  // 1
         console/log(b);  // 2
         console.log(restElements) // [3,4,5]
      }
```

## What is the difference between map() and forEach() ?
>> Map :
```
   map() method is used when you want to modify each element of an array and create a new array with modified values.
```
```js
      let arr = [1,2,3,4];
      let newArray = arr.map((e) => e*2);
      console.log(newArray);
```
>> forEach :
```
   forEach() basically used to iterate over a array.
   forEach() is used when you want to perform some operation on each element without creating a new array.
```
```js
      let arr = [1,2,3,4];
      arr.forEach((e) => {
         console.log(e*2);
         }); // Does not return anything
```

## Explain Pass By Value & Pass By Reference in JS :
>> Pass By Value :
```
   In JS, Primitive Data Types are always passed by value.
   Primitive data types when passed to another variable, are passed by value. Instead of just assigning the same address to
   another variable, the value is passed and new space of memory is created.
```
```js
      var y = 10; // to this value 10 memory is allocated and address is returned. It means that y is pointing towards address
                  //of value 10 not value itself
      var z = y ; // On this line, to value 10 a new memory location is allocated and that new memory address is returned
                  // It means that both variable y & z are pointing towards different memory location which has same value.
```

>> Pass By Reference :
```
   In JS, Non-Primitive Data Types are always passed by reference.
   In the below example, the assign operator directly passes the location of the variable obj to the variable obj2. In other words, the reference of the variable obj is passed to the variable obj2.
```
```js
      var obj = { name: "Vivek", surname: "Bisht" };
      var obj2 = obj;   // obj and obj2 are pointing towards same memory location. so changing any one of them will change other
```

## What is Hoisting ?
>> Hoisting is a behavior in JavaScript where variable and function declarations are moved to the top of their containing scope during the compilation phase, before the code is executed. This means that you can use a variable or call a function before it has been declared in your code, and JavaScript will still work, However, the initialization (assigning a value) remains in place.
Example : 
   ```js
            console.log(x); // undefined 
            var x = 5; ``
   ```

## What is the difference between null and undefined?
>> null is an explicitly assigned value that represents the absence of any object value, while undefined indicates that a variable has been declared but hasn't been assigned a value.

## Explain the difference between == and === in JavaScript.
>> == is a loose equality operator that performs type coercion, while === is a strict equality operator that checks both value and type.

## What is DOM ?
>> The DOM (Document Object Model) acts as an interface provided by web browsers, allowing developers to use languages like JavaScript to interact with and modify the structure and content of web documents, such as HTML or XML. The DOM represents web pages as a hierarchical tree of objects, with each element, attribute, or text being a node in the tree. Developers can programmatically access, change, and respond to user interactions, making it easy to create dynamic and interactive web applications.

## What is an Immediately Invoked Function in JavaScript?
>> An Immediately Invoked Function ( known as IIFE and pronounced as IIFY) is a function that runs as soon as it is defined.

Syntax of IIFE :
```js 
      (function() { Do something;})() ;
```

## What is Closures in JS?
>> Closures are an ability of a function to remember the variables and functions that are declared in its outer scope.
```js 
         function randomFunc(){ 
         var obj1 = {name:"Vivian", age:45}; 

         return function(){ 
         console.log(obj1.name + " is "+ "awesome");  // Has access to obj1 even when the randomFunc function is executed
            } 
         }
         var initialiseClosure = randomFunc();  // Returns a function
         initialiseClosure();
```
- When the function randomFunc() runs, it seems that the returning function is using the variable obj1 inside it:
Therefore randomFunc(), instead of destroying the value of obj1 after execution, saves the value in the memory for further reference. This is the reason why the returning function is able to use the variable declared in the outer scope even after the function is already executed.
This ability of a function to store a variable for further reference even after it is executed is called Closure. 

## Scope Chain :
>> Scope : Scope in JS determines the accessibility of variables and functions at various parts of one’s code.
In general terms, the scope will let us know at a given part of code, what are variables and functions we can or cannot access.

>> Scope Chain : JavaScript engine also uses Scope to find variables.
                 If the javascript engine does not find the variable in local scope, it tries to check for the variable in the outer scope. If the variable does not exist in the outer scope, it tries to find the variable in the global scope.

## Synchronous & Asynchronous in JS ?
>> Asynchronous JavaScript is the programming method where operations are run independently allowing the program to continue running while waiting for certain tasks to complete. Synchronous JavaScript is the programming approach where tasks of a program are executed sequentially one at a time.  

## What is Event Loop ?
>> Javascript is inherently single threaded, meaning it executes one operation at a time in a sequential manner. When our code contains asynchronous operations like fetching a resource from database or having setaTimeout etc. . Instead of waiting for these operations to complete, JavaScript delegates them to the Event Loop. The Event Loop is a central component of JavaScript's runtime environment. It continually checks a message queue for pending tasks and executes them one by one. Messages are added to the queue when asynchronous operations complete. JS has a Call Stack. It keeps track of the functions being executed at any given moment. When the stack is empty, the Event Loop starts processing messages from the queue.

## What is Callback in JS ?
>> In Javascript, the Callback function is a type of function that is passed as an argument to some other function.

## What is Callback Hell ?
>> Callback hell is a phenomenon in which the nesting of multiple Callbacks is present inside a single function. It is also called as Pyramid of Doom.

## What is setTimeout and setInterval ?
>> setTimeout is used to schedule the execution of a function or a code snippet after a specified delay (in milliseconds).
   It takes two arguments: a function or code snippet to execute and the delay in milliseconds.

>> setInterval is used to repeatedly execute a function or code snippet at a specified interval (in milliseconds) until it is   canceled.
   It also takes two arguments: a function or code snippet to execute and the interval in milliseconds.

## What is Promise ?
>> A Promise is an object representing the eventual completion or failure of an asynchronous operation.
>> It allows you to work with asynchronous code in a more structured and predictable manner, making it easier to handle complex asynchronous flows.

-  There are 3 States of Promise Object : 
   1) Pending
   2) Fulfilled
   3) Rejected

> The Promise object supports two properties: state and result.
- While a Promise object is "pending" (working), the result is undefined.
- When a Promise object is "fulfilled", the result is a value.
- When a Promise object is "rejected", the result is an error object.

## What is async and await ?
>> The async keyword is used to define a function as asynchronous. An async function always returns a Promise implicitly, even if you don't explicitly create one.
-  async functions are used to simplify working with asynchronous code by providing a more linear and readable flow.
-  Inside an async function, you can use the await keyword to pause the execution of the function until a Promise is resolved.It allows you to wait for the result of an asynchronous operation.
-  So basically , They provide a way to work with Promises in a more synchronous-like fashion, eliminating the need for explicit chaining of .then() methods.

```js
            async function exampleAsyncFunction() {
            console.log("Start");

            // Simulate an asynchronous operation using a Promise
            await new Promise((resolve) => {
               setTimeout(() => {
                     console.log("Async operation complete");
                     resolve();
               }, 2000); // Simulating a 2-second delay
            });

               console.log("End");
            }

            console.log("Before async function call");
            exampleAsyncFunction();
            console.log("After async function call");

```
```
      // Output :
      Before async function call
      Start
      After async function call
      Async operation complete
      End
```
>> it's important to understand that the program as a whole isn't executing synchronously. Other non-blocking operations can still occur while waiting for the asynchronous operation. The code after the await expression is not blocked; it's only the code within the async function that appears to execute in a more synchronous fashion.