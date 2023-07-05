# 💎 Day 2 💎
 <br>
 <br>
   
## Operators 💻 🔥
### Plus sign (+) 💫

Has several different uses:

1. Adding number : (ex: 2 + 5)
2. Concatenate strings: at least on side is string (ex: “Sarah” + 1)
<br>

### typeof 🔮🫧
operator returns a string indicating the type of the operand's value.

```javaScript
// Exercise
// 1. The total number of siblings of your parents
9 + 1

// 2. The average number of hours you slept this week
(4 + 6 + 5.5 + 4.5 + 3.5 + 4 + 5 + 3)/7

// 3. The number of dogs you'd pet in a week if you pet 1 dog per hour while awake
1 * (24-8) * 7
```
<br>

### Expenaioation (**) ✨ ⚡️
```javaScript
3**2 // 9
2**5 // 32
```
<br>

### Strict VS. loosey-goosey: ⏳🤔
```javaScript
 //   loosey-goosey      vs.	         strict	
      1 === 1     /* ✅	 vs.	 ✅  */   1 == 1 
    "1" === "1"	  /* ✅  vs.  ✅	 */ "1" == "1" 
      1 === "1"	  /* ❌	 vs.  ✅	 */   1 == "1"
```
   <br>
   <br>
   
## Expressions✨☄️
An expression evaluates (aka resolves) to a value
```javaScript
// ex
"Frontend" + "Masters"
```
<br>

### **Variables:** 🎯🚀

**Variable names:** camelCase
👉❓'variables contain values?  
     variables contain point to values'

```javaScript
let s = "Sarah"
let sa = s
s = "sarah"
console.log(sa)
 // the value of sa won't change
```
<br>

### **Statements vs. Expressions** 👩🏻‍💻🤔

An **expression** "asks" JS for a value
```javaScript
myAssignedVariable  // what is the value of my variable
6 + 4               // what is the value of this summation
document.getElementById("board")
```

A **statement** "tells" JS to do something, actions we want JS to do it

```javaScript
// e.g: declare/assign a variable
let ten = 6 + 4;
myDeclaredVariable = "new value";
let board = document.getElementById("board");

function add(x, y) {
    return x + y;
}

let biggest;
if (5 > 4) {
    biggest = 5;
} else {
    biggest = 4;
}
for (let character of "string") {
    console.log(character);
}
```
   <br>
   <br>
   
## Arrays 🔥💫
**Arrays** let us keep multiple values together in a single collection

```javaScript
// ex
let synonyms = ["plethora", "array", "cornucopia"];
synonyms.length // Like strings, arrays have a length

synonyms[1]
synonyms.indexOf("cornucopia") // And each value has an index

synonyms.includes("plethora") // check if an array contains a certain value

// Unlike strings, we can modify arrays
synonyms[1] = "variety";
let lastItem = synonyms.pop();
synonyms.push("multitude");

let mixedArray = ["pop", 6, "squish", false, document];
// Arrays can hold any type of items, or mix and match!

"Sarah" == ["Sarah"]      // ✅
"Sarah" === ["Sarah"]     // ❌
"Sarah" === ["Sarah"][0]  // ✅

["a","c","b"].sort()  // ['a', 'b', 'c']
[100, 2 ,50].sort()   // [100, 2 ,50].sort() 
// it converts the elemnts into strings then sort them


// convert it to string
["lions", "tigers", "bears oh!"].join(" & ") // 'lions & tigers & bears oh!'
[1 , 2].join("@")  // '1@2'

[1, 2, 3].concat([4, 5, 6]) // [1, 2, 3, 4, 5, 6] 

```
<br>

### **Mutating data:** ✏️📝 
In JS certian values behave differently than certian other values that we might think are similar

```javaScript
let abcArray = ["a", "b", "c"];
abcArray[1] = "d";
abcArray;  // ['a', 'd', 'c']

let abcString = "abc";
abcString[1] = "d";
abcString; // 'abc'
```
<br>

### Mutable vs. Immutable: 🧐🪩
"**Mutable**" data can be edited (e.g. **Arrays**)
"**Immutable**" data always stays the same (e.g. **strings** & **other primitives**)
 
 <br>

### 👉❓Do these do the same thing?
```javaScript
let numbers1 = [1, 2, 3];
let result1 = numbers1.push(4); 
numbers1;  // [1, 2, 3, 4]
 
let numbers2 = [1, 2, 3];
let result2 = numbers2.concat([4]);
numbers2; // [1, 2, 3]
```
<br>
<br>

> ### 👉 **See this** 👈
> Some actions "**mutate**" an array (e.g. `oldArray.push(newValue)`)
> aka(called) change the array ***in-place***
> Other actions **do** ***not* mutate** the original array, but instead create a new copy (e.g. `oldArray.concat(otherArray)`)

   <br>

### Variables themselves can also be (im)mutable  🎆🌟 

```javaScript
let letVariable = "original value";
letVariable = "new value";

const constVariable = "original value";
constVariable = "new Value";
```
<br>

### Immutable variable with mutable value 💡💎
What happens when we use const with a mutable value like an array?
```javaScript
const operands = [4, 6];
const sum = operands[0] + operands[1]; //  10

operands[0] = 5;
const newSum = operands[0] + operands[1]; // 11
```

<br>
<br>

> ### 📌 Advises:
> 1.  If you have the choice keep thing immutable
> 2.  The default for array is const unlees you have a good reson to use let      

<br>

### Copying an array: ✏️📋

```javaScript
let array1 = [1,2,3,4]
let array2= array1
array1[0]=5

array1 // [5,2,3,4]
array2 // [5,2,3,4]

// Even if I used const >> the same result
```

   <br>
   <br>
   
## Objects  🍄🍃
**Objects** collect multiple values together to describe more complex data
**objects** let us *point at* related values using *properties* in the object.

```javaScript
// We can access edit and add any property using "."
const js = {
    name: "JavaScript",
    abbreviation: "JS",
    isAwesome: true,
    officialSpec: "ECMAScript",
    birthYear: 1995,
    creator: "Brendan Eich"
};
 
js.name
js.name.startsWith("Java")
js.learn = true
```
<br>

### Feezing an object: 🥶🧊 
Object.freeze() : static method freezes an object.
```javaScript
const obj = {
  prop: 42
};
Object.freeze(obj);

obj.prop = 33;  // Throws an error in strict mode
console.log(obj.prop); // Expected output: 42
```

```javaScript
// other example to freez just proparty
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
<br>

###  **Methods:** ✨🎀
Properties can point to functions too.
We call function-properties "methods" on objectsCopy
```javaScript
const dog = {
    name: "Ein",
    breed: "Corgi",
    speak: function () {
        console.log("woof woof");
    }
}
dog.speak();
```
<br>

### Built in objects:🔑🎆
1. document
2. array
3. console : has methods : log, error 
4. Math
5. Function

   <br>
   <br>
   
## Tic Tac Toe! 🌟🌠
```HTML
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

```javaScript
/*
1. Set up the players Create a players array containing 2 objects
   representing each player 
   Each object should store the player's name and symbol (X or O)
   Display each player's name in the appropriate element in the page Play! 
   Take turns placing symbols in the board On each turn: Retrieve the square 
   you want to play in Set the square's text to your player's symbol
*/

let players = [{name: "Sarah", symbol : "X"},
               {name: "Evryone else", symbol : "O"}]

document.querySelector("#p1-name").textContent = players[0].name
document.querySelector("#p2-name").textContent = players[1].name

/*
2. Play!
   Take turns placing symbols in the board
   On each turn:
   Retrieve the square you want to play in
   Set the square's text to your player's symbol
*/

squares = document.getElementsByClassName("square")
squares[0].textContent=players[0].symbol
squares[4].textContent=players[1].symbol
```

 <br>
 <br>
   

## 💡 **Notes:**
1. **typeof**: it’s an operator
2. **push** will affect the original array while **concat** don’t, it creats a new array
3. We can mute the array even if we declared it using const
4. **Objects** are muttable
5. **console** is a **built in** **object** that has a proparty called **log**
6. **Strings** are ***primitive** values* (**not objects**) but JS automatically wraps them in `String` objects

 <br>
 <br>

## Coding Exercises for challenges: 🔥💪
1. [Use the Rest Parameter with Function Parameters](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/use-the-rest-parameter-with-function-parameters)
My solution:
```javaScript
const sum = (...args) => {
  
  return args.reduce((sum,a)=>{return sum+a} ,0)
}
```

2. [Use the Spread Operator to Evaluate Arrays In-Place](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/use-the-spread-operator-to-evaluate-arrays-in-place)
My solution:
```javaScript
const arr1 = ['JAN', 'FEB', 'MAR', 'APR', 'MAY'];
let arr2;

arr2 = [...arr1];  // Change this line

console.log(arr2);
```

3. [Use Destructuring Assignment to Extract Values from Objects](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/use-destructuring-assignment-to-extract-values-from-objects)
My solution:
```javaScript
const HIGH_TEMPERATURES = {
  yesterday: 75,
  today: 77,
  tomorrow: 80
};

// Only change code below this line

const {today,tomorrow} = HIGH_TEMPERATURES;

// Only change code above this line
```

4. [Use Destructuring Assignment to Assign Variables from Objects](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/use-destructuring-assignment-to-assign-variables-from-objects)
My solution:
```javaScript
const HIGH_TEMPERATURES = {
  yesterday: 75,
  today: 77,
  tomorrow: 80
};

// Only change code below this line
  
const {today:highToday, tomorrow:highTomorrow} = HIGH_TEMPERATURES

// Only change code above this line
```

5. [Use Destructuring Assignment to Assign Variables from Nested Objects](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/use-destructuring-assignment-to-assign-variables-from-nested-objects)
My solution:
```javaScript
const LOCAL_FORECAST = {
  yesterday: { low: 61, high: 75 },
  today: { low: 64, high: 77 },
  tomorrow: { low: 68, high: 80 }
};

// Only change code below this line
  

const { today: { low: lowToday, high: highToday }}=LOCAL_FORECAST

// Only change code above this line
```

 <br>
 <br>
  
## Problem Solving: 💪🚀
1. [How good are you really?](https://www.codewars.com/kata/5601409514fc93442500010b/train/javascript)
My solution:
```javaScript
function betterThanAverage(classPoints, yourPoints) {
  return classPoints.reduce((sum,c)=>{return sum + c },yourPoints)/(classPoints.length+1)<= yourPoints
}

```

2. [Duplicate Encoder](https://www.codewars.com/kata/54b42f9314d9229fd6000d9c/train/javascript)
My solution:
```javaScript
function duplicateEncode(word){
  word = word.toLowerCase()
  let m = new Map()
  for(let i =0; i<word.length; i++)
    m[word[i]]===undefined? m[word[i]] =1 : m[word[i]]++
  let ans = ""
  for (let i=0; i<word.length; i++)
    m[word[i]] ===1 ? ans+="(" : ans+=")"
  return ans
}

```
