# First **JS** meeting

## How to write JavaScript code

Inline

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <h1>Its HTML</h1>
    <script>
      console.log("Hello world");
    </script>
  </body>
</html>
```

in Separate file

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <h1>Its HTML</h1>
    <script src="script.js"></script>
  </body>
</html>
```

```javascript
console.log("mohammed");
//var let const
var baseSalary = 6000; //function scope

let BaseSalary = 5000; //block scope

const Salary = 5000; //block scope cant be changed
```

---

## Writing variable on JavaScript

- Camel case
  Writing the name in one word but every word start with upper case `baseSalary`
- Two variables can't have the same name
- variables name is case sensitive
- can't start with a number

---

## Data types

### Primitive types

```javascript
//string
let keyWord = "mohammed";
console.log(keyWord); //mohammed
console.log(typeof keyWord); //string

//number
let baseSalary = 5000;
console.log(baseSalary); //5000
console.log(typeof baseSalary); //number

//boolean
let authed = true;
console.log(authed); //true
authed = false;
console.log(authed); //false
console.log(typeof authed); //boolean

//null
let name = null;
console.log(name); //null
console.log(typeof name); //object

//undefined
let x;
console.log(x); //undefined // undefined is false
console.log(typeof x); //undefined
```

### non-Primitive types

```javascript
//array
let array = [1, 2, 3, 4];
console.log(array); //(4) [1,2,3,4]
console.log(array.length); //4
console.log(array);

//object
let object = {
  name: "mohammed",
  age: 19,
};
console.log(object.name); //mohammed
console.log(`${object.name} is ${object.age}`); //mohammed is 19
```

`array` is a list of values
`index` of a array start form 0,1,2,........
`array` can get more than data type (primitive & non-primitive)

`opject` is a `key` and a `value`

**We use `typeof()` function to know the type of a value**

---

## Operators

### Math operators +, -, /, \* , \*\*

```javascript
let number1 = 5;
let number2 = 10;
console.log(`Sum = ${number1 + number2}`); //sum = 15
console.log(`Subtract = ${number1 - number2}`); //subtract = -5
console.log(`Divide = ${number1 / number2}`); //Divide = .5
console.log(`Multiply = ${number1 * number2}`); //Multiply = 50
console.log(`Bower = ${number1 ** number2}`); //Bower =  9765625
```

### comparison operators >, <, =!, == , ===

```javascript
let y = 5;
let z = 10;
let r = "5";
console.log(`is y > z ? ${y > z}`); //is y > z ? false
console.log(`is z > y ? ${z > y}`); //is z > y ? true
console.log(`is z != y ? ${z != y}`); //is z != y ? true
console.log(`is z == y ? ${z == y}`); //is z == y ? false
console.log(`is y == r ? ${y == r}`); //is y == r ? true
console.log(typeof r); //string
console.log(`is y === r ? ${y === r}`); //is y == r ? false
```

### logical operators ! && ||

```javascript
let y = 5;
let z = 10;
let t = true;
let f = false;
if (t){
	console.log{"that is true"} //that is true
} else {
	console.log{"that is false"}
}

if (!t){
	console.log{"that is true"}
} else {
	console.log{"that is false"} //that is false
}


if (t && f) {
 console.log("both true and false is true"); //both true and false is't true
} else {
	console.log("both true and false is't true");
}

if (t || f) {
	console.log("both true or false is true"); //both true or false is true
}
```

`!` mean not
`&&` mean and : Both value should be `true`
`||` mean or : One value should be `true`

---

## what is false

| falsely     | truthy                    |
| ----------- | ------------------------- |
| `false`     | `true`                    |
| `null`      | `{}`                      |
| `0`         | any number                |
| `undefined` | value which isn't falsely |
| `NaN`       |                           |
| `" "`       | any filled string         |

---

## If & else

```javascript
/*
if(condition){
	true result
}else if(another condition){
	another true result
}else{
	false result
}
*/
let open = true;
let closer = false;
let number = 15;

if (open == true) {
  console.log("yes"); //yee
} else {
  consloe.log("no");
}

if (number == 25) {
  console.log("yes");
} else {
  consloe.log("no"); //no
}
```

---

## String method

`method` is a build-in function on JavaScript

| method               | job                                                              |
| -------------------- | ---------------------------------------------------------------- |
| `length`             | the length of string spaces calculated                           |
| `toLocalUpperCase()` | Convert all string to upper case                                 |
| `toLocalLowerCase()` | Convert all string to lower case                                 |
| `substring(,)`       | Cut string in this index                                         |
| `indexOf(" ")`       | Find the first index of a given string (case sensitive)          |
| `replace("","")`     | Replace the first string with the second string                  |
| `split("")`          | Convert the string to array and split them with the given string |
| `parsInt()`          | Convert `string` to a number but `INT`                           |
| `parsFloat()`        | Convert `string` to a number but `float`                         |
| `isNaN()`            | Check if a value is number not a type                            |

---

## Number methods

| method         | job                                                 |
| -------------- | --------------------------------------------------- |
| `toFixed()`    | get the num of numbers after point                  |
| `Math.round()` | get the near real number with respect of last umber |
| `Math.floor()` | Get the nearest smaller real number                 |
| `Math.ceil()`  | Get the nearest bigger real number                  |
| `Math.pow(,)`  | Get the power of a number                           |
| `Math.sqrt()`  | Get the square root of a number                     |

---

## Switch case

```javascript
let day = "friday";
switch (day) {
  case "monday":
    console.log("start of the week");
    break;
  case "friday":
    console.log("weekend near");
    break;
  default:
    console.log("regular day");
    break;
}
```

---

## Loop

```javascript
/*
for (initialization; condition; Increment or decrement i++ , i--)
*/
for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

---

## prompt

```javascript
let num1 = parseFloat(prompt("Enter your first number"));
let num2 = parseFloat(prompt("Enter your second number"));
let operation = prompt("please enter an operation + - / *");

switch (operation) {
  case "+":
    console.log(`${num1} + ${num2} = ${num1 + num2}`);
    break;
  case "-":
    console.log(`${num1} - ${num2} = ${num1 - num2}`);
    break;
  case "*":
    console.log(`${num1} * ${num2} = ${num1 * num2}`);
    break;
  case "/":
    console.log(`${num1} / ${num2} = ${num1 / num2}`);
    break;
  default:
    console.log("not valid");
    break;
}
```

---

## Search

- Hosting `var` problem ( اعادة التعريف )
- symbol
