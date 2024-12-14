# JS lec 5

## Agenda

1. revision on the promises types of resolve
2. OPP

## Revision

async saved in the web api

- `setTimeout`

macro tasks que

- set time out

micro tasks ques start first

- async function runs first if it doesn't contain awt
- promise
  - resolve
  - reject

```javascript
console.log("A");
Promise.resolve("F").then((result) => console.log(result));

setTimeout(() => {
  console.log("B");
}, 0);
console.log("L");

setTimeout(() => {
  console.log("R");
}, 2000);

Promise.resolve("C").then((result) => console.log(result));
async function nameFunc() {
  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/todos");
    const data = await response.json();
    console.log("ahmed");
  } catch (error) {
    console.error("Error:", error);
  }
}
nameFunc();
console.log("D");
console.log("Z");
//A
//L
//D
//Z
//F
//C
//B
//ahmed
//9
```

## OPP

> Object-oriented programming

**DRY** Don't repeat yourself

1. encapsulation
2. polymorphism
3. inheritance
4. instruction

### encapsulation

- `public`
- `private` `#` no one can see
- `protected` can be seen but can't be edited

```javascript
class Employee {
  #salary;
  constructor(name, position, salary) {
    this.name = name;
    this.position = position;
    this.#salary = salary;
  }
  getSalary() {
    return `The salary of ${this.name} is ${this.#salary} USD.`;
  }
  setSalary(newSalary) {
    if (newSalary > 0) {
      this.#salary = newSalary;
    } else {
      console.log("Invalid salary amount!");
    }
  }
}
const employee = new Employee("Sara", "Software Engineer", 5000);
console.log(employee.getSalary());
employee.setSalary(6000);
console.log(employee.getSalary());
employee.setSalary(2000);

//The salary of Sara is 5000 USD.
//The salary of Sara is 6000 USD.
```

### inheritance

> make a copy of an object and edit on it
>
> add just a key

```javascript
class Vehicle {
  constructor(type, brand) {
    this.type = type;
    this.brand = brand;
  }

  startEngine() {
    console.log(`${this.brand} ${this.type} engine started.`);
  }
}

class Bike extends Vehicle {
  constructor(brand, gearCount) {
    super("Bike", brand);
    this.gearCount = gearCount;
  }

  describe() {
    console.log(`${this.brand} bike has ${this.gearCount} gears.`);
  }
}

class Car extends Vehicle {
  constructor(brand, fuelType) {
    super("Car", brand);
    this.fuelType = fuelType;
  }

  describe() {
    console.log(`${this.brand} car runs on ${this.fuelType} fuel.`);
  }
}

const myBike = new Bike("Trek", 21);
myBike.startEngine(); //Trek Bike engine started.
myBike.describe(); //Trek bike has 21 gears.
const myCar = new Car("Toyota", "Petrol");
myCar.startEngine(); //Toyota Car engine started.
myCar.describe(); //Toyota car runs on Petrol fuel.
```

### polymorphism

> overwrite an object Properties
>
> edit on the value

```javascript
class Animal {
  speak() {
    console.log("This animal makes a sound.");
  }
}
class Dog extends Animal {
  speak() {
    console.log("The dog barks.");
  }
}
class Cat extends Animal {
  speak() {
    console.log("The cat meows.");
  }
}
const myDog = new Dog();
const myCat = new Cat();
myDog.speak(); //The dog barks.
myCat.speak(); //The cat meows.
```

### instruction

> cutout from the object

```javascript
class Shape {
  constructor(name) {
    this.name;
    name;
  }
  getArea() {
    throw new Error(`${this.name} must implement getArea`);
  }
}
class Circle extends Shape {
  constructor(radius) {
    super("Circle");
    this.radius = radius;
  }
  getArea() {
    return Math.PI * this.radius ** 2;
  }
}

class Square extends Shape {
  constructor(side) {
    super("Square");
    this.side = side;
  }
  getArea() {
    return this.side ** 2;
  }
}
const circle = new Circle(7);
console.log(`Area of circle: ${circle.getArea()}`);
const square = new Square(5);
console.log(`Area of square: ${square.getArea()}`);
```

## local storage

> save info permanently on the local device
>
> data is saved as a string so we transform it to object

```javascript
localStorage.setItem("name", "mohammed");
localStorage.setItem("theme", "dark");
let user = localStorage.getItem("name");
console.log(user); //mohammed
localStorage.removeItem("name");
localStorage.clear(); //clear every thing
```

## session storage

> clear when close the page or refresh

```javascript
sessionStorage.setItem("isLogin", true);
const session = JSON.parse(sessionStorage.getItem("isLogin"));
console.log(session); //true
```

## cookies

> sent in the request

```javascript
document.cookie = "username=mohammed";
console.log(document.cookie); //username=mohammed
```

## search

> helps to hide something for security

- setters
- getters
