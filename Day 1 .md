# 💎 Day 1 💎
 <br>
 <br>
   
## Intoduction 💻 📑
* JS is dynamic programming language used in websites to make it interactive,  we use it to talk to web browser, hence it’s called "programming language of the web".
* Created by Brendon Eich in 1995  (10 days).
* Used to interact  and modify HTML.
* **Where do we use JS?**
1. Browsers
2. Servers: Node.js
3. Imbedded devices
   <br>
   <br>
## DOM (Document Object Model) ✨☄️
it’s a Javascript built in object that repersent the whole web page.
### Finding elements:
* Title of the page: `document.title`
* The whole HTML body <body> : `document.body`
* Body elements in HTML (ex: header & divs) :  `document.body.children` 
* Get specific element using id:  `document.getElementById("board")` 
* The same as previous but this to CSS sector:  `document.querySelector("#board")`   return the same result as above
* Get **all** the elements with the same tag:  `document.getElementsByTagName("h1")` 
* In SCC sector: `document.querySelectorAll("h1")`
* Get element with same class :  `document.getElementsByClassName("player")` 
* CSS sector :  `document.querySelectorAll(".player")` 
* Finding the nubmer of elements: `document.getElementsByClassName("player").length` or in CSS `document.querySelectorAll(".player").length`

* Get the text element inside the selected element or container `document.getElementById("p1-name").`
   <br>
   <br>
#### HTML code:🔥💫
```javaScript
<body>
    <header>
    <h1>Tic Tac Toe</h1>
    <h2>A game you know</h2>


    <div id="players">
        <p id="p1" class="player">Player <span id="p1-symbol">X</span>: <span id="p1-name">Anjana</span></p>
        <p id="p2" class="player">Player <span id="p2-symbol">O</span>: <span id="p2-name">Marc</span></p>
    </div>
    </header>

    <div id="board">
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
    </div>
</body>
```
   <br>
   <br>
   
### **Editing the DOM with JS:** 📋✏️

I can use the equal operator `=` to assign a value to any element. Tow ways:

1. .textContent = “”
2. .appned(””)

#### Examples:

```JavaScript
document.title = "My Page"
// change the title

document.getElementById("p1-name").textContent = "Sofia" 
//replace the text of the #p1-name element

document.getElementById("p1-name").append(" & friends")
// add to the end of the element's current text

document.getElementsByTagName("h2")[0].textContent = "Hello" 
// return an array

document.querySelector("header h2").textContent = "sarah" 
// the same as previous 

document.querySelector("h1").append(" !!!")

document.querySelector("header h1").textContent="Sarah"
```
   <br>
   <br>
   
## Values & Data Types 🔑🌠
### Values
Are chunks of information we want to work with, that information (data) can be of different types:

### JS has two kinds of data:

* Primitive types
1. **string :**  (ex: “Sarah”, ‘Sarah’ , `Sarah`, "20")
2. **number :** (ex: 9, 525600, 3.14. 1.2e9, Infinity)
3. **boolean**: (ex: true, false)
4. **undefined**: there was supposed to be sth. but accidentaly there is nothing
5. **null**: I ment to be nothing here.
    
* Objects
    
     (e.g. `document` & friends)
   <br>
   <br>

👉 **typeof:** operator returns a string indicating the type of the operand's value.
###Exampls:

```javaScript
typeof("21")   // string
typeof(false)  // boolean
typeof(null)   // object
typeof("some string".length) // number
```
   <br>
   <br>
   
### String 📜🎆
Sequence of  characters are in a specific order, each gets a number, starting at 0

#### Examples:
```javaScript
"ALOHA"[0]      // “A”
"ALOHA".length  // 5

"ALOHA".indexOf("L")   //1 
// What's the index of the first accourance of specific character
// if not exist will return -1

"ALOHA".includes("HA")  // true
// "ALOHA".includes("HA")

"ALOHA".startsWith("AL") // true
// Does this string start with some other string?

"ALOHA".indexOf("HA") // 3
// At what index does this substring begin?

"ALOHA" + "!"
 // Connecting strings together

"ALOHA".toLowerCase() // "aloha"
```
 <br>
   
### Exercises: ⚙️🔥
```javaScript
// Exercises
// 1. Add your last name in the players listing
document.getElementById("p1-name").append(" abu irmeileh")

// 2. Retrieve the first "T" in the page title
document.title.indexOf("T")

// 3. Answer whether the page title contains the string "JavaScript"
document.title.includes("JavaScript")

// 4. Capitalize the heading "Tic Tac Toe"
document.querySelector("header h1").textContent =  // to appear in the page
document.querySelector("h1").textContent.toUpperCase()
```
 <br>

## 💡 **Notes:**
1. **[developer.mozilla.org](http://developer.mozilla.org) :** very helpful in programming
2.  When reloading the page evry changes in browser console won’t be saved
3. null is primitive data type, but when we write typeof null it’s an object !!
4. if I declare an array using const key word I still can change it's element by index
5. To ensure your data doesn't change, JavaScript provides a function Object.freeze to prevent data mutation.
6.  We can not change string by index
 <br>
 <br>

## Coding Exercises for challenges 🔥💪
1. [Compare Scopes of the var and let Keywords](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/compare-scopes-of-the-var-and-let-keywords)
My solution:
```javaScript
function checkScope() {
    let i = 'function scope';
    if (false) {
      i = 'block scope';
      console.log('Block scope i is: ', i);
    }
    console.log('Function scope i is: ', i);
    return i;
  }

```

2. [Mutate an Array Declared with const](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/mutate-an-array-declared-with-const)
My solution:
```javaScript
const s = [5, 7, 2];
function editInPlace() {
  // Only change code below this line
  s[0]=2
  s[1]=5
  s[2]=7
  // Using s = [2, 5, 7] would be invalid

  // Only change code above this line
}
editInPlace();
```

3. [Prevent Object Mutation](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/prevent-object-mutation)
My solution:
```javaScript
function freezeObj() {
    const MATH_CONSTANTS = {
      PI: 3.14
    };
    // Only change code below this line
  
    Object.freeze(MATH_CONSTANTS)
  
    // Only change code above this line
    try {
      MATH_CONSTANTS.PI = 99;
    } catch(ex) {
      console.log(ex);
    }
    return MATH_CONSTANTS.PI;
  }
  const PI = freezeObj()
```

4. [Use Arrow Functions to Write Concise Anonymous Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/use-arrow-functions-to-write-concise-anonymous-functions)
My solution:
```javaScript
const magic = ()=> {
  return new Date();
};
```

5. [Write Arrow Functions with Parameters](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/write-arrow-functions-with-parameters)
My solution:
```javaScript
const myConcat = (arr1, arr2) =>{
  return arr1.concat(arr2);
};

console.log(myConcat([1, 2], [3, 4, 5]));
```

6. [Set Default Parameters for Your Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/set-default-parameters-for-your-functions)
My solution:
```javaScript
// Only change code below this line
const increment = (number, value=1) => number + value;
// Only change code above this line
```
 <br>
 <br>
  
## Problem Solving 💪🚀

1. [Up and down, the string grows](https://www.codewars.com/kata/644b17b56ed5527b09057987/train/javascript)
My solution:
```javaScript
const STRANGE_STRING = "Aß"
```

2. [Array.diff](https://www.codewars.com/kata/523f5d21c841566fde000009/train/javascript)
My solution:
```javaScript
function arrayDiff(a, b) {
  return a.filter(e=>{
    return !b.some(ee=>{return ee ===e})
  })
}
```

3. [Beginner Series #3 Sum of Numbers](https://www.codewars.com/kata/55f2b110f61eb01779000053/train/javascript)
My solution:
```javaScript
function getSum(a, b)
{
  let aa = Math.min(a,b)
  let bb = Math.max(a,b)
  console.log(aa,bb)
  let ans =0
  for(let i =aa; i<=bb; i++)
    ans+=i
  return ans
}
```


