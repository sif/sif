---
layout: post
title: "Javascript"
categories: javascript
tags: javascript scripting_languages scripting_language
---

* TOC
{:toc}

Bookmark: https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/use-the-spread-operator-to-evaluate-arrays-in-place

https://lp.jetbrains.com/academy/learn-javascript/

https://natureofcode.com

"ES6 stands for ECMAScript 6. ECMAScript was created to standardize JavaScript, and ES6 is the 6th version of ECMAScript, it was published in 2015, and is also known as ECMAScript 2015."

## Basics

works on media like images, videos, audio, canvas

Manipulating CSS



<a href="https://github.com/sif/sif/raw/main/files/post_files/breakout.html">Breakout</a>

<img src="https://github.com/sif/sif/raw/main/files/post_files/tictactoe.png" />



### Variables & Data Types

String
Number
Boolean
Array
Object

```
let number = parseInt("123", 10) // 123
let binaryNumber = parseInt("1111", 2) // 15
```

typeof()

hoisting, the act of using a variable before declaring it

### Operators

```
+
-
*
/
++
--
=
==
===
!=
!==
||
&&
<
?
<=
>=
```

### Loops & Conditionals

For
If
Else
Do
While
Break

### Functions

closure



### Error Handling

Try-Catch-Finally
Throw
Exceptions



### Debugging

Console.log
Console.trace
Console.table



### Events

Event Listeners
On Event
Click Events



### Data Storage

Localstorage

File system



### Asynchronous

Ajax, Async function, Workers, etc.

callback

"An async function is a function declared with the async keyword, and the await keyword is permitted within them. The async and await keywords enable asynchronous, promise-based behavior to be written in a cleaner style, avoiding the need to explicitly configure promise chains."

"The promise will always log pending as long as its results are not resolved yet. You must call .then on the promise to capture the results regardless of the promise state (resolved or still pending):"
"Why is that?

Promises are forward direction only; You can only resolve them once. The resolved value of a Promise is passed to its .then or .catch methods."
https://stackoverflow.com/questions/38884522/why-is-my-asynchronous-function-returning-promise-pending-instead-of-a-val



## Advanced

JavaScript Bridge

GraphQL

WebGL



### Security

CSRF, encryption, injection, CORS, etc.



## Webpack



## TypeScript

TSX is typescript file using JSX syntax

strongly typed javascript



- create a page
- add an ejs file to route
- add a views file
- add a line to server.js



## Server-Side JavaScript



### Node.js

querystring

Puppeteer, used to control Chrome or Chromium

`yarn config set --home enableTelemetry 0`

Express - web framework for Node.js



## Client-Side JavaScript



### axios

https://zetcode.com/javascript/axios/

axios is a promise based HTTP client

axios makes it easy to send asynchronous HTTP requests to REST endpoints and perform CRUD operations

It can be used in plain JavaScript or with a library such as Vue or React


