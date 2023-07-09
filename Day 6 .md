# 💎 Day 6 💎
 <br>
 <br>

 []()

  <br>
   
## JavaScript Principles  🎯🚀 
When JavaScript code runs, it:

1. Goes through the code line-by-line and runs/ ’executes’ each line - known as the **thread of execution**
2. Saves ‘data’ like strings and arrays so we can use that data later - in its memory. We can even save code (‘functions’)

<br>

### Call stack: 🔮🫧

It is a traditional way of storing information in a computer

JavaScript keeps track of what function is currently running (where’s the thread of execution)

* Run a function - add to call stack
* Finish running the function - JS removes it from call stack
* Whatever is top of the call stack - that’s the function we’re   currently running

<br>

## Functions & Callbacks ✨⚡️

We could generalize our function - So we pass in our specific instruction only when we run copyArrayAndManipulate !

```javaScript
function copyArrayAndManipulate(array, instructions) {
 const output = [];
 for (let i = 0; i < array.length; i++) {
		 output.push(instructions(array[i]));
	}
 return output;
}
function multiplyBy2(input) { return input * 2; }
const result = copyArrayAndManipulate([1, 2,

/* If I want to add 2 or divide or subtract 3 ot any fanctionality I just write
the small faunction for it */
```
<br>

### First class objects⏳🤔
Functions in javascript = first class objects 

They can co-exist with and can be treated like any other javascript object

1. Assigned to variables and properties of other objects
2. Passed as arguments into functions
3. Returned as values from functions

   <br>
   
### Higher Order Function ✨☄️ 

The outer function that takes in a function or return one is our higher-order function

<br>

###  Callback Function💻🔥
The function we insert is our callback function

<br>

### Anonymous and arrow functions 👩🏻‍💻🤔

Improve immediate legibility of the code

- But at least for our purposes here they are ‘syntactic sugar’
- we’ll see their full effects later - Understanding how they’re working under-the-hood is vital to avoid confusion

   <br>
   <br>
   
## Closure 🔥💫
A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, a closure gives you access to an outer function's scope from an inner function. In JavaScript, closures are created every time a function is created, at function creation time.

> ### 💡Notes:
> * When our functions get called, we create a live store of data (local
memory/variable environment/state) for that function’s execution context.
> * When the function finishes executing, its local memory is deleted (except the
returned value)
> * But what if our functions could hold on to live data between executions?
> * This would let our function definitions have an associated cache/persistent
memory
> * But it all starts with us returning a function from another function

<br>


```javaScript
function createFunction() {
	 function multiplyBy2 (num){
		  return num*2;
	 }
	 return multiplyBy2;
}
const generatedFunc = createFunction();
const result = generatedFunc(3); // 6

```

<br>

### The ‘backpack’ or ‘Closure’: ✏️📝

The data that my inner function used from the outer function

```javaScript
//  all the variables in the outer fun that the inner fun used iy, my res can
//  also access it, because it is attached to my fun

let outer = ()=>{
    const x = 5;
    const  inner = ()=>{
        return x
    }
    return inner()
}

const res = outer()
console.log(res)
```

<br>

> #### 💡 Note :
> The inner fun data will be brought wherever the function goes


### What can we call this ‘backpack’? 🧐🪩
* Closed Over `Variable Environment` (C.O.V.E.)
* Persistent Lexical Scope Referenced Data (P.L.S.R.D.)
* `Backpack`
* `Closure`


<br>

> #### 💡 Note :
> * Closure gives our functions persistent memories and entirely new toolkit for writing professional code
> * **reduceRight:** Make cummulative operations in reverse order

   <br>

### Practical Applications:  🎆🌟 

1. **Helper functions:** Everyday professional helper functions like ‘once’ and ‘memoize’
2. **Iterators and generators:** Which use lexical scoping and closure to achieve the
most contemporary patterns for handling data in JavaScript
3. **Module pattern:** Preserve state for the life of an application without polluting the
global namespace
4. **Asynchronous JavaScript:** Callbacks and Promises rely on closure to persist state
in an asynchronous environment

<br>
<br>

## Coding Exercises for challenges: 🔥💪
1. [Question 1:](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day2-tasks/tasks.md)
My solution:
```javaScript
const createCounter = (start)=>{
    let counter =0;
    const increment = ()=> ++counter
    return increment
}
```

2. [Question 2](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day2-tasks/tasks.md)
My solution:
```javaScript
const  calculateAverage = (nums)=>{
    const average = ()=> nums.reduce((sum,num)=>sum+num,0)/nums.length
    return average
}
```

3. [Question 3](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day2-tasks/tasks.md)
My solution:
```javaScript
const powerOf = (baseNum)=>{
    const result = (exp)=> baseNum**Num
    return result
}
```

4. [Question 4](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day2-tasks/tasks.md)
My solution:
```javaScript
const compose = (...functions)=>{
    const reverse =()=> functions.reduceRight((result, fun)=>fun(result))
    return reverse
} 
```


 <br>
 <br>
  
## Problem Solving: 💪🚀
[Square Every Digit](https://www.codewars.com/kata/546e2562b03326a88e000020/train/javascript)
```
function squareDigits(num){
    if (num ===0) return 0
    let n = Math.ceil(Math.log10(num))
    let ans =""
    while(n--){
        ans += (Math.floor(num/(10**n))**2)
        num = Math.floor(num%10**n)
    }
    return parseInt(ans)
  }  
```

2. [Number of People in the Bus](https://www.codewars.com/kata/5648b12ce68d9daa6b000099/train/javascript)
My solution:
```javaScript
var number = (busStops)=> busStops.reduce((sum,bus)=>sum+bus[0]-bus[1],0)
```


