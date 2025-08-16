## Basic concepts

| Keyword | Scope    | Reassignable | Redeclarable | Hoisted | Use Case                     |
| ------- | -------- | ------------ | ------------ | ------- | ---------------------------- |
| `var`   | Function | Yes          | Yes          | Yes ✅  | Legacy code                  |
| `let`   | Block    | Yes          | No           | No ❌   | Use for mutable variables    |
| `const` | Block    | No           | No           | No ❌   | Use for constants/references |

#### Global Scope

A variable declared outside of any function or block is in the global scope. It can be accessed from anywhere in the code.

#### Functional Scope

A variable is said to have function scope if it is accessible only within the function where it was declared.

#### Block Scope

A variable has block scope if it is accessible only within a block {} (like if, loop, or function blocks).

Example

```JS
function Greet(){
    if (true){
        var a = 10;
        let b = 20;
    }

    console.log(a)  // 10
    console.log(b)  // Error
}
```

#### Lexical Scope (Static Scope)

JavaScript uses lexical scoping, which means scope is determined by the physical location of variables in the source code — not how or when functions are called.

Example

```JS
function outer() {
  let a = "outer";

  function inner() {
    console.log(a); // Has access to 'a' even though it's not declared inside inner()
  }

  inner();
}
```

**Note:** Variable `a` has `outer` function scope

#### Hoisting

Hoisting is JavaScript’s default behavior of **moving declarations to the top** of their scope before code execution.

- Only **declarations** are hoisted, **not initializations**.
- Applies to **variables** (`var`, `let`, `const`) and **functions**.

With `var`

```js
console.log(a); // undefined
var a = 5;
```

Explanation

```js
var a;
console.log(a); // undefined
a = 5;
```

With `let` / `const`

```js
console.log(b); // ReferenceError
let b = 10;
```

`let` and `const` are hoisted, but exist in a **Temporal Dead Zone (TDZ)** until their declaration line.

The TDZ is the time between:

1. When a variable is hoisted (name reserved in memory), and

2. When the variable is actually declared (initialized) in your code.

During this zone, any attempt to access the variable will throw a ReferenceError.

With `Functions`

```js
greet(); // Works
greet2(); // ReferenceError
greet3(); // ReferenceError

// Function Declaration
function greet() {
  console.log("Hello");
}

// Function Expression
const greet2 = () => {
  console.log("Hello2");
};

// Function Expression
const greet3 = function () {
  console.log("Hello3");
};
```

###### Summary Table

| Type                 | Hoisted | Accessible Before Declaration | Notes                               |
| -------------------- | ------- | ----------------------------- | ----------------------------------- |
| `var`                | ✅ Yes  | ✅ Yes (value = undefined)    | Function-scoped                     |
| `let`, `const`       | ✅ Yes  | ❌ No (in TDZ)                | Block-scoped, safer                 |
| Function Declaration | ✅ Yes  | ✅ Yes                        | Can be called before declaration    |
| Function Expression  | ✅ Yes  | ❌ No (in TDZ)                | Cannot be called before declaration |

#### Closure

A closure is a function that remembers variables from its outer scope, even after that outer function has finished executing.

Closures allow inner functions to access variables defined in outer functions, even when the outer function is no longer in scope.

Example

```js
function outer() {
  let count = 0;

  return function inner() {
    count++;
    return count;
  };
}

const counter = outer();

console.log(counter()); // 1
console.log(counter()); // 2
console.log(counter()); // 3
```

`Observations`

1. `count` variable is private and cannot be accessed directly from outside
2. `count` value is preserved on each function call

Real world Examples

###### Data privacy/Encapsulation

```JS
function createCounter(){
    let count = 0
    return {
        increament: () => ++count,
        decrement: () => --count,
        get: () => count
    }
}

const counter = createCounter()
console.log(counter.increment()); // 1
console.log(counter.increment()); // 2
console.log(counter.get());       // 2
console.log(counter.count);       // undefined (count is private)
```

###### Memoization

```js
function memoizedFib() {
  const cache = {};

  return function fib(n) {
    if (n <= 1) return n;
    if (cache[n]) return cache[n];
    return (cache[n] = fib(n - 1) + fib(n - 2));
  };
}

const fib = memoizedFib();
console.log(fib(40)); // much faster than plain recursion
```

###### Debouncing

```JS
function debounce(func, delay){
    let timeoutID

    return function(...args){
        clearTimeout(timeoutID);
        timeoutID = setTimeout(()=>{
            func.apply(this, args);
        }, delay)
    }
}

function myfunc(name){
    console.log("Hello",name)
}

dbouncedFunc = debounce(myfunc, 1000)
dbouncedFunc("Nomaan")
```

## JavaScript Data Types

JavaScript has two main types of data: **Primitive Types** and **Complex (Reference) Types**.

#### 1. Primitive Types (Immutable)

> Hold single values and are **copied by value**.

| Type        | Example         | Description                         |
| ----------- | --------------- | ----------------------------------- |
| `string`    | `"hello"`       | Text data                           |
| `number`    | `42`, `3.14`    | All numbers (integers, floats, NaN) |
| `boolean`   | `true`, `false` | Logical values                      |
| `null`      | `null`          | Explicit empty value                |
| `undefined` | `undefined`     | Declared but not assigned           |
| `symbol`    | `Symbol("id")`  | Unique and immutable identifier     |
| `bigint`    | `123456789123n` | Large integers beyond safe range    |

###### Characteristics:

- Stored in **stack**
- Immutable (cannot be changed in place)
- Compared by **value**

#### 2. Complex (Reference) Types

> Hold collections or functions and are **copied by reference**.

| Type          | Example                  | Description                    |
| ------------- | ------------------------ | ------------------------------ |
| `object`      | `{ name: "Nomaan" }`     | Key-value pairs                |
| `array`       | `[1, 2, 3]`              | Ordered list of values         |
| `function`    | `function() {}`          | Callable object                |
| `date`        | `new Date()`             | Date and time                  |
| `RegExp`      | `/ab+c/`                 | Regular expressions            |
| `Map` / `Set` | `new Map()`, `new Set()` | Advanced key/value collections |

###### Characteristics:

- Stored in **heap**
- Mutable (values can be changed)
- Compared by **reference**
