# 💎 Day 11 💎
 <br>
 <br>

## Objects 🎯🚀 
### this 💫💭

 <br>

> ### 💡Note:
> In JavaScript, the value of this is determined by how a function is called

 <br>

### In function  🔮🫧

A function's this references the execution context for that call, determined entirely by how the function was called.

A this-aware function can thus have a different context each time it's called, which makes it more flexible & reusable.

<br>

### Imlicit bunding ✨⚡️
Refere to the object which invoke it

```javaScript
let work = {
    teacher: "Sarah",
    ask(q){
        console.log(this.teacher,q)
    }
}

// work call ask
work.ask("Why?")
// Sarah Why?
```

<br>

### Sharing 🔥💫

```javaScript
function ask(q){
    console.log(this.teacher,q)
}

let work1 = {
    teacher: "Sarah1",
    ask:ask
    
}

let work2 = {
    teacher: "Sarah2",
    ask:ask
    
}

work1.ask("Why?")
// Sarah1 Why?

work2.ask("Why?")
```

<br>

### Explicit binding 🎆🌟 
the same as prevous but i explictly send this
```javaScript
function ask(q){
    console.log(this.teacher,q)
}

let work1 = {
    teacher: "Sarah1"
}

let work2 = {
    teacher: "Sarah2"
}

ask.call(work1,"Why?")
// Sarah1 Why?

ask.call(work2,"Why?")
// Sarah2 Why?
```

<br>

### Hard binding ✏️📋
Hard binding locks a function's this context to a fixed object, ensuring predictability and preventing accidental changes.

```javaScript
let work = {
    teacher: "Sarah",
    ask(q){
        console.log(this.teacher,q)
    }
}

setTimeout(work.ask,3000) // undefined

// you are passing the method reference without binding it to the work object 
//Therefore, when the ask method is executed after the timeout
```

<br>

### New binding 🍄🍃

```javaScript
function ask(q){
    console.log(this.teacher, q)
    
}
const n = new ask("Why?")

n //undefined Why? 
```

<br>

###  Things that new keyword do ✨🎀

1. Create a brand new empty object
2.  Link that object to another object
3. Call function with this set to the new object
4. If function does not return an object, assume return of this

<br>

> ### 💡Note:
> Thes steps will happen if calling new with empty fun

<br>

### Defualt binding 🔑🎆
refer to the globle window or obj
   
```javaScript
// this works in the browsre console
const t = "Sarah";
function ask(q) {
    console.log(this.t, q);
}
ask("Why?");
// this refer to the globale obj which has t
```

<br>

### Disable this featuer 🌟🌠
use `“use strict”`

<br>
<br>

## this: determination 🚀🌊
 

1. Is the function called by new?  **>>**  `this will be the newly created obj`
2. Is the function called by call() or apply()?   
Note: bind() effectively uses apply()
3. Is the function called on a context object?  **>>** `the object`
4. DEFAULT: global object (except strict mode)  **>>** `global object`

   <br>
   <br>

### arrow functions 🪐🪄

> ### 💁🏻‍♀️Notes:
> 1. arrow fun don’t define a this keyword
> 2. if you put this keyword inside an arrow fun it behave like any other varible, so it will sreach in the outer scope and use it’s this (it will work lexically)
> 3. using new with arrow fun fire an error
> 4. objects are not scope, ex:

<br>

```javaScript
const work = {
    teacher: "Sarah",
    ask: q=>{
        console.log(this.teacher, q)
    }
}

work.ask("Why") // undefined Why
// work is not a scope, so the scope of this is the globale scope
```

<br>

> ### 📌 Advice:
> Only use => arrow functions when you need exical this.


<br>
<br>

## Regular Expressions🔬✏️ 
Regular expressions are used in programming languages to match parts of strings. You create patterns to help you do that matching.

```javaScript
/*
If you want to find the word the in the string The dog chased the cat, 
you could use the following regular expression: 
*/

let testStr = "freeCodeCamp";
let testRegex = /Code/;
testRegex.test(testStr);
```

<br>

### Search for multiple patterns🧐🪩
if at least 0ne accure it will be true

```javaScript
let petString = "James has a pet fish.";
let petRegex = /dog|cat|bird|fish/; 
let result = petRegex.test(petString);
console.log(result) // true

```

<br>

###  Ignore Case While Matching 🎆🌟 
You can match both cases using what is called a flag. There are other flags but here you'll focus on the flag that ignores case - the i flag. 

```javaScript
//  /ignorecase/i. This regex can match the strings ignorecase,
//  igNoreCase, and IgnoreCase.

let myString = "freeCodeCamp";
let fccRegex = /freeCodeCamp/i; // Change this line
let result = fccRegex.test(myString); // true
```

<br>

### .match() 💡💎
extract the actual matches you found with the `.match()` method.

Note that the `.match` syntax is the "opposite" of the `.test` method you have been using thus far:


```javaScript
"Hello, World!".match(/Hello/);
let ourStr = "Regular expressions";
let ourRegex = /expressions/;
console.log(ourStr.match(ourRegex))

/* 
	[
	  'expressions',
	  index: 8,
	  input: 'Regular expressions',
	  groups: undefined
	]
*/
```

<br>
  
### To search or extract a pattern more than once : ✏️📋
you can use the global search flag: g.

```javaScript
let testStr = "Repeat, Repeat, Repeat";
let repeatRegex = /Repeat/g;
testStr.match(repeatRegex);
//["Repeat", "Repeat", "Repeat"]
```

   <br>
   
> ### 💡Note:
> You can have multiple flags on your regex like
> `/search/gi`

 <br>

### dot 🍄🍃
. will match any one character. 

```javaScript
/*
Complete the regex unRegex so that it matches the strings 
run, sun, fun, pun, nun, and bun.
*/

let exampleStr = "Let's have fun with regular expressions!";
let unRegex = /.un/; // Change this line
let result = unRegex.test(exampleStr);
```


<br>

### search for a literal pattern ✨🎀
bag, big, and bug but not bog. You can create the regex /b[aiu]g/

```javaScript
let bigStr = "big";
let bagStr = "bag";
let bugStr = "bug";
let bogStr = "bog";
bigStr.match(bgRegex);
bagStr.match(bgRegex);
bugStr.match(bgRegex);

// insted we can make
let bgRegex = /b[aiu]g/;
bogStr.match(bgRegex);
```

<br>

### Search in a range 🔑🎆

```javaScript

let catStr = "cat";
let batStr = "bat";
let matStr = "mat";
let bgRegex = /[a-e]at/;
catStr.match(bgRegex);
batStr.match(bgRegex);
matStr.match(bgRegex);

/ *
	[
	  'T', 'h', 'e', 'q', 'u', 'i', 'c',
	  'k', 'b', 'r', 'o', 'w', 'n', 'f',
	  'o', 'x', 'j', 'u', 'm', 'p', 's',
	  'o', 'v', 'e', 'r', 't', 'h', 'e',
	  'l', 'a', 'z', 'y', 'd', 'o', 'g'
	]
*/
```

   <br>
   
### Works for numbers 🌟🌠
For example, /[0-5]/ matches any number between 0 and 5, including the 0 and 5.

```javaScript
//possible to combine a range of letters and numbers in a single character

let jennyStr = "Jenny8675309";
let myRegex = /[a-z0-9]/ig;
jennyStr.match(myRegex);

/*
	[
	  'J', 'e', 'n', 'n',
	  'y', '8', '6', '7',
	  '5', '3', '0', '9'
	]
*/
```



 <br>
 <br>
   


## Coding Exercises for challenges: 🔥💪
1. [Using the Test Method](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/regular-expressions/using-the-test-method)

My solution:
```javaScript
let myString = "Hello, World!";
let myRegex = /Hello/;
let result = myRegex.test(myString)
```

2. [Match Literal Strings](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/regular-expressions/match-literal-strings)

My solution:
```javaScript
let waldoIsHiding = "Somewhere Waldo is hiding in this text.";
let waldoRegex = /Waldo/; // Change this line
let result = waldoRegex.test(waldoIsHiding);
```

3. [Match a Literal String with Different Possibilities](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/regular-expressions/match-a-literal-string-with-different-possibilities)

My solution:
```javaScript
let petString = "James has a pet cat.";
let petRegex = /dog|cat|bird|fish/; // Change this line
let result = petRegex.test(petString);
```

4. [Ignore Case While Matching](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/regular-expressions/ignore-case-while-matching)

My solution:
```javaScript
let myString = "freeCodeCamp";
let fccRegex = /freeCodeCamp/i; // Change this line
let result = fccRegex.test(myString);
```

5. [Extract Matches](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/regular-expressions/extract-matches)

My solution:
```javaScript
let extractStr = "Extract the word 'coding' from this string.";
let codingRegex = /coding/; // Change this line
let result = extractStr.match(codingRegex); // Change this line
```

6. [Find More Than the First Match](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/regular-expressions/find-more-than-the-first-match)

My solution:
```javaScript
let twinkleStar = "Twinkle, twinkle, little star";
let starRegex = /Twinkle/gi; // Change this line
let result = twinkleStar.match(starRegex); // Change this line
```

7. [Match Anything with Wildcard Period](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/regular-expressions/match-anything-with-wildcard-period)

My solution:
```javaScript
let exampleStr = "Let's have fun with regular expressions!";
let unRegex = /.un/; // Change this line
let result = unRegex.test(exampleStr);
```

8. [Match Single Character with Multiple Possibilities](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/regular-expressions/match-single-character-with-multiple-possibilities)

My solution:
```javaScript
let quoteSample = "Beware of bugs in the above code; I have only proved it correct, not tried it.";
let vowelRegex = /[aeiou]/ig; // Change this line
let result = quoteSample.match(vowelRegex); // Change this line
```

9. [Match Letters of the Alphabet](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/regular-expressions/match-letters-of-the-alphabet)

My solution:
```javaScript
let quoteSample = "The quick brown fox jumps over the lazy dog.";
let alphabetRegex = /[a-z]/ig; // Change this line
let result = quoteSample.match(alphabetRegex); // Change this line
```

10. [Match Numbers and Letters of the Alphabet](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/regular-expressions/match-numbers-and-letters-of-the-alphabet)

My solution:
```javaScript
let quoteSample = "Blueberry 3.141592653s are delicious.";
let myRegex = /[h-s2-6]/ig; // Change this line
let result = quoteSample.match(myRegex); // Change this line
```

 <br>
 <br>
  
## Problem Solving: 💪🚀
1. [Two numbers are positive](https://www.codewars.com/kata/602db3215c22df000e8544f0/train/javascript)

My solution:
```javaScript
const  twoArePositive = (a, b, c)=> {return [a,b,c].filter(i=>i>0).length===2}
```

2. [Get the addresses of all Google Sheets cells in the range](https://www.codewars.com/kata/62c376ce1019024820580309/train/javascript)

My solution:
```javaScript
function getCellAddresses(range) {
  const letters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
  const ans = [], [start, end] = range.split(":")
  
  if (start === end)return []
  for (let i = parseInt(start.slice(1)); i <= parseInt(end.slice(1)); i++) {
    const col = []
    for (let j = letters.indexOf(start[0]); j <= letters.indexOf(end[0]); j++) {
      col.push(letters[j] + i)
    }
    ans.push(...col)
  }
 return ans 
}
```

3. [Count characters in your string](https://www.codewars.com/kata/52efefcbcdf57161d4000091/train/javascript)

My solution:
```javaScript
 function count(sring) {
    let ans = {}
    for (let i of sring)
        ans[i] = ans[i] === undefined ? 1 : ans[i] +1
    return ans;
  }
```
