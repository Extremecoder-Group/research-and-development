## ECMASCript and TC39
- ECMAScript the official specification that JavaScript conforms to has improved a lot in the past few years.
- Today the ECMAScript Technical Committee, which is known as TC39, makes yearly releases of ECMAScript, and the modern browsers shortly follow by implementing the new features introduced in each year.
- git link of TC39: `github.com/tc39`
- This has started with ECMAScript 2015, or its other commonly known name, `ES6`. Since then, we have had yearly releases named ES plus the current year.

## Variables and Block Scopes
- `{{{}}}` is this a valid block? Answer: Yes.
- So what did it do? Answer: These are nested block scopes.
- We could write a variable like this and access in this way. Java script does not care about how many nested blocks are there.
  ```javascript
  {{{ var v = 42; }}}
  v
  ``` 
- A block scope is created with a pair of curly braces, just like this example here. It also applies to if statements and for statements as well.
    ```javascript
    {
        // Block Scope
    }

    if(true) {
        // Block Scope
    }

    for(var i=1; i<=10; i++) {
        // Block Scope
    }

    function sum(a, b) {
        // Function Scope
        var result = a + b;
    }

    sum(4+3);
    ```
- Block scopes are a bit different that function scopes, which are created for each function.
- We we declare a variable with `var` keyword it can be accessed from anywhere.
- But if we declare a varaiable with `let` keyword it can not be accessed outside the defined block.
    ```javascript
    // var
    for(var i=1; i<=10; i++) {
        
    }
    console.log(i)

    // let
    for(var j=1; j<=10; j++) {
        
    }
    console.log(j) // will throw an error
    ```
- **Nested Block Scope**
    ```javascript
    {
        // Block scope
        {
            // Nested Block scope
        }
    }
    ```
    - Within each level the scope will protect the variables defined in it as long as we use the `let` keyword or the `const` keyword.
- **`const` keyword**
  - We use `const` when the reference assigned to a variable is meant to be a constant one.
  - References assigned with `const` cannot be changed. That means references not values.
  - **Because defining an object with `const` does not make it an immutable object. It just mean constant reference to it. We can still change that object just like we can do within functions that receive objects as arguments.**
  - **If the variable defined with `const` is a scaler one, like a string or an integer we can think of it as an immutable object. Because these scalar values in JavaScript are immuatable. We can not mutate the value of a string or an integer in JavaScript.**
  - **However placing an array or object in a `const` is a different story.**