Read This Also : https://www.interviewbit.com/javascript-interview-questions/
For Closure Concept in JS : https://www.w3schools.com/js/js_function_closures.asp


## What is Hoisting ?
>> Hoisting is a behavior in JavaScript where variable and function declarations are moved to the top of their containing scope during the compilation phase, before the code is executed. This means that you can use a variable or call a function before it has been declared in your code, and JavaScript will still work, However, the initialization (assigning a value) remains in place.
Example : 
            `` console.log(x); `` // undefined 
            `` var x = 5; ``

## What is the difference between null and undefined?
>> null is an explicitly assigned value that represents the absence of any object value, while undefined indicates that a variable has been declared but hasn't been assigned a value.

## Explain the difference between == and === in JavaScript.
>> == is a loose equality operator that performs type coercion, while === is a strict equality operator that checks both value and type.

## What is DOM ?
>> The DOM (Document Object Model) acts as an interface provided by web browsers, allowing developers to use languages like JavaScript to interact with and modify the structure and content of web documents, such as HTML or XML. The DOM represents web pages as a hierarchical tree of objects, with each element, attribute, or text being a node in the tree. Developers can programmatically access, change, and respond to user interactions, making it central to creating dynamic and interactive web applications.

## What is an Immediately Invoked Function in JavaScript?
>> An Immediately Invoked Function ( known as IIFE and pronounced as IIFY) is a function that runs as soon as it is defined.

Syntax of IIFE :
`` (function() {// Do something;})() ;``

## What is Closures in JS?
>> Closures are an ability of a function to remember the variables and functions that are declared in its outer scope.

` function randomFunc(){ `
`  var obj1 = {name:"Vivian", age:45}; `

`  return function(){ `
`    console.log(obj1.name + " is "+ "awesome"); ` // Has access to obj1 even when the randomFunc function is executed
`  } `
`}`
`var initialiseClosure = randomFunc();` // Returns a function
`initialiseClosure();` 

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
   It allows you to work with asynchronous code in a more structured and predictable manner, making it easier to handle complex asynchronous flows.

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
-  So basically , They provide a way to work with Promises in a more synchronous-like fashion, eliminating the need for explicit chaining of 
.then() methods.

## 