# 💎 Day 9 💎
 <br>
 <br>
   
## Static Typing 🎯🚀 

<br>

###  Benefits: 💫💭 

1. Catch type-related mistakes
2. Communicate type intent
3. Provide IDE feedback
4. validating operand types to avoid errors


<br>

### **[TypeScript vs Flow](https://github.com/niieani/typescript-vs-flowtype)** 🔮🫧

<br>
<br>

##  Scope ✨☄️

JavaScript organizes scopes with functions and blocks

<br>

> ### 👉 Note:
>  Having two varibles with same name in different scopes called shadowing

<br>

### **Befor executing the code :** 💻🔥

1. scope maneger detrmine the scope
2. then bring data or store it in the variable
###  

<br>



###  Auto Globale: 👩🏻‍💻🌍

If I try to use varible in cuurent scope without declaring it, it will be delared in the globale scope

```javaScript
function h (){
    x = "sarah"
    console.log(x)
}
h() // sarah
```

   <br>
   

### Disable it 🔥💫

```javaScript
"use strict" 
function h (){
    x = "sarah"
    console.log(x)
}
h() // erorr
```

<br>
<br>

## Scope & Function Expressions 🎨🌊

### Function expression 🔮🫧

```javaScript
let fun1 = function fun2(){
    console.log("Sarah")
}

fun1() //Sarah
fun2() //ReferenceError
```

### Named Function Expressions: Benefits 💫💭

1. Reliable function self-reference (recursion, etc)
2. More debuggable stack traces
3. More self-documenting code

### Exercises🍄🍃

```javaScript
/*
You are provided three functions stubs -- `printRecords(..)`, `paidStudentsToEnroll()`, and `remindUnpaid(..)` -- which you must define.

At the bottom of the file you will see these functions called, and a code comment indicating what the console output should be.

1. `printRecords(..)` should:
	- take a list of student Ids
	- retrieve each student record by its student Id (hint: array `find(..)`)
	- sort by student name, ascending (hint: array `sort(..)`)
	- print each record to the console, including `name`, `id`, and `"Paid"` or `"Not Paid"` based on their paid status

2. `paidStudentsToEnroll()` should:
	- look through all the student records, checking to see which ones are paid but **not yet enrolled**
	- collect these student Ids
	- return a new array including the previously enrolled student Ids as well as the to-be-enrolled student Ids (hint: spread `...`)

3. `remindUnpaid(..)` should:
	- take a list of student Ids
	- filter this list of student Ids to only those whose records are in unpaid status
	- pass the filtered list to `printRecords(..)` to print the unpaid reminders
*/

function printRecords(studentId) {
    return studentRecords.find(function getById(student) {
        return student.id === studentId
    })
}


function paidStudentsToEnroll() {
    const studentsToEnroll = studentRecords.filter(function needToEnroll(student) {
        return (student.paid && !student.currentEnrollment.includes(record.id))
        // checks if the id of the current record is not already present in the currentEnrollment array
    })

    return [...currentEnrollment, ...studentsToEnroll.map(function getIId(student) {
        return student.id
    })]
}

function remindUnpaid(recordIds) {
	const unpaidIds = recordIds.filter(function notPaidYet(studentId){
		const record = getStudentFromId(studentId);
		return !record.paid;
	});

	printRecords(unpaidIds);
}
```

<br>
<br>

#  Coding Exercises for challenges: 🔥💪
1. [Use typeof to Check the Type of a Variable](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/debugging/use-typeof-to-check-the-type-of-a-variable)
   
My solution:
```javaScript
let seven = 7;
let three = "3";
console.log(seven + three);
// Only change code below this line

console.log(typeof seven)
console.log(typeof three)
```

2. [Catch Misspelled Variable and Function Names](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/debugging/catch-misspelled-variable-and-function-names)

My solution:
```javaScript
let receivables = 10;
let payables = 8;
let netWorkingCapital = receivables - payables;
console.log(`Net working capital is: ${netWorkingCapital}`);
```

3. [Catch Unclosed Parentheses, Brackets, Braces and Quotes](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/debugging/catch-unclosed-parentheses-brackets-braces-and-quotes)
My solution:
```javaScript
let myArray = [1, 2, 3];
let arraySum = myArray.reduce((previous, current) =>  previous + current);
console.log(`Sum of array values is: ${arraySum}`);
```

4. [Catch Mixed Usage of Single and Double Quotes](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/debugging/catch-mixed-usage-of-single-and-double-quotes)

My solution:
```javaScript
let innerHtml = "<p>Click here to <a href=\"#Home\">return home</a></p>";
console.log(innerHtml);
```

5. [Catch Use of Assignment Operator Instead of Equality Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/debugging/catch-use-of-assignment-operator-instead-of-equality-operator)

My solution:
```javaScript
let x = 7;
let y = 9;
let result = "to come";

if(x === y) {
  result = "Equal!";
} else {
  result = "Not equal!";
}

console.log(result);
```

6. [Catch Missing Open and Closing Parenthesis After a Function Call](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/debugging/catch-missing-open-and-closing-parenthesis-after-a-function-call)

My solution:
```javaScript
function getNine() {
  let x = 6;
  let y = 3;
  return x + y;
}

let result = getNine();
console.log(result);
```

7. [Catch Arguments Passed in the Wrong Order When Calling a Function](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/debugging/catch-arguments-passed-in-the-wrong-order-when-calling-a-function)

My solution:
```javaScript
function raiseToPower(b, e) {
  return Math.pow(b, e);
}

let base = 2;
let exp = 3;
let power = raiseToPower(base, exp);
console.log(power);
```

8.  [Catch Off By One Errors When Using Indexing](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/debugging/catch-off-by-one-errors-when-using-indexing)

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

 <br>
 <br>
  
## Problem Solving: 💪🚀
1. [Simple Pig Latin](https://www.codewars.com/kata/520b9d2ad5c005041100000f/train/javascript)

My solution:
```javaScript
function pigIt(str){
    let splited = str.split(' ')
    return splited.map(i => {return !/^[A-Za-z]+$/.test(i) ? i : i.slice(1)+i[0]+"ay"}).join(' ')
  }

```

2. [Valid Braces](https://www.codewars.com/kata/5277c8a221e209d3f6000b56/train/javascript)
My solution:
```javaScript
function validBraces(braces) {
    const pair = { '(': ")", '[': ']', '{': "}" }
    let stack = []

    for (let i of braces){
        if (i === '(' || i==='{' || i==='[')
            stack.push(i)
        else{
            if (pair[stack[stack.length-1]]===i)
                stack.pop()
            else 
            stack.push(i)
        }
    }
    return stack.length ===0
}
```


