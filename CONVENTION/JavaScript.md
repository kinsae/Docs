## PROGRAMMING BEST PRACTICES

### 1. Naming Convention

NOTE: Naming variable, methods and classes must be self-explanatory and meaningful.

#### Naming Variables

- use `camelCase` convention
- eg;

      let myVariable;
      var fruitName = "Apple";

#### Naming Constants

- use `UPPERCASE` `SNAKE_CASE` convention for universal constants
- eg;

      const PI = 3.14;
      const HOURS_IN_DAY = 24;

- use `camelCase` convention for dynamic constants
- eg;

      const today = new DATE();

#### Naming FUNCTIONS

- use `camelCase` convention
- use verbs as prefix (get, set, find, delete, etc.)
- use descriptive naming but be concise wherever possible
- eg;

      function getUserByEmail() {
        // ...
      }
      function getUserAddress() {
        // ...
      }
      function deleteUserByID() {
        // ...
      }

#### Naming Classes

- use `PascalCase` convention
- use nouns
- eg;

      class Person {
        // ...
      }
      class EatableFruit {
        // ...
      }

### 2. Avoid Using Magic Number

Magic Number:

```
if(age < 30) return true;
// 30 is a magic number, number without any explanation
```

Good Practice:

```
const MAX_AGE = 30;
if(age < MAX_AGE) return true;
```

### 3. Utilize Recursive Function / Avoid Code Repetition

Code Repetition:

```
const nestedArray = [ [ [ 'value' ] ] ]
nestedArray.forEach((innerArr1) => {
  innerArr1.forEach((innerArr2) => {
    innerArr2.forEach((element) => {
      console.log(element);
    })
  })
});
```

Recursive Function:

```
const retrieveFinalValue = (element) => {
  if(Array.isArray(element)) {
    return retrieveFinalValue(element[0]);
  }
  return element;
}

retrieveFinalValue(nestedArray);
```

### 4. Avoid Writing Large Functions

- split different logics into each functions
- a function must perform only one task. <b>(The One Thing Rule)</b>
- `high cohesion` is better (focus on a single task: single-mindedness)
- `low coupling` is better (less dependence on other functions)
- keep indentation level up to <b>2</b>
- try to keep `5`-`10` lines of code per function

### 5. Make Use of Object Destructuring

Normal Usage:

```
function addUser(user) {
  const name = user.name;
  const age = user.age;
  const address = user.address;

  // ...
}
```

Object Destructuring:

```
function addUser(user) {
  const { name, age, address } = user;

  // ...
}
```

### 6. Avoid Single Character Names

```
const q = "SELECT * FROM table";  //  bad variable name

const query = "SELECT * FROM table";  //  better variable name
```

But OK in Loops:

```
for (let i = 0; i < arr.length; i++) {
  // ...
}
```
