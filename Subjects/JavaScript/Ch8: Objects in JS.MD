## JavaScript Objects Deep Dive

#### Object Literal (Most Common)

```js
const person = {
  name: "Alice",
  age: 30,
  greet: function () {
    console.log("Hello!");
  },
};
```

#### Using `new Object()` (Less Common)

```js
const person = new Object();
person.name = "Alice";
person.age = 30;
```

`Note:` Prefer object literals for clarity and brevity.

### Accessing & Modifying Properties

#### Dot Notation

```js
console.log(person.name); // Alice
person.age = 31;
```

#### Bracket Notation (Useful for dynamic keys)

```js
const key = "name";
console.log(person[key]); // Alice
```

#### Add New Property

```js
person.city = "Delhi";
```

#### Delete Property

```js
delete person.age;
```

### `this` Keyword In Object

#### In Functions

```js
const user = {
  name: "Ali",
  greet() {
    console.log("Hi, I’m " + this.name);
  },
};

user.greet(); // Hi, I’m Ali
```

#### In Arrow Functions (Does Not own `this`)

```js
const user = {
  name: "Ali",
  greet: () => {
    console.log("Hi, I’m " + this.name); // ❌ `this` is not `user`
  },
};

user.greet(); // Hi, I’m undefined
```

### Object Destructuring

> Extract values from objects easily

```js
const user = {
  name: "Ali",
  age: 25,
  city: "Mumbai",
};

const { name, city } = user;
console.log(name); // Ali
console.log(city); // Mumbai
```

#### Rename While Destructuring

```js
const { name: userName } = user;
console.log(userName); // Ali
```

#### With Default Values

```js
const { state = "Delhi" } = user;
console.log(state); // Delhi
```

### Copy Objects

#### Copy by References

```js
const a = { x: 1 };
const b = a;
b.x = 2;
console.log(a.x); // 2 — both `a` and `b` refer to same object
```

#### Shallow Copy

A shallow copy copies only the top-level properties of an object or array.
If those properties are references to other objects, the reference is copied — not the actual nested object.

```js
const original = {
  name: "Ali",
  address: {
    city: "Delhi",
  },
};

const shallowCopy = { ...original };

shallowCopy.address.city = "Mumbai";

console.log(original.address.city); // 👉 "Mumbai" — original is affected
```

#### Deep Copy (Nested objects)

A deep copy recursively copies all levels of the object, so that the new object is completely independent of the original.

```js
const original = {
  user: {
    name: "Ali",
  },
};

// Method_1
// cons: does not supports functions, undefined & Symbols
const deepCopy = JSON.parse(JSON.stringify(original));

// Method_2
const deepCopy = structuredClone(original);

// Method_3
import _ from "lodash";
const deepCopy = _.cloneDeep(original);
```
