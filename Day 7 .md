# 💎 Day 7 💎
 <br>
 <br>
   
## Asynchronous JavaScript 🎯🚀 
JavaScript is:

- Single threaded (one command runs at a time)
- Synchronously executed (each line is run in order the code appears)

<br>


```javaScript
function printHello() { console.log("Hello"); }
function blockFor1Sec() {
    setTimeout(()=>{console.log("1 sec");},1000)
    //blocks in the JavaScript thread for 1 sec
}


setTimeout(printHello, 0);
blockFor1Sec()
console.log("Me first!");

/* 
	Me first!
	Hello
	1 sec
*/
```

<br>

> ### 💡Note:
> setTimeOut doesn't do anything in JS it consequences in the web browser

#### JavaScript is not enough We need new pieces (some of which aren’t JavaScript at all) 💫💭

<br>

### Our core JavaScript engine has 3 main parts: 🔮🫧

- Thread of execution
- Memory/variable environment
- Call stack

<br>

### We need to add some new components: ✨ ⚡️

- Browser APIs/Node background APIs
- Promises
- Event loop, Callback/Task queue and micro task queue

```javaScript
setTimeout(()=>console.log("Hello"), 0);

for (let i=0; i<100; i++)
    console.log("Me first!");

//for loop makes block for the execution, when finish the loop will print Hello
```

<br>


```javaScript
function setTime() {
    setTimeout(()=>{console.log("Hello")},4000)}

for (let i=0; i<5; i++)
    setTime()

console.log("Finally");

// will print Finally then Hello ورا بعض على طول
```

   <br>
   <br>

   
## Promises ✨☄️ 
```javaScript
const futureData = fetch('https://twitter.com/will/tweets/1')

// futereData is Promise {<fulfilled>: Response} has automatic values
// 1. value 
// 2. fulfilled : array
// Any function I want to apply after fetching the data should be in the
// fulfilled array, bhut I don't have access to it, so .then do that
// on other words a functins thst automaticlly run when the data comes
```

<br>

### then method and functionality to call on completion 💻🔥


```javaScript
- Any code we want to run on the returned data must also be saved on the promise
object
- Added using .then method to the hidden property ‘onFulfilment’
- Promise objects will automatically trigger the attached function to run (with its
input being the returned data
```

<br>

###  Order of execution: 👩🏻‍💻🤔
We have three things to organize the execution:

1. **call stck**
2. **callback queue**
3. **micro queue**
 
<br>

> ### 👉 See this
>
> any function thrown out of JS or at lest link back to it is thrown out of JS via the old school callback facade function like setTimeOut those functions when the background work is complete, second in the callback queue. 
>
>any function that attached to a promise object via the then method and the outo trigged to run from withen JS  when the value proprety that promise .object gets update outomaticlly, as a result of background work from a two pronged facade function like fetch go to micro queue 

<br>

> ### ⏳🤔 Note
>When all the global code finished running and thers is nothing in the call stack 
>the queues is going to be checked (micro queue is the first)

<br>


```javaScript
function display(data){console.log(data)}
function printHello(){console.log("Hello");}
function blockFor300ms(){/* blocks js thread for 300ms */ }


const futureData = fetch('https://twitter.com/will/tweets/1')
futureData.then(display)
setTimeout(printHello, 0); 
// when the time finish the callback will be sent to callback queue
blockFor300ms()
console.log("Me first!");

// micro queu: display
// callback queue: printHello

/*
	Me first!
  Hello
  Response {type: 'cors', url: 'https://dummyjson.com/quotes', ...}
*/
```

   <br>

```javaScript
const final = ()=>{console.log("Filnaly")}

setTimeout(()=>{console.log("Set Time Out 1")},0)
console.log("1")

setTimeout(()=>{console.log("Set Time Out 2")},0)
console.log("2")

for(let i =0; i<2; i++)
console.log("after second set Time")

final()

/*
	1
	2
	after second set Time
	after second set Time
	Filnaly
	Set Time Out 1
	Set Time Out 2
*/
```

   <br>

> ### ✏️📝 Note:                         
> Any function i declear it as async, when I want to call it I should use .then() .catch() or use async/await

   <br>
   
## Classes & Prototypes 🔥💫 
Prototype chain: the feature behind-the-scenes that enables emulation of
OOP but is a compelling tool in itself

<br>


### _proto_ VS. prototype:🧐📝 
Proto and prototype both are objects that help in whether creating an array, object, or function and provide access to those specific methods or objects directly without taking memory and even it will give access to its constructor and all the array methods like push, pop, etc.

**_*proto_*:** It is an actual object that provides a way to inherit properties from JavaScript with the help of an object which is created with new. Every object with behavior associated has internal property [[prototype]].

<br>


```javaScript
function Student(name,age) {
this.name = name;
this.age = age;
}
var stu1 = new Student("John", 50);

// Object have proto property
stu1

// Also if apply strict equal to check
// if both point at the same
// location then it will return true.
Student.prototype === stu1._proto_
```

<br>

**Prototype**: It is a special object which means it holds shared attributes and behaviors of instances. It is a way to inherit properties from javascript as it is available in every function declaration.

```javaScript
// Constructor function
function Student(name, age) {
	this.name = name;
	this.age = age;
}

// Objects
var stu1 = new Student("gfg1", 25);
var stu2 = new Student("gfg2", 42);

// Prototype
Student.prototype.getName = function() { return this.name; }


// Function have property prototype
// Student

// Function call using object
stu1.getName();

// Constructor function
function Student(name, age) {
	this.name = name;
	this.age = age;
}

// Objects
var stu1 = new Student("gfg1", 25);
var stu2 = new Student("gfg2", 42);

// Prototype
Student.prototype.getName = function() { return this.name; }


// Function have property prototype
// Student

// function call using object
stu1.getName();

// Access prototype
Student.prototype
```
<br>


> ### 👉[More Diffrences](https://www.geeksforgeeks.org/difference-between-proto-and-prototype/)

<br>
   <br>

### Solutions for repeating the code: 🎆🌟  

1. **Generate objects using a function**

**Problem**:  each time we create a new user we make space in our computer's
memory for all our data and functions. But our functions are just copies

1. **Using the prototype chain**
2. Introducing the keyword that automates the hard work: **new** (95% of developers have no idea how it works and therefore fail interviews)
3. **The class**

<br>
> 💡 **Notes**:
>
> - All objects have a **proto** property by default which defaults to linking to a big
> object - Object.prototype full of (somewhat) useful functions
> - Arrow functions override the normal this rules


### Class notes: 💡💎
* instanceof: allows you to compare an object to a constructor, whether or not that object was created with the constructor.

```javaScript
let Bird = function(name, color) {
    this.name = name;
    this.color = color;
    this.numLegs = 2;
  }
  
  let crow = new Bird("Alexis", "black");
  console.log(crow instanceof Bird) // true
// if crow has the same attribute of Bird but wasn't creates using Bird(false) 
```

* Object.prototype.isPrototypeOf():
 method checks if an object exists in another object's prototype chain.
 ```javaScript
function Animal() { }

Animal.prototype = {
  constructor: Animal,
  eat: function() {
    console.log("nom nom nom");
  }
};

function Dog() { }
Dog.prototype = Object.create(Animal.prototype);
let beagle = new Dog();
// instances of Dog inherit from Animal
```

* objectName.hasOwnProperty()
will return just the proprty in the declartion (false if defined in the prototype)
 ```javaScript
function Bird(name) {
    this.name = name;  //own property
  }
Bird.prototype.numLegs = 2; // prototype property
let duck = new Bird("Donald");
let ownProps = [];
let prototypeProps = [];

for (let property in duck) {
  if(duck.hasOwnProperty(property)) {
    ownProps.push(property);
  } else {
    prototypeProps.push(property);
  }
}

console.log(ownProps);
console.log(prototypeProps);
```

* iterete the obj attribute & method

 ```javaScript
// us in while we us of in array
for (let i in obj){
// will return them as string
}
```

* Two kinds of properties
1. **Own properties:** are defined directly on the object instance itself. 
2. **prototype** **properties:** are defined on the `prototype`.

 ```javaScript
function Bird(name) {
  this.name = name;  //own property
}
Bird.prototype.numLegs = 2; // prototype property
```

* objectName.constructor

```javaScript
console.log(duck.constructor === Bird);
```

* Adding multible attributes or methods

```javaScript
Bird.prototype = {
constructor: Bird,
  numLegs: 2,
  eat: function() {
    console.log("nom nom nom");
  },
  describe: function() {
    console.log("My name is " + this.name);
  }
};
```

* isPrototypeOf
method checks if an object exists in another object's prototype chain.

```javaScript
Bird.prototype.isPrototypeOf(duck);
```

*Object.getPrototypeOf(objectName)
To bring the all prototype

*  Ways to creat obj

```javaScript
function Animal(name) { 
this.name = name;}

let animal = new Animal();
let animal2 = Object.create(Animal.prototype); // not invok the constructer fun
// ex. animal2.name >> undefined
```

*  inherits its prototype

```javaScript
function Animal() {}

Animal.prototype = {
  constructor: Animal,
  eat: function() {
    console.log("nom nom nom");
  }
};

function Dog() {}

Dog.prototype = Object.create(Animal.prototype);
// you ensure that instances of Dog can inherit and access the properties 
// and methods defined on Animal.prototype.
```

* Inhert the construvter property

```javaScript
Bird.prototype.constructor = Bird;
```

* override method in prototype

```javaScript
Dog.prototype.eat = function (){
    console.log("Woof!")
}
```

* mixin:
For unrelated objects, it's better to use mixins. A mixin allows other objects to use a collection of functions.

```javaScript
let flyMixin = function(obj) {
  obj.fly = function() {
    console.log("Flying, wooosh!");
  }
};

let bird = {
  name: "Donald",
  numLegs: 2
};
flyMixin(plane);
```

* Immediately Invoked Function Expression (IIFE)
execute a function as soon as it is declared:

```javaScript
// befor 
function makeNest() {
  console.log("A cozy nest is ready");
}
makeNest();

//after
(function () {   //The function should be anonymous.
  console.log("A cozy nest is ready");
})() 
```

   <br>
   <br>

## GSG tasks   🍄🍃
[Tasks link](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day3-tasks/tasks.md)

Question 1
   
My solution:
```javaScript
const task1 = () => new Promise((resolve) => {
    setTimeout(() => {
      const message = "Task 1 has executed successfully!";
      resolve(message);
    }, 3000);
  });

  const task2 = () => new Promise((resolve) => {
    setTimeout(() => {
      const message = "Task 2 has executed successfully!";
      resolve(message);
    }, 0);
  });

  const task3 = () => new Promise((resolve) => {
    setTimeout(() => {
      const message = "Task 3 has executed successfully!";
      resolve(message);
    }, 1000);
  });

  const task4 = () => new Promise((resolve) => {
    setTimeout(() => {
      const message = "Task 4 has executed successfully!";
      resolve(message);
    }, 2000);
  });

  const task5 = () => new Promise((resolve) => {
    setTimeout(() => {
      const message = "Task 5 has executed successfully!";
      resolve(message);
    }, 4000);
  });

  const asyncTasks = [task1, task2, task3, task4, task5];

  const executeInSequenceWithCBs = async (tasks, callback) => {
    const promises = tasks.map((task) => task());
    const results = await Promise.all(promises);
    callback(results);
    return results;
  };

  executeInSequenceWithCBs(asyncTasks, (messages) => {
    console.log(messages);
  });
```

Question 2:
   
My solution:
```javaScript
const apis = [
    {
        apiName: "products",
        apiUrl: "https://dummyjson.com/products",
    },
    {
        apiName: "users",
        apiUrl: "https://dummyjson.com/users",
    },
    {
        apiName: "posts",
        apiUrl: "https://dummyjson.com/posts",
    },
    {
        apiName: "comments",
        apiUrl: "https://dummyjson.com/comments",
    }
]


const executeInParallelWithPromises = (apis) => {
    const promises = apis.map(api => {
        return fetch(api.apiUrl)
            .then(response => { response.json() })
            .then(data => {
                return {
                    apiName: api.apiName,
                    apiUrl: api.apiUrl,
                    apiData: data
                }
            })
    })

    return Promise.all(promises)
}

executeInParallelWithPromises(apis)
    .then(data=>console.log(data))
    .catch(error => console.log(error))



```

Question 3:
   
My solution:
```javaScript

const apis = [
    {
        apiName: "products",
        apiUrl: "https://dummyjson.com/products",
    },
    {
        apiName: "users",
        apiUrl: "https://dummyjson.com/users",
    },
    {
        apiName: "posts",
        apiUrl: "https://dummyjson.com/posts",
    },
    {
        apiName: "comments",
        apiUrl: "https://dummyjson.com/comments",
    }
]

const executeInSequenceWithPromises = async (apis) => {
    const results = []
    for (let api of apis){
        const respose = await fetch(api.apiUrl)
        const data = await respose.json()
        results.push({
            apiName: api.apiName,
            apiUrl: api.apiUrl,
            apiData: data
        })
    }
    return results
}

executeInSequenceWithPromises(apis)
    .then(results=>{console.log(results)})
    .catch(error =>console.log(error))

```
   
## GSG optional task 🌟🌠

 [ALL 26 exercises of the Object Oriented Programming section](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#object-oriented-programming)

[My solutions](https://www.freecodecamp.org/SarahAbuirmeileh)


 
