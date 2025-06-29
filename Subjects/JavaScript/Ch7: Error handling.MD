- `try...catch...finally`
- `throw` statement
- Custom Error creation

### Error Handling in JavaScript

#### try...catch...finally

```JS
try {
  // Code that may throw an error
  let result = riskyOperation();
} catch (error) {
  // Handle error gracefully
  console.error("Something went wrong:", error.message);
} finally {
  // Always runs
  console.log("Cleanup or final steps");
}
```

#### Manual Error throw

You can throw anything, but best practice is to use Error objects for consistency.

```JS
throw new Error("Something broke");
throw "Just a string"; // not recommended
throw 404;             // not recommended
```

#### Custom Error Creation

You can create custom error types using class

```JS
class ValidationError extends Error {
  constructor(message) {
    super(message);
    this.name = "ValidationError";
  }
}

function processData(input) {
  if (typeof input !== "string") {
    throw new ValidationError("Expected a string input");
  }
  return input.toUpperCase();
}

try {
  processData(42);
} catch (e) {
  if (e instanceof ValidationError) {
    console.error("Validation failed:", e.message);
  } else {
    console.error("Unknown error:", e);
  }
}
```
