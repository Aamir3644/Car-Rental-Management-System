Read This Also : https://www.interviewbit.com/javascript-interview-questions/
For Closure Concept in JS : https://www.w3schools.com/js/js_function_closures.asp

## What is JavaScript ? What is JavaScript Engine ?

> > JavaScript is a programming language that makes static web pages dynamic and interactive.
> > JavaScript Engine is a program present in Web browser that executes JavaScript Code.

## What is ECMA Script ?
>> It is a scripting language specification on which javascript is built. 

## Compiled and Interpreted ?

> > Compiled Languages are compiled first and then executed later, usually don't compile when there is an error
> > e.g : C, Java, Rust
> > Interpreted languages are executed line by line, they can run partially if there is a error
> > e.g : JavaScript, Python

## What is difference between var, let and const keyword ?

> > var creates a function scoped variable.
> > let creates a block scoped variable.
> > const creates a block scoped variable but it can be assigned only once and its value can not be changed afterwards.

## What are Types of Data Types in JavaScript ?

> > Primitive : Number, Strings, Booleans, Undefined, Null
> > Non-Primitive : Object, Array, Function, Date, RegExp

## What is the difference between primitive and non-primitive data types ?

> > Primitive :

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

> > Non-Primitive :

```
   Non-Primitive data types can hold multiple value.
   They are mutable and their values can be changed.
```

## What is difference between Spread and Rest Operator in JS ?

> > Spread Operator :

```
   Spread Operator is used to spread or expand elements from an iterable like an array into indivisual elements.
   Spread Operator is Used for :
   (1) Copying an Array
```

```js
      const arr = [1,2,3];
      const arr1 = [..arr]; // this will copy the elements of arr to arr1
```

```
   (2) Merging Arrays
```

```js
const arr = [1, 2, 3];
const arr1 = [4, 5, 6];
const mergedArray = [...arr, ...arr1];
console.log(mergedArray); // [1,2,3,4,5,6]
```

```
   (3) Passing Multiple Arguments to a function
```

```js
const arr = [1, 2, 3, 4];
sum(...arr);
function sum(a, b, c, d) {
  console.log(a + b + c + d);
}
```

> > Rest Operator :

```
   Rest Operator is used in function parameters to collect all remaining arguments into an array.
```

```js
display(1, 2, 3, 4, 5);
function display(a, b, ...restElements) {
  console.log(a); // 1
  console / log(b); // 2
  console.log(restElements); // [3,4,5]
}
```

## What is the difference between map() and forEach() ?

> > Map :

```
   map() method is used when you want to modify each element of an array and create a new array with modified values.
```

```js
let arr = [1, 2, 3, 4];
let newArray = arr.map((e) => e * 2);
console.log(newArray);
```

> > forEach :

```
   forEach() basically used to iterate over a array.
   forEach() is used when you want to perform some operation on each element without creating a new array.
```

```js
let arr = [1, 2, 3, 4];
arr.forEach((e) => {
  console.log(e * 2);
}); // Does not return anything
```

## Explain Pass By Value & Pass By Reference in JS :

> > Pass By Value :

```
   In JS, Primitive Data Types are always passed by value.
   Primitive data types when passed to another variable, are passed by value. Instead of just assigning the same address to
   another variable, the value is passed and new space of memory is created.
```

```js
var y = 10; // to this value 10 memory is allocated and address is returned. It means that y is pointing towards address
//of value 10 not value itself
var z = y; // On this line, to value 10 a new memory location is allocated and that new memory address is returned
// It means that both variable y & z are pointing towards different memory location which has same value.
```

> > Pass By Reference :

```
   In JS, Non-Primitive Data Types are always passed by reference.
   In the below example, the assign operator directly passes the location of the variable obj to the variable obj2. In other words, the reference of the variable obj is passed to the variable obj2.
```

```js
var obj = { name: "Vivek", surname: "Bisht" };
var obj2 = obj; // obj and obj2 are pointing towards same memory location. so changing any one of them will change other
```

## What is Hoisting ?

> > Hoisting is a behavior in JavaScript where variable and function declarations are moved to the top of their containing scope during the compilation phase, before the code is executed. This means that you can use a variable or call a function before it has been declared in your code, and JavaScript will still work, However, the initialization (assigning a value) remains in place.
> > Example :

```js
console.log(x); // undefined
var x = 5;
```

## What is Temporal Dead Zone (TDZ) ?
>> Hoisting moves variable declarations (those declared with var) to the top of their containing scope during the compilation phase. When using var, variables are initialized with undefined, so they can be accessed before their actual declaration in the code. However, when using let or const, variables are hoisted to the top of their block scope but remain uninitialized in a state known as the Temporal Dead Zone (TDZ). Attempting to access them before their declaration in the code results in a ReferenceError.

## What is the difference between null and undefined?

> > null is an explicitly assigned value that represents the absence of any object value, while undefined indicates that a variable has been declared but hasn't been assigned a value.

## Explain the difference between == and === in JavaScript.

> > == is a loose equality operator that performs type coercion, while === is a strict equality operator that checks both value and type.

## What is DOM ?

> > The DOM (Document Object Model) acts as an interface provided by web browsers, allowing developers to use languages like JavaScript to interact with and modify the structure and content of web documents, such as HTML or XML. The DOM represents web pages as a hierarchical tree of objects, with each element, attribute, or text being a node in the tree. Developers can programmatically access, change, and respond to user interactions, making it easy to create dynamic and interactive web applications.

## What is an Immediately Invoked Function in JavaScript?

> > An Immediately Invoked Function ( known as IIFE and pronounced as IIFY) is a function that runs as soon as it is defined.

Syntax of IIFE :

```js
      (function() { Do something;})() ;
```

## What is Closures in JS?

> > Closures are an ability of a function to remember the variables and functions that are declared in its outer scope.

```js
function randomFunc() {
  var obj1 = { name: "Vivian", age: 45 };

  return function () {
    console.log(obj1.name + " is " + "awesome"); // Has access to obj1 even when the randomFunc function is executed
  };
}
var initialiseClosure = randomFunc(); // Returns a function
initialiseClosure();
```

- When the function randomFunc() runs, it seems that the returning function is using the variable obj1 inside it:
  Therefore randomFunc(), instead of destroying the value of obj1 after execution, saves the value in the memory for further reference. This is the reason why the returning function is able to use the variable declared in the outer scope even after the function is already executed.
  This ability of a function to store a variable for further reference even after it is executed is called Closure.

## Scope Chain :

> > Scope : Scope in JS determines the accessibility of variables and functions at various parts of one’s code.
> > In general terms, the scope will let us know at a given part of code, what are variables and functions we can or cannot access.

> > Scope Chain : JavaScript engine also uses Scope to find variables.

                 If the javascript engine does not find the variable in local scope, it tries to check for the variable in the outer scope. If the variable does not exist in the outer scope, it tries to find the variable in the global scope.

## Synchronous & Asynchronous in JS ?

> > Asynchronous JavaScript is the programming method where operations are run independently allowing the program to continue running while waiting for certain tasks to complete. Synchronous JavaScript is the programming approach where tasks of a program are executed sequentially one at a time.

## Call Stack, Callback queue and Event Loop :

> > Call Stack :

```
 In JavaScript, the call stack is like a stack of function calls. When a function is called, it's added to the top of the call stack. When that function finishes executing, it's removed from the stack.
```

> > Callback Queue :

```
The callback queue in JavaScript is where functions wait for their turn to be executed.
When an asynchronous function completes its task, it places its callback function into the callback queue. These functions are waiting for their turn to be executed after the current call stack is empty.
```

> > Event Loop :

```
Imagine you're at a party where there's a dance floor and a DJ. People who want to dance give their song requests to the DJ. The DJ plays the songs one after another, making sure everyone gets a turn. The event loop in JavaScript is like this DJ; it keeps track of the call stack and the callback queue.
```

```
The event loop constantly checks if the call stack is empty. If it's empty, it takes the first function from the callback queue and pushes it onto the call stack for execution. This process continues, ensuring that asynchronous functions are executed when their turn comes, without blocking the main execution thread.
```

```
When a function with asynchronous operations is called, it executes synchronously, while the asynchronous operations are offloaded to the browser APIs. Once an asynchronous operation completes, its callback is placed in the callback queue. The event loop continuously checks if the call stack is empty. If it is, it takes the first callback from the queue and pushes it onto the call stack for execution. This process ensures non-blocking handling of asynchronous tasks in JavaScript.
```

## What is Callback in JS ?

> > In Javascript, the Callback function is a type of function that is passed as an argument to some other function.

```js
function sum(num1, num2, fnToCall) {
  var sum = num1 + num2;
  fnToCall(sum);
}

function displaySum(sum) {
  console.log("Sum is " + sum);
}

sum(1, 2, displaySum);
```

## What is Callback Hell ?

> > Callback hell is a phenomenon in which the nesting of multiple Callbacks is present inside a single function. It is also called as Pyramid of Doom.

## What is setTimeout and setInterval ?

> > setTimeout is used to schedule the execution of a function or a code snippet after a specified delay (in milliseconds).
> > It takes two arguments: a function or code snippet to execute and the delay in milliseconds.

> > setInterval is used to repeatedly execute a function or code snippet at a specified interval (in milliseconds) until it is canceled.
> > It also takes two arguments: a function or code snippet to execute and the interval in milliseconds.

## What is Promise ?

> > A Promise is an object representing the eventual completion or failure of an asynchronous operation.
> > It allows you to work with asynchronous code in a more structured and predictable manner, making it easier to handle complex asynchronous flows.

- There are 3 States of Promise Object :
  1.  Pending
  2.  Fulfilled
  3.  Rejected

> The Promise object supports two properties: state and result.

- While a Promise object is "pending" (working), the result is undefined.
- When a Promise object is "fulfilled", the result is a value.
- When a Promise object is "rejected", the result is an error object.

E.g:

```js
function fetchData() {
  return new Promise((resolve, reject) => {
    // Simulating an asynchronous operation (e.g., fetching data from an API)
    setTimeout(() => {
      const data = "Some fetched data";
      // Simulating a successful response
      resolve(data);
    }, 2000);
  });
}

// Using the fetchData function with a Promise
fetchData()
  .then((result) => {
    console.log("Data fetched successfully:", result);
    // assuming that we are doing something with the fetched data
  })
  .catch((error) => {
    console.error("Error fetching data:", error);
    // Handle the error appropriately
  });
```

## What is async and await ?

> > The async keyword is used to define a function as asynchronous. An async function always returns a Promise implicitly, even if you don't explicitly create one.
> > Inside a async function, we can use "await" keyword to pause the execution of the function, until the asynchronous operation gets completed and promise is resolved. The thing is that we will be operating on that data (e.g: console.log(data))in the next coming lines so If we do not use await keyword then it will not wait till promise is resolved cause it already got a promise object. it will print the promise object received which will have pending state. so thats the main use case of await keyword.
> > await keyword can only be used in async function.
> > So basically , They provide a way to work with Promises in a more synchronous-like fashion, eliminating the need for explicit chaining of .then() methods.
> > Examples :

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

```js
async function fetchData() {
  return new Promise((resolve, reject) => {
    // Simulating an asynchronous operation (e.g., fetching data from an API)
    setTimeout(() => {
      const data = "Some fetched data";
      // Simulating a successful response
      resolve(data);
    }, 2000);
  });
}

async function fetchDataAndProcess() {
  try {
    const data = await fetchData();
    console.log("Data fetched successfully:", data); //if we do not use await keyword on the above line, data will be printed as "Promise<Pending>"
  } catch (error) {
    console.error("Error fetching data:", error);
    // Handle the error appropriately
  }
}

// Using the fetchDataAndProcess function with async/await
fetchDataAndProcess();
```

> > it's important to understand that the program as a whole isn't executing synchronously. Other non-blocking operations can still occur while waiting for the asynchronous operation. It's only the code within the async function that appears to execute in a more synchronous fashion.

## What is the difference between fetch API and axios ?

> > Fetch API :

```
    Fetch API is a built-in web API in modern browsers that allows making network requests using the fetch() function.
    Fetch API uses promises so we can use .then(), .catch() to work with asynchronous code.
```

Example of How to fetch an API using fetch API :

```js
async function fetchDataFromAPI() {
  const response = await fetch("https://api.example.com/data");

  if (!response.ok) {
    throw new Error("Failed to fetch data from the API");
  }

  const data = await response.json();
  return data;
}

async function fetchData() {
  try {
    const data = await fetchDataFromAPI();
    console.log("Fetched data:", data);
    // Process the fetched data
  } catch (error) {
    console.error("Error fetching data:", error.message);
    // Handle the error appropriately
  }
}

fetchData();
```

> > Axios :

```
    Axios is a third party library which is used for making HTTP requests in JS.
    Axios provides additional features like JSON parsing, etc.
    Axios use promises like fetch API.
```

```js
import axios from "axios";

async function fetchData() {
  try {
    const response = await axios.get("https://api.example.com/data");

    // Assuming the response contains JSON data, you can access it using response.data
    console.log("Data fetched successfully:", response.data);

    // Process the fetched data
  } catch (error) {
    // Handle errors
    console.error("Error fetching data:", error.message);
  }
}

// Call the fetchData function
fetchData();
```
