# JS lec 4

## Events

> action or interaction on the `DOM` > `addEventListener`

### mouse events

#### click

- click on a button to make an action
- onClick

```javascript
const btn = document.querySelector("#btn"); //catch the button with it's id
btn.addEventListener("click", () => {
  alert("click is done"); //action will be done after clicking the btn
});
```

#### double click

```javascript
const btn = document.querySelector("#btn"); //catch the button with it's id
btn.addEventListener("doubleclick", () => {
  console.log("btn is double clicked"); //action will be done after double clicking the btn
});
```

#### mouseover

```javascript
const btn = document.querySelector("#btn"); //catch the button with it's id
btn.addEventListener("mouseover", () => {
  console.log("btn is hovers"); //action will be done wile hovering
});
```

#### mouseout

```javascript
const btn = document.querySelector("#btn"); //catch the button with it's id
btn.addEventListener("mouseout", () => {
  console.log("mouse is out from btn"); //action will be done after exit the btn
});
```

### mousemove

```javascript
const btn = document.querySelector("#btn"); //catch the button with it's id
btn.addEventListener("mousemove", () => {
  console.log("mouse is out from btn"); //action will be done mouse is moved while the cursor's hover btn.
});
```

## keyboard events

### keydown

```javascript
document.addEventListener("keydown", (e) => {
  console.log(`you clicked on ${e.key}`); // will print every key i press
});
```

### keyup

```javascript
document.addEventListener("keyup", (e) => {
  console.log(`you clicked on ${e.key}`); // will print every key after its press over
});
```

### keypress

```javascript
document.addEventListener("keydown", (e) => {
  console.log(`you clicked on ${e.key}`); // will fire only keys numbers key i press
});
```

## Form event

### submit

```javascript
const form = document.querySelector("#form");
form.addEventListener("submit", (e) => {
  e.preventDefault(); //prevent the reload of the page
  alert("form submitted"); //action fire when submit button is clicked
});
```

## window events

```javascript
window.addEventListener("resize", () => {
  console.log("resize fire"); //on resize widows
});
window.addEventListener("load", () => {
  console.log("load fire"); //on reload
});
window.addEventListener("scroll", () => {
  console.log("scroll fire"); //on scroll
});
window.addEventListener("unload", () => {
  console.log("unload fire"); //when the user close the page
});
```

## advanced topics

### JSON files

javascript object notation

> integration between frontend and database

convert an object to a json file

```javascript
const data = {
  name: "ali ",
  age: 20,
  city: "cairo",
};
const jsonData = JSON.stringify(data);
console.log(jsonData);
```

convert json file to object

```javascript
const objData = JSON.parse(jsonData);
```

### Synchronous Asynchronous

java script can handel

`Synchronous`

`Asynchronous`

1. `setTimeout`
2. `promises`
3. `async function`
4. `await function`

> that is the arrange of firing them

java script will run `Synchronous` then `Asynchronous`

### setTimeout

```javascript
setTimeout(() => {
  console.log("the is late");
}, 1000);
console.log("that is early");
//that is early
//the is late
```

### promise

> `promise` have priority on the `setTimeout`

action done which is Asynchronous

- pending
- Fulfilled `then`
- rejected `catch`

```javascript
const promise = new Promise((resolve, reject) => {
  const success = true;
  if (success) {
    resolve("Operation was Successful");
  } else {
    reject("there was an Error ");
  }
});
promise
  .then((result) => console.log(result))
  .catch((error) => {
    console.error(error);
  });
//Operation was Successful
```

```javascript
console.log("1");
setTimeout(() => console.log("2"), 0);
Promise.resolve().then(() => console.log("3"));
console.log("4");
```

### Async

> `async` have priority on the `promise`

fires at specific time

`.json()` give me just the json data if removed i will get the whole response

```javascript
async function fetchData() {
  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/todos");
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Error:", error);
  }
}
fetchData();
```

### Await

> `Await` is the last to fire

### Fetch data from API

```javascript
fetch("https://jsonplaceholder.typicode.com/users")
  .then((res) => res.json())
  .then((users) => {
    users.forEach((user) => console.log(user));
  })
  .catch((error) => console.error("Error fetching users", error));
```

### event loop

1. all in call stack line by line
2. `web API` for all `Asynchronous` to the task queue by priorities

### call stack

### web API

## Search

- `debouncing`
- `focus`
- `select`
- `promise.all()`
  > wait all then fire don't run if there is an error
- `promise.race()`
  > return one first promise even if it was true of false
- `promise.any()`
- `promise.allSettled()`
- `setInterval()`
