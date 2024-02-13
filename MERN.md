```
npm i slugify
npm i nodemon --save-dev   (This is to specify that this is a developement dependency)
npm i nodemon --global     (To install it globally)
npm run start              (first you have to define a script named "start" under "scripts"
                            attribute in package.json and write "nodemon index.)

```

## What is Node.JS ?
>> Node.JS is a javascript runtime built on google's open source V8 JS Engine
>> In simple language, node js is more like a container(a runtime environment) that will be containing our JS code which will be executed by V8 JS Engine

## When to use and When not to use Node.JS ?
>> It is event-driven, non-blocking I/O model which makes it efficient for handling concurrent connections/requests. e.g : chat applications, gaming applications, etc.
>> It is not suitable where there is CPU intensive operations will be done on server side e.g: video encoding, etc.
>> It is also not suitable in applications with complex business logic

## What is REPL ?
>> it stands for Read Eval Print Loop.

## Importing of modules :
>> When you call `require("module-name")`, Node.js searches for that module.
>> if that module is a core module, then Node.js loads it directly.
>> if it is not a core module, then it searches in "node_modules" folder and further.
>> Once a module is loaded, Node.js caches it.
>> subsequent calls to require() with same name will not load that module again and again. Instead, Node.js returns cached module experts.
>> this helps improving application performance.

## Exporting of modules :
>> When you create a module in Node.js, you can typically export variables, functions, objects that you want to make available to other parts of your application.
>> You can export values using `module.exports` 

## What is the difference between Node.js and Express :
>> Node.js is a JavaScript runtime environment for executing JavaScript code on the server side.
>> Express.js is a web application framework for Node.js, providing additional features like routing, middleware and request handling and tools for building web applications and APIs.

## What is npm ?
>> It stands for Node Package Manager
>> It is a command line interface app which automatically comes with node.js.
>> It is a default package manager for node.js
>> It is used to manage dependencies and install open source packages 