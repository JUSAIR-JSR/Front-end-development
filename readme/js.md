# JavaScript Full Course (Beginner to Advanced)

Welcome to the complete **JavaScript Course** designed for absolute beginners as well as intermediate learners.
This course covers everything from basics to advanced concepts.

---

# ⭐ 1. Introduction to JavaScript

JavaScript is a programming language used to:

* Add interactivity to websites
* Handle logic
* Update content dynamically
* Work with APIs
* Create web apps, games, backend apps, etc.

Add JS to HTML:

```
<script>
  console.log("Hello JS!");
</script>
```

Or external file:

```
<script src="app.js"></script>
```

---

# ⭐ 2. Variables

```
let name = "Jusair";
const age = 21;
var city = "India";
```

Use:

```
console.log(name);
```

---

# ⭐ 3. Data Types

* String
* Number
* Boolean
* Null
* Undefined
* Object
* Array

Example:

```
let x = "Hello";
let y = 100;
let z = true;
```

---

# ⭐ 4. Operators

```
+ , - , * , / , %
== , === , != , !==
> , < , >= , <=
&& , || , !
```

Example:

```
console.log(5 + 3);
console.log(10 > 6);
```

---

# ⭐ 5. Functions

```
function greet() {
  console.log("Hello!");
}
greet();
```

Arrow functions:

```
const add = (a, b) => a + b;
```

---

# ⭐ 6. Strings

```
let name = "Jusair";
console.log(name.length);
console.log(name.toUpperCase());
```

Template literals:

```
console.log(`Hello ${name}`);
```

---

# ⭐ 7. Arrays

```
let arr = [10, 20, 30];
arr.push(40);
arr.pop();
```

Loop:

```
for(let i of arr){
  console.log(i);
}
```

---

# ⭐ 8. Objects

```
let user = {
  name: "Jusair",
  age: 20,
  city: "India"
};

console.log(user.name);
```

---

# ⭐ 9. Conditions

```
if(age > 18){
  console.log("Adult");
} else {
  console.log("Minor");
}
```

---

# ⭐ 10. Loops

```
for(let i = 1; i <= 5; i++){
  console.log(i);
}
```

While loop:

```
let i = 0;
while(i < 5){
  console.log(i);
  i++;
}
```

---

# ⭐ 11. DOM Manipulation

```
document.getElementById("title").textContent = "Updated!";
```

Example:

```
<button onclick="changeText()">Click</button>
<h1 id="title">Hello</h1>

<script>
function changeText(){
  document.getElementById("title").textContent = "Button Clicked!";
}
</script>
```

---

# ⭐ 12. Events

```
button.addEventListener("click", function(){
  console.log("Clicked!");
});
```

Common events:

* click
* mouseover
* keydown
* submit

---

# ⭐ 13. Timing Functions

```
setTimeout(() => console.log("Wait 2 sec"), 2000);
setInterval(() => console.log("Repeating"), 1000);
```

---

# ⭐ 14. JSON

```
let user = {
  name: "John",
  age: 30
};

let str = JSON.stringify(user);
let obj = JSON.parse(str);
```

---

# ⭐ 15. Local Storage

```
localStorage.setItem("name", "Jusair");
console.log(localStorage.getItem("name"));
```

---

# ⭐ 16. Fetch API (GET)

```
fetch("https://jsonplaceholder.typicode.com/posts")
  .then(res => res.json())
  .then(data => console.log(data));
```

---

# ⭐ 17. Async / Await

```
async function load(){
  let res = await fetch("https://jsonplaceholder.typicode.com/users");
  let data = await res.json();
  console.log(data);
}

load();
```

---

# ⭐ 18. ES6 Features

* let / const
* Arrow functions
* Spread operator `...`
* Destructuring

Example:

```
const user = {name: "Jusair", age: 20};
const {name, age} = user;
```

---

# ⭐ 19. Classes

```
class Person{
  constructor(name){
    this.name = name;
  }
}

let p = new Person("John");
```

---

# ⭐ 20. Modules

Import/export between files:

```
export const x = 10;
```

```
import { x } from './file.js'
```

---


