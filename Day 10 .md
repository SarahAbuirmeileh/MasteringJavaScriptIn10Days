# 💎 Day 10 💎
 <br>
 <br>

## Advanced Scope 🎨🌊:

### lexical scope 🔮🫧

The idea that a compiler is figuring out all the scopes ahead of time befor being executed 

lex → the first stage of parsing

<br>

### lexical scope VS. dynamic scope ✨ ⚡️

The scope of **dynamic scope** is determined based upon a conditions at runtime (where this function has been called).

while **lexical scope** is determined at auther time.

```javaScript
const n = "Sarah"

function f(){
    console.log(n)
}

function ff(){
    const n = " Hello"
    f()
}

ff()
// Sarah => lexical
// Hello => dynamic
```

<br>

## Function Scoping 🍄🍃

> ### 📌Principle of privilage:
> You  should default to keep evreything private and only exposing the minimal necessary

<br>

```javaScript
let x
try {
    x = funMayReturnError(1)
}
catch (error) {
    x = 5
}

// using anaymaous function 
let x = (function bringX() {
    try {
        return funMayReturnError(1)
    }
    catch (error) {
        return 5
    }
})
```

<br>

### IIFE (Immediately Invoked Function Expression) 💫💭

```javaScript
function f (){
    console.log("hello")
}
f()

// we can do
// also it may do not have name
(function  ff (){    // not a functon declertion
    console.log("hello")
})()
```

<br>

### Block Scoping 🔮🫧


> ### 💡Note:
> Block(curly braces) are not scopecauntil they have let or const inside them

<br>

### Hoisting ✨⚡️
- **Hoisting** is the process of moving variable and function declarations to the top of their scope.
- Variable declarations are hoisted but not their assignments. They are accessible but have an initial value of `undefined`.
- Function declarations are also hoisted, allowing them to be called before they are defined.
- Hoisting does not apply to function expressions, arrow functions, or variables declared with `let` or `const`.

<br>


```javaScript
var t = "1"
o()

function o(){
    console.log(t)
    var t = "2"
}
o() //undefined
```

   <br>
   <br>
   
### let & hoisting ✨☄️ 
Wa can’t say that let dosn’t have hoisting, insted it’s kind of uninitioalized state

```javaScript
var t = "1"

{
    console.log(t)
    let t = "2"
}

// error
// but should print 1, beacuse it's in the outer scope, 
```

<br>

## Closure 🎯🚀 
Closure is when a function “remembers” its lexical scope even when the function is executed outside that lexical scope.


```javaScript
for (var i=1; i<=3; i++){
    setTimeout(()=>{
        console.log(i)
    },1000*i)
}

/*
	there is only one i variable that is shared across all the iterations of the
  loop. When the setTimeout functions are executed after the delays, they all 
  use the same value of i, which is 4
*/

for (let i=1; i<=3; i++){
    setTimeout(()=>{
        console.log(i)
    },1000*i)
}

/*
	each iteration of the loop creates a new and separate i variable. As a result, 
	when the setTimeout functions are executed after the delays, each callback 
	captures its own unique value of i. It
*/

```

<br>
<br>

## Modules 💫⏳

Modules encapsulate data and behavior (methods) together. The state (data) of a module is held by its methods via closure.

<br>

 > ### 💡Note:
 > Namespace, NOT a module

 <br>
 <br>

    
## Prototypes 🌌⚡️ 

<br>

> ### 🪐Notes:
> 1. Objects are built by "constructor calls" (via new)
> 2. A "constructor call" makes an object “❌based on❌” its own prototype
> A "constructor call" makes an object “✅linked to✅” its own prototype

<br>

### example: 🪄💭
![Screenshot from 2023-07-24 08-58-28](https://github.com/SarahAbuirmeileh/test/assets/127017088/a756f3aa-5ac8-4428-b281-176049ceed39)


<br>


### Explaintion: 🔎🔮

![Screenshot from 2023-07-24 08-58-36](https://github.com/SarahAbuirmeileh/test/assets/127017088/73e412b3-26ea-4ce2-b4b2-e61d4b220144)

<br>

> ### Explaining: ✨🎨
> when we add ask to prototype, it’s added to the prototype object
> when we creat deepJS we didn’t copy the prototype  of workshop insted it has a link to it, if we try to access sth isn;t exist in the deepJS it search in workShop if not exist it search in > the JS main prototype (inside of it there is toString())


<br>

## Clarifying Inheritance:☄️🌍
<br>
In c++ & Java

<br>

![Screenshot from 2023-07-24 09-52-37](https://github.com/SarahAbuirmeileh/test/assets/127017088/20443b1d-0678-4851-85a8-1f6205bcd5de)

<br>

in JS

![Screenshot from 2023-07-24 09-53-15](https://github.com/SarahAbuirmeileh/test/assets/127017088/97518be4-993f-44e1-b15f-86f9f4e6aa6b)

   <br>

> ### 💻Note:
> **OLOO:** 🔥 
> Objects Linked to Other Objects

   <br>

   <br>
   
## types✨☄️

[more details and information](https://github.com/getify/Typl)

<br>

### Motivations to use TS 👩🏻‍💻🤔

1. Only standard JS syntax
2. Compiler and Runtime (both optional)
3. Completely configurable (ie, ESLint)
4. Main focus: inferring or annotating
values; Optional: "static typing"
5. With the grain of JS, not against it

<br>
<br>

   
## Functional Programming🔥💫
<br>

> ### 📝Note:
>  Functional programming is a good habit. It keeps your code easy to manage, and saves you from sneaky bugs. 

<br>
<br>

## Coding Exercises for challenges: 🔥💪
1. [Catch Off By One Errors When Using Indexing](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/debugging/catch-off-by-one-errors-when-using-indexing)

My solution:
```javaScript
function countToFive() {
  let firstFive = "12345";
  let len = firstFive.length;
  // Only change code below this line
  for (let i = 0; i < len; i++) {
  // Only change code above this line
    console.log(firstFive[i]);
  }
}

countToFive();
```

2. [Use Caution When Reinitializing Variables Inside a Loop](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/debugging/use-caution-when-reinitializing-variables-inside-a-loop)

My solution:
```javaScript
function zeroArray(m, n) {
  // Creates a 2-D array with m rows and n columns of zeroes
  let newArray = [];
  let row = [];
  for (let i = 0; i < m; i++) {
    // Adds the m-th row into newArray

    for (let j = 0; j < n; j++) {
      // Pushes n zeroes into the current row to create the columns
      row.push(0);
    }
    // Pushes the current row, which now has n zeroes in it, to the array
    newArray.push(row);
    row =[]
  }
  return newArray;
}

let matrix = zeroArray(3, 2);
console.log(matrix);

```

3. [Prevent Infinite Loops with a Valid Terminal Condition](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/debugging/prevent-infinite-loops-with-a-valid-terminal-condition)

My solution:
```javaScript
function myFunc() {
  for (let i = 0; i <= 4; i += 2) {
    console.log("Still going!");
  }
}
```

4. [Learn About Functional Programming](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/learn-about-functional-programming)

My solution:
```javaScript
// Function that returns a string representing a cup of green tea
const prepareTea = () => 'greenTea';

/*
Given a function (representing the tea type) and number of cups needed, the
following function returns an array of strings (each representing a cup of
a specific type of tea).
*/
const getTea = (numOfCups) => {
  const teaCups = [];

  for(let cups = 1; cups <= numOfCups; cups += 1) {
    const teaCup = prepareTea();
    teaCups.push(teaCup);
  }
  return teaCups;
};

// Only change code below this line
const tea4TeamFCC = getTea(40);
// Only change code above this line
```

5. [Understand Functional Programming Terminology](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/understand-functional-programming-terminology)

My solution:
```javaScript
// Function that returns a string representing a cup of green tea
const prepareGreenTea = () => 'greenTea';

// Function that returns a string representing a cup of black tea
const prepareBlackTea = () => 'blackTea';

/*
Given a function (representing the tea type) and number of cups needed, the
following function returns an array of strings (each representing a cup of
a specific type of tea).
*/
const getTea = (prepareTea, numOfCups) => {
  const teaCups = [];

  for(let cups = 1; cups <= numOfCups; cups += 1) {
    const teaCup = prepareTea();
    teaCups.push(teaCup);
  }
  return teaCups;
};

// Only change code below this line
const tea4GreenTeamFCC = getTea(prepareGreenTea, 27);
const tea4BlackTeamFCC = getTea(prepareBlackTea, 13);
// Only change code above this line

console.log(
  tea4GreenTeamFCC,
  tea4BlackTeamFCC
);
```

 <br>
 <br>
  
## Problem Solving: 💪🚀
1. [Find the capitals](https://www.codewars.com/kata/539ee3b6757843632d00026b/train/javascript)

My 1st solution:
```javaScript
const capitals = function (word) {
    return word.split('').map((l,i)=>{ return /^[A-Z]$/.test(l)? i : null}).filter(l=> l!=null)
};
```

My 2nd solution: 
```javaScript
const capitals = word => { return word.match(/[A-Z]/g).map( x => { return word.indexOf(x) }) }
```

2. [IP Validation](https://www.codewars.com/kata/515decfd9dcfc23bb6000006/train/javascript)

My solution:
```javaScript
function isValidIP(str) {
    return str.split('.').filter(v => {return +v <= 255 && +v >= 0 && v.length == String(+v).length;}).length == 4;    
  }
```


 
