## Introduction

JavaScript was created in 1995 by `Brendan Eich` at Netscape in just 10 days, initially named Mocha, then LiveScript, and finally JavaScript for marketing purposes. It was standardized as ECMAScript (ES) in 1997 to unify browser implementations. Today, it's the most widely used language, powering everything from frontend apps to backend services and cloud functions.

## How Javascript runs in Browser

When you open a webpage, the browser loads the HTML and starts executing any JavaScript through its JavaScript engine (e.g., V8 in Chrome, SpiderMonkey in Firefox).

Step-by-Step Flow

1. Parsing: The javascript code is parrsed into token tree structure called Abstract Syntax Tree (AST)

2. Interpratation: The AST is then converted to Byte-Code

3. Conversion to Machine Code: The Byte-Code is optimized and converted to machine code

`Note:` Conversion from javascript code to bytecode is at once, while execution of code is line by line

**Did You Know**\
JS is single-threaded (one thing at a time), but it handles async tasks using event loop + callback queue.

## JavaScript Event Loop & Async Execution

JavaScript is **single-threaded**, meaning it executes one operation at a time in a **call stack**. However, through browser-provided **Web APIs** and the **event loop**, JavaScript achieves **non-blocking asynchronous behavior**.

#### 1. Call Stack

- Stack data structure
- Tracks function execution
- Functions are pushed and popped as they begin and finish

#### 2. Web APIs (Browser/Node.js)

- Not part of core JavaScript
- Include: `setTimeout`, `fetch`, DOM events, etc.
- Handle async tasks separately from the call stack

#### 3. Callback Queue

- Holds completed async callbacks waiting to be run
- First-in, first-out (FIFO)

#### 4. Event Loop

- Constantly checks if the **call stack is empty**
- If empty, it **pushes the next callback** from the queue onto the stack

Example

```js
setTimeout(() => {
  console.log("Timeout!");
}, 0);

for (let i = 0; i < 1e9; i++) {} // Heavy task

console.log("Done");
```

OUTPUT

```
Done
Timeout!
```

#### Why?

- `setTimeout` sends callback to Web API
- After 0ms, callback moves to **callback queue**
- Call stack is **still busy** (loop)
- Event loop waits for stack to clear
- Only then the callback is **executed**

<p align="center">
  <img src=static/Javascript-event-loop.png alt="Event Loop" width="400" height="auto">
</p>

#### Key Take Away

- JavaScript code is first parsed and compiled to bytecode, then executed step by step.
- Core Javascript is synchronous & single-threaded
- Functions from the `callback queue` move to the call stack only when it is empty.
