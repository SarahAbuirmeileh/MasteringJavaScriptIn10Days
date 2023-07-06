# 💎 Day 3 💎
 <br>
 <br>
   
## Quiz 💻 📑

[Qiuz Link](https://anjana.dev/javascript-first-steps/2-jsquiz-fancy.html)

**My mark:**

 <br>
 
![img](https://github.com/SarahAbuirmeileh/test/assets/127017088/5df1f43a-48e8-40fa-ac1f-41644e534949)


   <br>
   <br>
   
## Project ✨☄️
```HTML
<!DOCTYPE html>
<!-- saved from url=(0038)file:///home/sarah/Downloads/Quiz.html -->
<html lang="en-US"><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    
    <title>Quiz.js</title>
    <style>
        body {
            margin: 1rem auto;
            padding: 3rem;
            font-family: sans-serif;
        }
        header {
            width: 50%;
            margin: 1em auto;
        }
        main {
            min-width: 25rem;
            max-width: 50%;
            margin: 0px auto;
            display:flex; 
            flex-direction: column;
        }
        #statement {
            border: 1px solid black;
            border-radius: 0.5rem;
            box-shadow: 5px 5px 5px gray;
            padding: 1rem;
            font-size: x-large;
            text-align: center;
            margin: 1rem 0px;
            min-height: 2em;
        }
        #explanation {
            padding: 1rem;
            text-align: center;
        }
        #options {
            width: 100%;
            display: flex;
            flex-direction: column;
        }
        button {
            padding: 0.5rem;
            font-size: medium;
            border-radius: 5px;
        }
        .correct {
            background-color: lightgreen;
        }
        .incorrect {
            background-color: lightpink;
        }
    </style>
  </head>
  <body>
    <header>
    <h1>Quiz.js</h1>
    <p>Do you know JS? Find out!</p>
    </header>

    <main>
    <div id="statement">
        
    </div>

    <div id="options">
        <button name="true" value="true">true</button>
        <button name="false" value="false">false</button>
    </div>

    <div id="explanation">

    </div>

    </main>

  

  <script type="text/javascript">


    // TODO 1: Declare & assign variables pointing to the corresponding element(s)
    // statement should be the "statement" div
    // optionButtons should be all the elements within the "options" div
    // explanation should be the "explanation" div

    const statement = document.getElementById("statement")
    const optionButtons = document.querySelector("#options").children
    const explanation = document.getElementById("explanation")


    // TODO 2: Declare & assign a variable called fact
    // Its value should be an object with a statement, true/false answer, and explanation 
    
    let fact = {
        statement : "Sarah is the queen of programming",
        answer : true,
        explanation :  " Sarah possesses exceptional skills and expertise in the field of programming, she is a highly skilled programmer who can tackle complex problems and create innovative solutions."
    }

    
    // TODO 3: Set the text of the statement element to the fact's statement

    statement.textContent= fact.statement

    // TODO 4: Declare disable & enable functions to set or remove the "disabled" attribute from a given button element
    // disable(button) should set the button element's attribute "disabled" to the value ""
    // enable(button) should remove the attribute "disabled" from the button element

    const disable = button =>{
        button.setAttribute("disabled","")
    }

    const enable = button =>{
         button.removeAttribute("disabled")
    }


    // TODO 5: Declare an isCorrect function that compares a guess to the right answer
    // isCorrect(guess) should return true if the guess matches the fact's answer
    
    const isCorrect = guess =>{ return guess === fact.answer.toString()}


    // TODO 6A: Use a for loop to add a click event listener to each of the optionButtons
    for (let b of optionButtons){
        b.addEventListener("click", event =>{
            
        
    
            // TODO 6B: Within the event handler function, display the fact's explanation by setting the text of the explanation element
            
            explanation.textContent = fact.explanation

            // TODO 7: Within the event handler function, 
            // Use a for loop to disable all the option buttons

            for (let allB of optionButtons)
                disable(allB)
        

            // TODO 8: Within the event handler function,
            // Get the guessed value from the clicked button
            // Use a conditional to compare the guess to the fact's answer
            // and add the "correct"/"incorrect" class as appropriate

            if (isCorrect(b.value)){
                b.classList.add("correct")
            }else{
                b.classList.add("incorrect")
            }

        })
    }
    

  </script>

</body></html>
```

   <br>
   <br>
   
##  Functions🔥💫
   <br>

>  ### 👉 Remmber:
> **values** are things
> 
> **variables** point to things
> 
> **functions** do things

   <br>

### Exercises:  🔑🌠
```javaScript
// 1. multiply: given 2 numbers, return their product
const mult = (a,b)=>a*b

// 2. yell: given a lowercase string, log it in all caps to the console
const yell = (str)=> str.toUpperCase()

// 3. longerThan: given 2 arrays, return whether the first is longer than
//    the second
const longerThan = (a,b)=> a.length >= b.length
```

   <br>
   
###  setAttribute() & removeAttribute() methods 📋✏️
`setAttribute` : Sets the value of an attribute on the specified element. If the attribute already exists, the value is updated; otherwise a new attribute is added with the specified name and value.
```javaScript
setAttribute(name, value)
```

 <br>
 
` removeAttribute`: removes the attribute with the specified name from the element.
```javaScript
removeAttribute(attrName)
```
 
   <br>
   
### Exercises: ⚙️🔥    
```javaScript
/* 1. declare functions to disable or enable a button */

		const disable = button =>{
		        button.d.setAttribute("disabled","")
		    }

		const enable = button =>{
		         button.removeAttribute("disabled")
		    }

/* 2. declare isCorrect(guess) function that compares a guess string to your 
     fact's answer string */

const isCorrect = guess =>{ guess === fact.answer}
```
   <br>

 ### Scope:📜🎆
Scope determines where variables are "in play"Copy

 <br>

>  👉 Within each scope, you can access variables declared in a wider scope (e.g. global scope) But not those declared in a narrower scope (e.g. function scope) 👈

 <br>

```javaScript
// Use destructuring assignment to swap the values of a and b
[a,b]=[b,a]
```

<br>
 <br>

## 💡 **Notes:**
1. The **`Function`** object provides methods
2. `this` keyword works differently in arrow fun. and normal fun.
3. To set or remove any attribute for element we use `setAttribue` & `removeAttribute`
4. The browser looks weather the disabled attribute exist or not, regardless to it's value

 <br>
 <br>

## Coding Exercises for challenges: 🔥💪
1. [Use Destructuring Assignment to Assign Variables from Arrays](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/use-destructuring-assignment-to-assign-variables-from-arrays)
My solution:
```javaScript
let a = 8, b = 6;
// Only change code below this line
[a,b]=[b,a]
```

2. [Destructuring via rest elements](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/use-destructuring-assignment-with-the-rest-parameter-to-reassign-array-elements)
My solution:
```javaScript
function removeFirstTwo(list) {
  // Only change code below this line
  const [a, b, ...shorterList] = list; // Change this line
  // Only change code above this line
  return shorterList;
}

const source = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
const sourceWithoutFirstTwo = removeFirstTwo(source);
```

3. [Use Destructuring Assignment to Pass an Object as a Function's Parameters](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/use-destructuring-assignment-to-pass-an-object-as-a-functions-parameters)
My solution:
```javaScript
const stats = {
  max: 56.78,
  standard_deviation: 4.34,
  median: 34.54,
  mode: 23.87,
  min: -0.75,
  average: 35.85
};

// Only change code below this line
const half = ({max, min}) => {return  (max + min) / 2.0; }
// Only change code above this line
```

4. [Create Strings using Template Literals](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/create-strings-using-template-literals)
My solution:
```javaScript
const result = {
  success: ["max-length", "no-amd", "prefer-arrow-functions"],
  failure: ["no-var", "var-on-top", "linebreak"],
  skipped: ["no-extra-semi", "no-dup-keys"]
};
function makeList(arr) {
  "use strict";
  // change code below this line
  const failureItems = [];
  for (let i = 0; i < arr.length; i++) {
    failureItems.push(`<li class="text-warning">${arr[i]}</li>`);
  }
  // change code above this line
  return failureItems;
}

const failuresList = makeList(result.failure);
```

5. [Write Concise Object Literal Declarations Using Object Property Shorthand](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/write-concise-object-literal-declarations-using-object-property-shorthand)
My solution:
```javaScript
const createPerson = (name, age, gender) => {
  // Only change code below this line
  return {
    name,
    age,
    gender
  };
  // Only change code above this line
};
```

 <br>
 <br>
  
## Problem Solving: 💪🚀
1. [Reverse List Order](https://www.codewars.com/kata/53da6d8d112bd1a0dc00008b/train/javascript)
My solution:
```javaScript
function reverseList(list) {
  return list.reverse()
}
```

2. [Sum of two lowest positive integers](https://www.codewars.com/kata/558fc85d8fd1938afb000014/train/javascript)
My solution:
```javaScript
function sumTwoSmallestNumbers(numbers) {  
    numbers.sort((a,b)=>{ return a>b ? 1 : b>a ?-1 : 0 })
    return numbers[0]+ numbers[1]
  }
```


 
