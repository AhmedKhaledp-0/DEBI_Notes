# JS lecture 2

## closure

function return another function

```javascript
//parent
function outerFunction(outerVariable) {
  //childe can see parent variables
  return function innerFunction(innerVariable) {
    console.log(`outer Variable : ${outerVariable}`); //outer Variable : outside
    console.log(`inner Variable : ${innerVariable}`); //inner Variable : inside
  };
}
const newFunction = outerFunction("outside");
newFunction("inside");

let count = 22;
function createCounter() {
  let count = 0;
  return function () {
    count++;
    return count;
  };
}
console.log(count);
const counter = createCounter(); //expression function
console.log(counter()); //1
console.log(count); //22
```

the `inner function` can see `outer function` variables , but the `outer function` can't see the `inner function` variables

## Recursion

> iteration

A function return it's self until specific condition

used for node dom

```javascript
function factorial(n) {
  if (n === 0) return 1;
  return n * factorial(n - 1);
}
console.log(factorial(5)); //120
```

## High order function

a `Function` that take a function as its parameter

```javascript
const numbers = [1, 2, 3, 4, 5, 6];
const newNumbers = numbers.map((number) => number * 2);
console.log(newNumbers); //(6) [2, 4, 6, 8, 10, 12]
```

## destructure (array) `ECMAScript`

> call data in a short easy way
>
> `react` built on it

```javascript
const names = ["fahmy", "hepa", "khaled", "nairra", "asmaa", "eslam"];
console.log(names[3]); //nairra
const [first, second, third] = names;
const [, , name3] = names;

console.log(first); //fahmy
console.log(second); //hepa
console.log(third); //khaled
console.log(name3);
```

## destructure (objects) `ECMAScript`

```javascript
const student = {
  name: "asmaa",
  age: 20,
  city: "cairo",
};
console.log(student.name); //asmaa
console.log(student.age); //20
//make it shorter
// const name = student.name;
// const age = student.age;
// const city = student.city;

const { name, age, login = true } = student;
console.log(name); //asmaa
```

## destructing function params

```javascript
function printDetails({ name, age }) {
  console.log(`Name: ${name}, Age: ${age} `);
}

printDetails(student); // Name: asmaa, Age: 20
```

## spreed operator `...` `ECMAScript`

> for `array`

```javascript
const newNames = [...names, "hanan", "ali", "folan"];
console.log(newNames); //['fahmy', 'hepa', 'khaled', 'nirra', 'asmaa', 'eslam', 'hanan', 'ali', 'folan']
```

## rest operator `...` `ECMAScript`

> for `function`

```javascript
function sum(...args) {
  return args.reduce((total, num) => total + num, 0);
}
console.log(sum(1, 2, 3)); //6
```

## BOM

> Browser Object Model
> key word is `window` `this`

```javascript
consols.log(window); //Window {window: Window, self: Window, document: document, name: '', location: Location, …}
console.log(window.innerWidth); //839
const newWindow = window.open("https://www.google.com","    blank");|
```

### Location

`href`

```javascript
console.log(location.href); //http://127.0.0.1:5500/index.html
console.log(location.hostname); //127.0.0.1
location.reload(); //reload the page
location.assign("https://google.com"); //got to a page
```

### history

```javascript
history.back();
history.forward();
history.go(2); //forward 2
history.go(-2); //backward 2
history.length; //show site history
```

### navigator

```javascript
console.log(navigator.userAgent); //userAgent
```

### Screen

```javascript
console.log(screen); //Screen {availWidth: 1920, availHeight: 1032, width: 1920, height: 1080, colorDepth: 24, …}
```

## object

```javascript
const person = {
  name: "Ahmed",
  age: 25,
  greet: function () {
    return `Hello, my name is ${this.name}`;
  },
};
console.log(person.name); //Ahmed
console.log(person.greet()); //  Hello, my name is Ahmed
```

`this` is the scope of the object

## constructor function

> initial value for the objet `dynamic object`

```javascript
function Student(name, age) {
  this.name = name;
  this.age = age;
}
const person1 = new Student("Sara", 30);
console.log(person1); //Student {name: 'Sara', age: 30}

const car = {
  brand: "Toyota",
  model: "Corolla",
  getDetails: function () {
    return `${this.brand} ${this.model}`;
  },
};
console.log(car.getDetails()); // Toyota Corolla
//if we removed `this`
const car = {
  brand: "Toyota",
  model: "Corolla",
  getDetails: function () {
    return `${brand} ${model}`;
  },
};
console.log(car.getDetails()); // ReferenceError: brand is not defined
```

## DOM Document Object Model

- `getElementById`
- `getElementByClassName` all elements have this class in array `[]`
- `getElementByTagName`
- `querySelector()` '.btn' classname ,'btn` tagName ,'#btn' id give me only the first one
- `querySelectorAll()`

```javascript
const title = document.getElementById("title");
console.log(title.innerText); //JS DEBI task 2

const buttons = document.querySelectorAll(".btn");

//using forEach
buttons.forEach((btn) => {
  console.log(btn);
});

//using spread operator
const newBtn = [...buttons].map((btn) => btn.innerText);
console.log(newBtn);
```

### edit on HTML elements

```javascript
const title = document.getElementById("title");
title.innerText = "JS DEBI task 3"; //change the text of h1
title.style.color = "red"; //change the color of h1
```
