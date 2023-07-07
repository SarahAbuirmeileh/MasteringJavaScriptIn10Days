# 💎 Day 5 💎
 <br>
 <br>
   
##  Data Fetching & Promises 🎯🚀 

 <br>
 
> ### 👉 see that 👈

> **URLs** point to resources on the web
> **APIs (Application Programming Interface)** services that are exposing a whole bunch of data at acertin URLs**,** provide URLs that point at data we care about

 <br>

###  Promise: 💫🌌
Object represents the eventual completion (or failure) of an asynchronous operation and its resulting value (represent a value that we don’t have yet)

#### Promises can be in 3 possible states:🔮🫧

1. `pending`: still waiting for the value, hang tight
2.  fulfilled (aka `resolved`): finally got the value, all done 
3. `rejected`: sorry couldn't get the value, all done
   
<br>

### await: ✨⚡️
await lets us tell JS to stop and wait for an asynchronous operation to finish

```javaScript
let response = await fetch("https://dog.ceo/api/breed/hound/list");
console.log(response);
```

<br>

### .json() 💻🔥
It's body contains the data we care about

But we have to read the body somehow

> #### 💡 Note
> json() is async fun

<br>

```javaScript
// Calling the .json() method on the response parses its body as a JSON object
let r = await response.json()
```

<br>
<br>

##  Destructuring Data ⏳🤔
Destructuring is a fancy way of declaring multiple variables at once

By "extracting" values from an object with their property names

```javaScript
const spices = [{name:"Sarah", nickname:"queen"}]
let {name, nickname} = spices[0];
```
   <br>

### Use it with array ✨☄️  

```javaScript
const [one, tow ] = [1,2]

// We can ignore the values in the array we don't need
const [,,melB] = spices;

// We can use ... to collect remaining values
 const [babySpice, ...adultSpices] = spices;
```

<br>

### Exercise:  👩🏻‍💻🤔

```javaScript
/*
	In your Doggo Fetch file, follow TODO 2 to complete the getBreedFromURL 
	function with destructuring
	
	The string method .split() will be useful it returns an array of substrings
	 by splitting a string at a certain character: 
*/
let part = "https://images.dog.ceo/breeds/poodle-standard/n02113799_2280.jpg"
         .split("/") // parts of url
let name =  part[4] // the name
let removed = name.split("-")
let joinedName = removed.join(" ")
let finalName = joinedName.trim() // to remove the white spaces if the name 
																	// just one word
```

<br>
<br>

## async 🔥💫
### Exercise:  ✏️📝 
```javaScript
/*
In your Doggo Fetch file, follow TODO 3 to fill in the async function body

Use what we've learned about how to fetch, parse, and extract the data we need
*/
async function fetchMessage(url) {
        const response = await fetch(url);  // Fetch the resource at the given URL
        const {message} = await response.json(); // Parse the response as JSON & remember its 'message' value
        return message;
    }
```

<br>

### createElement() 🧐🪩
In an HTML document, the document.createElement() method creates the HTML element specified by tagName

```javaScript
const button = document.createElement("button")
```

   <br>
   
### appendChild() 🎆🌟 
The appendChild() method of the Node interface adds a node to the end of the list of children of a specified parent node.

```javaScript
options.appendChild(button)
```

<br>
<br>

## Modules 🍄🍃
Modules let us split big codebases across multiple files

```javaScript
<script type="module">
    //...
</script>

// JS modules work differently from JS scripts
```

<br>

### Module scope: 🎀💎

> ### 💡 Note:
> We can't access variables and function in the web console

<br>
<br>

## Debugging: ✏️📋
We can console.log() (or .warn() or .error()) is one way to understand what's happening when your program runs

```javaScript
function whyIsntThisWorking(input) {
    console.log("Well at least we got this far");
    console.log(input);
    return thingThatDoesntWork(input);
}
```

<br>
You can also use the browser's debugger to pause JS and inspect what's happening

```javaScript
function whyIsntThisWorking(input) {
    debugger;
    return thingThatDoesntWork(input);
}
```
The debugger statement creates a breakpoint where JS will pause and let you look around

<br>
<br>


## 💡 **Notes:**
1. **`trim()`** method removes whitespace from both ends of a string and returns a new string, without modifying the original string.
2. In `JS` we can creat any element we want to appeare in HTML page.
   
 <br>
 <br>

## GSG Task 🔥🌠:
[Task discription](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week1-day3-task/task.md)

[My solution](https://github.com/SarahAbuirmeileh/Alive-Character-List-Project)

 <br>
 <br>
 
## Coding Exercises for challenges: 🔥💪
1. [Reuse JavaScript Code Using import](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/reuse-javascript-code-using-import)
My solution:
```javaScript
  import {uppercaseString, lowercaseString} from './string_functions.js'
// Only change code above this line

uppercaseString("hello");
lowercaseString("WORLD!");
```

2. [Use * to Import Everything from a File](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/use--to-import-everything-from-a-file)
My solution:
```javaScript
import * as stringFunctions from "./string_functions.js";
// Only change code above this line

stringFunctions.uppercaseString("hello");
stringFunctions.lowercaseString("WORLD!");
```

3. [Create an Export Fallback with export default](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/create-an-export-fallback-with-export-default)
My solution:
```javaScript
export default  function subtract(x, y) {
  return x - y;
}
```

4. [Import a Default Export](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/import-a-default-export)
My solution:
```javaScript
import subtract from './math_functions.js'
// Only change code above this line

subtract(7,4);
```

5. [Create a JavaScript Promise](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/create-a-javascript-promise)
My solution:
```javaScript
const  makeServerRequest = new Promise((resolve, reject) => {

});

```

 <br>
 <br>
  
## Problem Solving: 💪🚀
1. [Leap Years](https://www.codewars.com/kata/526c7363236867513f0005ca/train/javascript)
My solution:
```javaScript
function isLeapYear(year) {
  return  year % 400 === 0 || (year % 100 !== 0 && year % 4 === 0)  ;
}
```

2. [Detect Pangram](https://www.codewars.com/kata/545cedaa9943f7fe7b000048/train/javascript)
My solution:
```javaScript
function isPangram(string) {
  const lowercaseString = string.toLowerCase();
  const uniqueLetters = new Set(lowercaseString.match(/[a-z]/g));
  return uniqueLetters.size === 26;
}

```


 
