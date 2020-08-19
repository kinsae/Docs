## JS Execution

There are two places that you can execute your JavaScript code. It is either inside the `browser` or `Node.js`. You cannot execute JavaScript code outside these two. Node.js and all browsers use a `JavaScript Engine` to interpret and execute JavaScript code.

JS engines: Google V8 (Chrome, node.js), SpiderMonkey (Firefox)

## Syntax Parser (Compiler)

- A program that reads your code and determines what it does and if its grammar/syntax is valid.
- translates human readable code into computer instructions
- translates character by character

## Lexical Environment

- related to words or grammar or syntax
- where something sits in the code you write is important

## Global Execution Context (GEC)

- the default execution context when JavaScript Engine starts to interpret a JavaScript file either inside a browser or in Node.js
- a wrapper/environment to help manage the code that is running
- JS engine creates `window` Global object and `this` variable in the browser context.
- `window = this`
- there is only one Global Execution context

## JS Engine: Global Execution Context Phases

### 1. Creation Phase

- create Global Object
- create this variable
- setup memory for variable and functions (`hoisting`)
- variables are initialized with `undefined`
- puts function declarations in memory

<img src="p1.png" width=500>
<img src="creation-phase.jpg" width=500>
<img src="p2.png" width=500>

### 2. Execution Phase

- executes the code you have written line by line from top to bottom
- assigns real values to the variables

<img src="execution-phase.jpg" width=500>
<img src="p3.png" width=500>

## Name/Value Pair

- a `name` which maps to a unique `value`
- a name may be defined more than once, but can only have one value at a <b>given context</b>
- value may be other name-value pairs

  ```
  // name can have only one value
  name: 'value'

  // value can be more name:value
  city: {
        name: 'New York',
        code: 1234
      }
  ```

## Hoisting

- variables and functions are lifted up to the top during the global execution; creation phase
- variables are initialized as undefined

  ```
  console.log(a);
  b();

  var a = 123;

  function b(){
    // some code
  }

  // Output
  undefined
  123
  ```

  Above code executes as;

  ```
  // variables & function hoisted
  var a;

  function b(){
    // some code
  }

  console.log(a);
  b();

  // Output
  undefined
  123
  ```

## Single Threaded

- one command runs at a time

## Synchronous

- one line at a time

## Function Invocation

- running/calling a function
- `()` is used to invoke the functions

  ```
  function learnJS(){
  }

  // invoking learnJS function
  learnJS();
  ```

## Function Execution Context (FEC)

- every function call creates new Function Execution Context (FEC) for that function
- function execution context has: `Creation` and `Execute` phases
- FEC exists inside the global context and will has access to variables in its parent context (GEC)
- creates extra `arguments` object
- setup memory for variables and functions in `Creation Phase`

<img src="fec-p1.png" width="500">
<img src="fec-p2.png" width="500">

In above example we have `num1` as a global variable and our function has `num2` as a local variable. `num2` only exists as long as the function is executing. `num2` is inside the function execution Context. So, when the function is done executing, `num2` does not exist anymore. This FEC has access to `this`, `num1` variables of GEC, so they have real values in the creation phase of this FEC.

## Execution/Call Stack

- stack of functions execution contexts
- every function execution context is added to call stack
- stack works in LIFO concept

  <img src="cal-stack.png" width=500>

## Scope Chain

- inner functions has access to variables of outer functions
- looking for variables not available within a function to outer function scope.

```
function b(){
  console.log(myVar);
}

function a(){
  var myVar = 2;
  b();
}

var myVar = 1;
a();

// Output
1
```

In above; `b()` has access to global `myVar` not of `a()`. `myVar` is not available within `b()`, so it looks at outer environment. This process is known as scope chain.

```
function a(){
  var myVar = 2;

  function b(){
    console.log(myVar);
  }
}

var myVar = 1;
a();

// Output
2
```

In above; `myVar` is not available within `b()`, so it looks at outer environment i.e. function `a()` in this case. `myVar` is available at `a()` and prints the value. If `myVar` was not available within `a()`, function `b()` will look at global environment.
