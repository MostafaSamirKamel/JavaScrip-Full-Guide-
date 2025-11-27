# JavaScrip Full Guide



# Basic JavaScript Concepts

## 1.1 What is JavaScript & what we can do with it

**Definition:**  
JavaScript (JS) is a high-level, interpreted programming language primarily used to make web pages interactive.  

**Uses:**  
- Dynamic content update on web pages  
- Form validation  
- DOM manipulation (changing HTML/CSS dynamically)  
- Server-side development (Node.js)  
- Building mobile/web apps (React, Angular, Vue, etc.)  

**History (ES Versions):**  
- **ES5:** Old standard, basic features  
- **ES6/ES2015:** Introduced `let`, `const`, arrow functions, classes, modules  
- **ES7+ (ES2016+):** `async/await`, `includes()`, exponential operator  

**Example:**  
```javascript
console.log("Hello, JavaScript!");
```

---

## 1.2 How to run JavaScript

**Browser Console:**
Open DevTools → Console → type JS

**Script in HTML:**

```html
<script>
  alert("Hello World");
</script>
```

**External JS file:**

```html
<script src="script.js"></script>
```

**Node.js Terminal:**

```bash
node script.js
```

---

## 1.3 Difference between Value and Variable

* **Value:** Actual data (e.g., `10`, `"Hello"`)
* **Variable:** Named storage to hold value

```javascript
let age = 25; // 25 is value, age is variable
```

---

## 1.4 How to declare variables (`var`, `let`, `const`)

* `var`: Function-scoped, hoisted, can be redeclared
* `let`: Block-scoped, hoisted but in temporal dead zone
* `const`: Block-scoped, cannot be reassigned

```javascript
var x = 10;
let y = 20;
const z = 30;
```

**Scopes:** Global, Function, Block

**Hoisting:**

* `var` is hoisted (initialized as undefined)
* `let`/`const` not accessible before declaration

**Temporal Dead Zone:** `let`/`const` cannot be used before declaration in block

---

## 1.5 Data Types

**Primitive:** Number, String, Boolean, Null, Undefined, Symbol, BigInt
**Non-Primitive (Reference):** Object, Array, Function

```javascript
let a = 10; // number
let b = "Hi"; // string
let c = [1,2,3]; // array
let d = {name: "Ali"}; // object
```

---

# 2. Operators

## 2.1 Comparison Operators

```javascript
5 == "5";   // true
5 === "5";  // false
5 != 10;    // true
5 > 3;      // true
```

## 2.2 Arithmetic Operators

```javascript
5 + 2  // 7
5 - 2  // 3
5 * 2  // 10
5 / 2  // 2.5
5 % 2  // 1
```

**Operator Precedence:** `()` > `* / %` > `+ -` > `< > <= >=`

## 2.3 Logical Operators

```javascript
true && false // false
true || false // true
!true        // false
```

## 2.4 Assignment Operators

```javascript
let x = 10;
x += 5; // x = 15
x -= 3; // x = 12
x *= 2; // x = 24
x /= 4; // x = 6
```

---

# 3. Type Concepts

## 3.1 Equality vs Strict Equality

```javascript
5 == "5"  // true (type conversion)
5 === "5" // false (no type conversion)
```

## 3.2 Type Conversion & Coercion

**Explicit:** `Number("5")`, `String(5)`
**Implicit:** JS auto-converts types

```javascript
"5" - 2  // 3
"5" + 2  // "52"
```

## 3.3 Truthy vs Falsy

**Falsy:** 0, "", null, undefined, NaN, false
**Truthy:** Everything else

## 3.4 Strings & Concatenation

```javascript
let a = "Hello";
let b = "World";
console.log(a + " " + b); // "Hello World"
```

---

# 4. Control Flow

## 4.1 If-Else

```javascript
let age = 18;
if(age >= 18){
  console.log("Adult");
} else {
  console.log("Minor");
}
```

## 4.2 Switch Statement

```javascript
let day = "Monday";
switch(day){
  case "Monday":
    console.log("Start week");
    break;
  default:
    console.log("Other day");
}
```

## 4.3 Ternary Operator

```javascript
let age = 20;
let status = age >= 18 ? "Adult" : "Minor";
```

---

# 5. Strict Mode

```javascript
"use strict";
x = 3.14; // Error, x not declared
```

---

# 6. Functions

## 6.1 Function Declaration

```javascript
function greet(name){
  return `Hello ${name}`;
}
```

## 6.2 Function Expression

```javascript
const greet = function(name){
  return `Hello ${name}`;
};
```

## 6.3 Arrow Function

```javascript
const greet = name => `Hello ${name}`;
```

## 6.4 Higher-Order Function

Function that takes or returns a function

```javascript
function higher(func){
  return func();
}
```

## 6.5 Callback Function

```javascript
function greet(name, callback){
  console.log(`Hello ${name}`);
  callback();
}
greet("Ali", () => console.log("Callback executed"));
```

## 6.6 Closure

```javascript
function outer(){
  let count = 0;
  return function(){
    count++;
    return count;
  }
}
const counter = outer();
console.log(counter()); // 1
```

## 6.7 Anonymous Function

```javascript
setTimeout(function(){ console.log("Hi"); }, 1000);
```

## 6.8 `this` keyword inside object

```javascript
const obj = {
  name: "Ali",
  greet: function(){ console.log(this.name); },
};
obj.greet(); // Ali
```

Arrow functions do not have their own `this`; they inherit from outer scope

---

# 7. Objects

## 7.1 Object

```javascript
const person = { name: "Ali", age: 25 };
```

## 7.2 Inheritance

```javascript
const parent = { greet() { console.log("Hi"); } };
const child = Object.create(parent);
child.greet(); // Hi
```

## 7.3 Object Methods

```javascript
Object.keys(person)   // ["name","age"]
Object.values(person) // ["Ali",25]
Object.entries(person) // [["name","Ali"],["age",25]]
```

## 7.4 Add/Delete/Update Properties

```javascript
person.gender = "male";  // add
delete person.age;       // delete
person.name = "Ahmed";   // update
```

## 7.5 Object Destructuring

```javascript
const {name, gender} = person;
```

---

# 8. Arrays

## 8.1 Array & Methods

```javascript
const arr = [1,2,3];
arr.push(4);
arr.pop();
arr.shift();
arr.unshift(0);
```

## 8.2 Cast to Array

```javascript
Array.from("hello"); // ["h","e","l","l","o"]
Array.of(1,2,3);     // [1,2,3]
```

## 8.3 Array Methods

```javascript
arr.slice(1,3);  // [1,2]
arr.splice(1,1); // remove index 1
arr.join("-");   // "1-2-3"
arr.reverse();   // [3,2,1]
arr.sort();      // [1,2,3]
arr.map(x => x*2);
arr.filter(x => x>2);
arr.find(x => x>2);
arr.findIndex(x => x>2);
arr.every(x => x>0);
arr.some(x => x>3);
arr.includes(2); // true
arr.indexOf(2);  // 1
```

## 8.4 Array Mapping / Destructuring

```javascript
const [first, second] = arr; // destructuring
```

## 8.5 Named vs Positional Arguments

JS functions rely on positional arguments; use destructuring objects for named arguments

---

# 9. Loops

## 9.1 For Loop

```javascript
for(let i=0;i<5;i++){
  console.log(i);
}
```

`break` stops loop, `continue` skips iteration

## 9.2 forEach

```javascript
arr.forEach(item => console.log(item));
```

## 9.3 For...of / For...in

```javascript
for(let val of arr) console.log(val); // values
for(let key in person) console.log(key); // keys
```

## 9.4 Spread, Rest, Structured Clone

```javascript
const arr2 = [...arr]; // spread
function sum(...nums){ return nums.reduce((a,b)=>a+b); } // rest
structuredClone(obj); // deep clone
```

---

# 10. Async JavaScript

## 10.1 Callback

```javascript
setTimeout(() => console.log("Hi"), 1000);
```

## 10.2 Promise

```javascript
const p = new Promise((resolve,reject)=>{
  resolve("Done");
});
p.then(res => console.log(res))
 .catch(err => console.log(err))
 .finally(()=>console.log("Finished"));
```

## 10.3 Async/Await

```javascript
async function fetchData(){
  try{
    let data = await fetch("url");
    console.log(await data.json());
  } catch(err){
    console.log(err);
  }
}
```

---

# 11. Extra Points

## 11.1 Sets

```javascript
const set = new Set([1,2,2,3]);
set.add(4);
set.has(2); // true
```

## 11.2 Maps

```javascript
const map = new Map();
map.set("name","Ali");
map.get("name"); // Ali
```

## 11.3 Object Methods

```javascript
Object.assign({}, person); // copy
Object.freeze(person);     // prevent modifications
```
---


## made by Eng* Mostafa_Samir ;


