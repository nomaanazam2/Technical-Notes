#### Function Declaration

```JS
function greet() {
  console.log("Hello!");
}
greet(); // ✅ Works even if called before the declaration (Hoisting)
```

#### Function Expression

```JS
const greet = function() {
  console.log("Hello!");
};
greet(); // Cannot be called before function expression (Not Hoisted)
```

#### Arrow Function

```JS
const greet = () => {
    console.log("Hello!");
}
greet();
```

### Parameters, Rest Parameters, Default Parameters

#### Normal parameter

```JS
function greet(name) {
  console.log("Hello " + name);
}
greet("Ali");
```

#### Default parameter

```JS
function greet(name = "Guest") {
  console.log("Hello " + name);
}
greet("Ali");
```

#### Rest parameter

```JS
// Argument received as Array
function sum(...nums) {
  console.log(nums)     // [1, 2, 3]
}
sum(1, 2, 3);
```

### Callback Functions

A function passed as an argument to another function

```JS
function greetUser(name, callback) {
  console.log("Hello " + name);
  callback();
}

function myFunc() {
  console.log("Welcome!");
}

greetUser("Ali", myFunc);
```

### Summary Table

| Feature            | Declaration | Expression | Arrow Function      |
| ------------------ | ----------- | ---------- | ------------------- |
| Hoisted            | ✅ Yes      | ❌ No      | ❌ No               |
| `this` context     | dynamic     | dynamic    | lexical (inherited) |
| Can be constructor | ✅ Yes      | ✅ Yes     | ❌ No               |
| Syntax simplicity  | medium      | medium     | ✅ Concise          |

### `this` Context in Javascript

In JavaScript, this refers to the context in which a function is executed — essentially, what object is “calling” the function.

| Context               | `this` refers to                            |
| --------------------- | ------------------------------------------- |
| In a regular function | `undefined` (in strict mode), else `window` |
| In an object method   | The object the method is called on          |
| In a constructor      | The **newly created object**                |
| In an event handler   | The DOM element triggering the event        |
| In an arrow function  | **Lexically inherited `this`**              |
