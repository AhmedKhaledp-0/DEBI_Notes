# Second **JS** meeting

## Loops

### for

```javascript
for (let i = 5; i < 5; i++) {
  console.log(`nba ${i}`);
}
```

### while

> loops through a block of code while a specified condition is true.

```javascript
let i = 1;
while (i < 5) {
  console.log(`nba ${i}`);
  i++;
}
```

### do/while

> also loops through a block of code while a specified condition is true

```javascript
let i = 1;
do {
  console.log(`nba ${i}`);
  i++;
} while (i < 5);
```

Always will do the result once

### for/in

> loops through the properties of an object

```javascript
let person = {
  name: "fahmy",
  age: 30,
  city: "cairo",
};
for (let key in person) {
  console.log(`${key} = ${person[key]}`);
}
// name = fahmy
// age = 30
// city = cairo
```

### for/of

> loops through the values of an iterable `array` object

```javascript
let fruits = ["apple", "banana", "cherry"];
for (let fruit of fruits) {
  console.log(fruit);
}
// apple
// banana
// cherry
```

## hoisting

```javascript
/*
if () {
  Scope
}
*/
let name = 0;
if (name == 0) {
  let asmaa = 100;
  var asmaa2 = 200;
  console.log("true");
  console.log(asmaa); //asmaa
}
console.log(asmaa2); //200
console.log(asmaa); //Reference error
```

`const` and `let` is a block scope

`var` is a function scope

`const` and `let` give us a `ReferenceError` but `var` gives `undefined`

```javascript
let a = "global";
function fun() {
  let a = "function scope";
  if (true) {
    let a = "block from if";
    var b = "hoisted from if";
    console.log(a); // block from if
    console.log(b); // hoisted from if
  }
  console.log(a); // function scope
  console.log(b); // hoisted from if
}
fun();
console.log(a); // global
console.log(b); // ReferenceError
```

## Types of functions

### Function Declaration

```javascript
function greet(name) {
  let sayHi = "welcome to my team";
  return `Hello, ${name}! ` + sayHi;
}
//Example of using for/of
let names = ["ahmed", "omar", "jo"];
for (let name of names) {
  console.log(greet(name));
}
//Hello, ahmed! welcome to my team
//Hello, omar! welcome to my team
//Hello, jo! welcome to my team
```

Function declarations are `hoisted`, meaning they are available for use even before they are defined in the code.

Ideal for basic operations and utility functions.

### Function expressions

```javascript
const sayGoodbye = function (name) {
  let sayHi = "welcome to my team";
  return `Goodbye, ${name}! ` + sayHi;
};
console.log(sayGoodbye("ahmed")); //Goodbye, ahmed! welcome to my team
```

Function expressions involve defining a function within an expression.

They can be `named` or kept `anonymous`.

Function expressions are `not hoisted`, which provides greater control over the execution flow.

### Arrow Functions

```javascript
const sayGoodMorning = (name) => {
  let sayHi = "welcome to my team";
  return `Good Morning, ${name}! ` + sayHi;
};
console.log(sayGoodMorning("ahmed")); //Good Morning, ahmed! welcome to my team
```

Introduced in `ES6`, arrow functions provide a concise syntax for defining functions.

They also share the `this` context with the `enclosing scope`, making them well-suited for callbacks and functional programming tasks.

### Immediately Invoked Function Expressions (IIFE)

```javascript
(function () {
  console.log("IIFE executed");
})(); // Output: IIFE executed
```

`IIFEs` are `functions` that are executed immediately upon definition.

They help create `private scopes` and module patterns, preventing variables from leaking into the `global scope`.

### Callback function

```javascript
setTimeout(function () {
  console.log("nba");
}, 5000);
```

### Constructor functions

> will be clear within the OPP

```javascript
function Person(name) {
  this.name = name;
}
const john = new Person("Alex");
console.log(john.name); // Output: Alex
```

Constructor functions are used to create objects.

They follow the `new` keyword and typically start with a capital letter.

They define the properties and methods associated with the objects they create.

### Named Functions

```javascript
function greet(name) {
  return `Hello, ${name}`;
}
```

### Anonymous Functions

```javascript
const greet = function (name) {
  return `Hello, ${name}`;
};
```

## Array methods

```javascript
let names = ["Doha", "Khaled", "Tasnim", "Naira", "Abdo", "Fahmy", "Asmaa"];
console.log(names); //(7) ['Doha', 'Khaled', 'Tasnim', 'Naira', 'Abdo', 'Fahmy', 'Asmaa']
console.log(names.indexOf("Fahmy")); //5
names.push("Hasnaa");
console.log(names); //(8) ['Doha', 'Khaled', 'Tasnim', 'Naira', 'Abdo', 'Fahmy', 'Asmaa', 'Hasnaa']

names.pop();
console.log(names); //(7) ['Doha', 'Khaled', 'Tasnim', 'Naira', 'Abdo', 'Fahmy', 'Asmaa']
names.shift();
console.log(names); //(6) ['Khaled', 'Tasnim', 'Naira', 'Abdo', 'Fahmy', 'Asmaa']
names.unshift("Samy");
console.log(names); //(7) ['Samy', 'Khaled', 'Tasnim', 'Naira', 'Abdo', 'Fahmy', 'Asmaa']
names.forEach((name) => {
  console.log(name);
});
// Samy
// Khaled
// Tasnim
// Naira
// Abdo
// Fahmy
// Asmaa

names.map((name) => {
  console.log(name);
});

//Samy;
//Khaled;
//Tasnim;
//Naira;
//Abdo;
//Fahmy;
//Asmaa;
let hiNames = names.map((name) => `hi ${name}`);
console.log(hiNames);
7; // ['hi Samy', 'hi Khaled', 'hi Tasnim', 'hi Naira', 'hi Abdo', 'hi Fahmy', 'hi Asmaa']

let namesFilter = names.filter((name) => names.length > 5);
console.log(namesFilter); //(2) ['Khaled', 'Tasnim']
```

| method      | use                                                                                     |
| ----------- | --------------------------------------------------------------------------------------- |
| `length`    | returns the length (size) of an array                                                   |
| `push()`    | adds a new element to an array (at the end)                                             |
| `pop()`     | removes the last element from an array:                                                 |
| `shift()`   | method removes the first array element and "shifts" all other elements to a lower index |
| `unshift()` | adds a new element to an array (at the beginning),                                      |
| `forEach()` | for iteration on array only                                                             |
| `map()`     | create a new array after doing an operations on it                                      |
| `filter()`  | Create new array with filtered condition                                                |

## Search

- `this`

  Q:what is the difference between declaration and arrow function

- `recursion function` function return a function
- `closure function` function within function
- `reduce` array method
