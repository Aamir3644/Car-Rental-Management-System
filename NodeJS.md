## What is Node.JS ?

> > Node.JS is a javascript runtime built on google's open source V8 JS Engine
> > In simple language, node js is more like a container(a runtime environment) that will be containing our JS code which will be executed by V8 JS Engine

## What is npm ?

> > It stands for Node Package Manager
> > It is a command line interface app which automatically comes with node.js.
> > It is a default package manager for node.js
> > It is used to manage dependencies and install open source packages

## When to use and When not to use Node.JS ?

> > It is event-driven, non-blocking I/O model which makes it efficient for handling concurrent connections/requests. e.g : chat applications, gaming applications, etc.
> > It is not suitable where there is CPU intensive operations will be done on server side e.g: video encoding, etc.
> > It is also not suitable in applications with complex business logic

## What is REPL ?

> > it stands for Read Eval Print Loop.

## Importing of modules :

> > When you call `require("module-name")`, Node.js searches for that module.
> > if that module is a core module, then Node.js loads it directly.
> > if it is not a core module, then it searches in "node_modules" folder and further.
> > Once a module is loaded, Node.js caches it.
> > subsequent calls to require() with same name will not load that module again and again. Instead, Node.js returns cached module experts.
> > this helps improving application performance.

## Exporting of modules :

> > When you create a module in Node.js, you can typically export variables, functions, objects that you want to make available to other parts of your application.
> > You can export values using `module.exports`

## What is the difference between Node.js and Express :

> > Node.js is a JavaScript runtime environment for executing JavaScript code on the server side.
> > Express.js is a web application framework for Node.js, providing additional features like routing, middleware and request handling and tools for building web applications and APIs.

## What is a Middleware ?

> > Middleware is a function that sits between two layers of web application. It intercepts data as it flows between them and checks it, modify it if needed and goes to next middleware in the chain.
> > When a request comes to web application, it goes through implemented middlewares before reaching route handler.
> > Middleware functions has access to request object('req') and response object ('res'). They can modify the request and response objects, end the request-response cycle, or call the next middleware function in the stack.
> > The middleware functions do tasks like authentication, parsing request bodies, handling CORS headers.
> > app.use() is used to mount the middlewares in express web application.

```js
app.use((req, res, next) => {
  console.log("This middleware is executed for every incoming request");
  next(); // Call the next middleware function in the stack
});
```

> > next() : This function is passed as an argument to each middleware function and is used to pass control to the next middleware function in the stack. When called, it transfers control to the next middleware function.

## What is a Global Catch ?

> > It is known as global error handler, which is used for catching unhandled errors that occur anywhere in an application. It is a special type of middleware function which has 4 arguments.

```js
app.use((err, req, res, next) => {
  res.status(500).send("Something went wrong!");
});
```

## What is Zod ?

> > It is a popular third party library that makes the process of input validation easy.

```js
const zod = require("zod");
// requirements are as follows
// email : should be string : should look like email
// password : should have atleast 8 letters

const schema = zod.object({
  email: zod.string().email(),
  password: zod.string().min(),
});

const response = schema.safeParse(obj);

// if it follows all input validations it will return a object which wil have a attribute named {success : true} and if it does not then {success : false}

console.log(response.success);
```

## JSON Web Token Library :

> > JWT (JSON Web Token) :

- It is a compact and self-contained way to represent information between two parties in a secure manner. JWTs are commonly used for authentication and authorization in web applications.

> > "jsonwebtoken" Library :

- The jsonwebtoken library is a popular Node.js library used for creating, verifying, and decoding JWTs.

# Usage of jsonwebtoken library:

> (1) Creating a JWT (Signing) :

- To create a JWT, you typically need a payload (data you want to include in the token) and a secret key.

```js
const jwt = require("jsonwebtoken");

// Payload data
const payload = {
  userId: "123456",
  username: "example_user",
};

// Secret key to sign the token
const secretKey = "your_secret_key";

// Creating a JWT
const token = jwt.sign(payload, secretKey, { expiresIn: "1h" });
console.log(token);
```

> (2) Verifying the token :

- We use the jwt.verify() method to verify the token. If the signature is valid and the token has not expired, it returns the decoded payload.
- If the token is invalid (e.g., tampered with or expired), it throws an error.

```js
const verifiedToken = jwt.verify(token, secretKey);
console.log(verifiedToken);
```

> (3) Decoding a JWT :

- You can also decode a JWT to access its payload without verifying its signature.

```js
const decodedToken = jwt.decode(token);
console.log(decodedToken);
```

## What is Debouncing :
>> Debouncing is commonly used in scenarios where you want to optimize performance and avoid unncessary request sending to server caused by frequent event triggering.
>> scenarios where debouncing can be used :
>> (1) In search functionality : for suggestion of words that user is typing, it will send request to server for fetching suggesting words, to delay the calling of that function which is making the request after every keystroke, debouncing can be applied.
>> (2) Input field autocomplete
```js
      let timeout;
      function debounceFunction(){
          //At first, value of "timeout" variable will be undefined.
          //clearTimeout is a function which takes timeout Id as parameter and cancels the timer.
          // whenever the debounce function will get called for the first time, it will not cancel any timer cause "timeout" variable does not have timeoutID, it is undefined.
          // when debounce function gets called before the timer gets completed, it will cancel the timer and in next line it will set another timer.
          clearTimeout(timeout);

          // setTimeout returns a unique timeout ID which can be used to cancel the timer using clearTimeout()
          timeout = setTimeout(function(){
            RequestFunction();
          },500);
      }
```

## Structure of a Backend Express Web Server:
- (1) index.js
- (2) db
- (3) middlewares
- (4) routes