# 💎 Day 4 💎
 <br>
 <br>
   
## Events & Handlers 🎯🚀 
How to make our web page interactive !
### addEventListener() 💫
method lets us listen for events on a DOM element 

<br>

> #### 👉 Note:
>  **addEventListener()** takes 2 parameters:
>  1. The name of the event to listen to (e.g. "click")
>  2. A handler function that JS calls when that event is fired on this element

<br>

```javaScript
document.addEventListener("click", () => {
    console.log("clicked")
});
```

<br>

#### Optional parameter: 🔮🫧
JS passes an event object to the handler function with information about the event. 

If we accept this as a parameter, we can use it to get details

```javaScript
document.addEventListener("click", (event) => {
    console.log(event);
});
```

<br>

### event.target: ✨⚡️
Is the element the event fired on (in this case, which element was clicked)
```javaScript
document.addEventListener("click", (event) => {
    console.log(event.target);
});
```
<br>

### Some events: 💻🔥
1. **["click"](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event)**
2. **["dblclick"](https://developer.mozilla.org/en-US/docs/Web/API/Element/dblclick_event)** 
3. [**"mouseover"**](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseover_event)
4. [**"mouseout"**](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseout_event)


```javaScript
let b = document.getElementsByName("true")[0]
b.addEventListener("mouseover", () => {
    console.log("The carser is in the button")
});

b.addEventListener("mouseout", () => {
    console.log("The carser is out the button")
});
```
<br>

###  Exercise:⏳🔥
The code in Project section or this [link](https://anjana.dev/javascript-first-steps/2-jsquiz-starter.html)

```javaScript
/*
	In the console, on our quiz add event listeners to the buttons so that:
	
	When the "true" button is clicked, the button's text becomes "clicked true"
	When the "false" button is clicked, the "explanation" div text becomes 
	"clicked false"
*/

let bt = document.getElementsByName("true")[0]
bt.addEventListener("click",()=>{b.textContent="clicked true"})

let bf = document.getElementsByName("false")[0]
bf.addEventListener("click",()=>{
		document.getElementById("explanation").textContent = "clicked false"
})
```
   <br>
   <br>
   
### Example ✨☄️ 

```HTML
<!DOCTYPE html>
<html>
<head>
  <title>Very Exciting Web Page</title>
  <style>
    .box {
      border: 3px solid grey;
      padding: 1em;
    }

    .hidden {
      display: none;
    }

    #clickme {
      background-color: purple;
      color: white;
      margin-top: 1em;
      padding: 1em;
      border: 0px;
      border-radius: 5px;
    }
  </style>
</head>
<body>
  <h1>Very Exciting Web Page</h1>

  <div class="box">
    <p id="in">Hello I am in a box</p>
  </div>

  <p id="out" class="hidden">Now I have escaped</p>

  <button id="clickme">Click me</button>

  <script>
    const button = document.getElementById("clickme");
    const paragraphs = document.querySelectorAll("p");

    button.addEventListener("click", event => {
      for (let p of paragraphs) {
        p.classList.toggle("hidden");
      }
    });
  </script>
</body>
</html>
```

<br>
<br>

## Conditionals  👩🏻‍💻🤔
### If statment: ❓🌟 
If it's given some other value, JS will convert it to a boolean and decide based on its "truthiness”

```javaScript
if ("nonempty strings are truthy") {
    console.log("this line will run");
}
```

<br>

#### Exercise: 🍄🍃

```javaScript
/*
  1. Write a conditional that logs a message saying whether your first name 
  or last name is longer 
*/

	if ("Sarah".length >= "Abu irmeileh".length){
	    console.log("First name is longer");
	}else{
	    console.log("Last name is longer");
	}


/*
2. Write a function isEmpty(array) that returns whether a given array is empty
*/

const isEmpty = (array)=>{array.length === 0 }


// 3. Is an empty array truthy or falsy? Write a conditional to find out 

if ([]){
    console.log("empty array is a truth value");
}else{
    console.log("empty array is a false value");
} // truth value
```

   <br>
   
###  Loops:🔥💫
#### enhanced loop: 🎆🌟 

```javaScript
const numbers = [1,2,3];
for (let i = 0; i < numbers.length; i++) {
    console.log(numbers[i]);
}
for (let n of numbers) {
    console.log(n);
}
```
   
<br>
<br>

### Complete the project: ✏️📝 

```javaScript
for (let b of optionButtons){
        b.addEventListener("click", event =>{
                        
            explanation.textContent = fact.explanation

            for (let allB of optionButtons)
                disable(allB)
        

            if (isCorrect(b.value)){
                b.classList.add("correct")
            }else{
                b.classList.add("incorrect")
            }

        })
    }
```

<br>
<br>

## Doggo Fetch Project  🧐🪩
```javaScript
<!DOCTYPE html>
<!-- saved from url=(0067)https://anjana.dev/javascript-first-steps/3-doggofetch-starter.html -->
<html lang="en-US"><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    
    <title>Doggo Fetch</title>
    <style>
        body {
            margin: 1rem auto;
            padding: 3rem;
            font-family: sans-serif;
        }
        header {
            width: 70%;
            margin: 1em auto;
        }
        main {
            max-width: 70%;
            margin: 0px auto;
            display:flex; 
            flex-direction: column;
        }
        img {
            max-width: 100%;
        }
        #image-frame {
            font-size: x-large;
            text-align: center;
            margin: 1rem auto;
        }
        #explanation, #score {
            padding: 1rem;
            text-align: center;
        }
        #options {
            max-width: 100%;
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
        .hidden {
            display: none;
        }
    </style>
  </head>
  <body>
    <header>
    <h1>Guess the Doggo</h1>
    <p>What breed is the dog in this image?</p>

    </header>

    <main>
    <div id="image-frame">
    </div>
    <div id="options">
    </div>

    </main>

  


  <script type="module">

    const RANDOM_IMG_ENDPOINT = "https://dog.ceo/api/breeds/image/random";

    const BREEDS = ["affenpinscher", "african", "airedale", "akita", "appenzeller", "shepherd australian", "basenji", "beagle", "bluetick", "borzoi", "bouvier", "boxer", "brabancon", "briard", "norwegian buhund", "boston bulldog", "english bulldog", "french bulldog", "staffordshire bullterrier", "australian cattledog", "chihuahua", "chow", "clumber", "cockapoo", "border collie", "coonhound", "cardigan corgi", "cotondetulear", "dachshund", "dalmatian", "great dane", "scottish deerhound", "dhole", "dingo", "doberman", "norwegian elkhound", "entlebucher", "eskimo", "lapphund finnish", "bichon frise", "germanshepherd", "italian greyhound", "groenendael", "havanese", "afghan hound", "basset hound", "blood hound", "english hound", "ibizan hound", "plott hound", "walker hound", "husky", "keeshond", "kelpie", "komondor", "kuvasz", "labradoodle", "labrador", "leonberg", "lhasa", "malamute", "malinois", "maltese", "bull mastiff", "english mastiff", "tibetan mastiff", "mexicanhairless", "mix", "bernese mountain", "swiss mountain", "newfoundland", "otterhound", "caucasian ovcharka", "papillon", "pekinese", "pembroke", "miniature pinscher", "pitbull", "german pointer", "germanlonghair pointer", "pomeranian", "medium poodle", "miniature poodle", "standard poodle", "toy poodle", "pug", "puggle", "pyrenees", "redbone", "chesapeake retriever", "curly retriever", "flatcoated retriever", "golden retriever", "rhodesian ridgeback", "rottweiler", "saluki", "samoyed", "schipperke", "giant schnauzer", "miniature schnauzer", "english setter", "gordon setter", "irish setter", "sharpei", "english sheepdog", "shetland sheepdog", "shiba", "shihtzu", "blenheim spaniel", "brittany spaniel", "cocker spaniel", "irish spaniel", "japanese spaniel", "sussex spaniel", "welsh spaniel", "english springer", "stbernard", "american terrier", "australian terrier", "bedlington terrier", "border terrier", "cairn terrier", "dandie terrier", "fox terrier", "irish terrier", "kerryblue terrier", "lakeland terrier", "norfolk terrier", "norwich terrier", "patterdale terrier", "russell terrier", "scottish terrier", "sealyham terrier", "silky terrier", "tibetan terrier", "toy terrier", "welsh terrier", "westhighland terrier", "wheaten terrier", "yorkshire terrier", "tervuren", "vizsla", "spanish waterdog", "weimaraner", "whippet", "irish wolfhound"];

    
    // Utility function to get a randomly selected item from an array
    function getRandomElement(array) {
        const i = Math.floor(Math.random() * array.length);
        return array[i];
    }

    // Utility function to shuffle the order of items in an array in-place
    function shuffleArray(array) {
        return array.sort((a,b) => Math.random() - 0.5);
    }



    // TODO 1
    // Given an array of possible answers, a correct answer value, and a number of choices to get,
    // return a list of that many choices, including the correct answer and others from the array
    function getMultipleChoices(n, correctAnswer, array) {
        // Use a while loop and the getRandomElement() function
        const choices= [correctAnswer]
        while(choices.length<n){
            const candidate = getRandomElement(array)
            if(!choices.includes(candidate))
                choices.push(candidate)
        }
        // Make sure there are no duplicates in the array
        return  shuffleArray(choices)

    }

    
    // TODO 2
    // Given a URL such as "https://images.dog.ceo/breeds/poodle-standard/n02113799_2280.jpg"
    // return the breed name string as formatted in the breed list, e.g. "standard poodle"
    function getBreedFromURL(url) {
        // The string method .split(char) may come in handy
        // Try to use destructuring as much as you can
        
    }



    // TODO 3
    // Given a URL, fetch the resource at that URL, 
    // then parse the response as a JSON object,
    // finally return the "message" property of its body
    async function fetchMessage(url) {
        
    }


    // Function to add the multiple-choice buttons to the page
    function renderButtons(choicesArray, correctAnswer) {

        // Event handler function to compare the clicked button's value to correctAnswer
        // and add "correct"/"incorrect" classes to the buttons as appropriate
        function buttonHandler(e) {
            if (e.target.value === correctAnswer) {
                e.target.classList.add("correct");
            } else {
                e.target.classList.add("incorrect");
                document.querySelector(`button[value="${correctAnswer}"]`).classList.add("correct");
            }
        }

        const options = document.getElementById("options"); // Container for the multiple-choice buttons

        // TODO 4
        // For each of the choices in choicesArray,
        // Create a button element whose name, value, and textContent properties are the value of that choice,
        // attach a "click" event listener with the buttonHandler function,
        // and append the button as a child of the options element
        
    }


    // Function to add the quiz content to the page
    function renderQuiz(imgUrl, correctAnswer, choices) {
        const image = document.createElement("img");
        image.setAttribute("src", imgUrl);
        const frame = document.getElementById("image-frame");

        image.addEventListener("load", () => {
            // Wait until the image has finished loading before trying to add elements to the page
            frame.replaceChildren(image);
            renderButtons(choices, correctAnswer);
        })
        
    }

    // Function to load the data needed to display the quiz
    async function loadQuizData() {
        document.getElementById("image-frame").textContent = "Fetching doggo...";
        
        const doggoImgUrl = await fetchMessage(RANDOM_IMG_ENDPOINT);
        const correctBreed = getBreedFromURL(doggoImgUrl);
        const breedChoices = getMultipleChoices(3, correctBreed, BREEDS);

        return [doggoImgUrl, correctBreed, breedChoices];
    }

    // TODO 5
    // Asynchronously call the loadQuizData() function,     
    // Then call renderQuiz() with the returned imageUrl, correctAnswer, and choices 
    
    


  </script>

</body></html>
```

<br>
<br>

## (A)synchronous code: 💡💎
### **Some things that take time:** ✨🎀

1. Waiting for user events 
2. Asking a user to pick a file 
3. Getting permission to access the camera/mic 
4. Loading data from the interwebs

<br>

###  Learning about asynchronous JS: ✏️📋

[1. MDN: Introducing Asynchronous JS](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Introducing)

**[2. Philip Roberts: What the heck is the event loop anyway?](https://www.youtube.com/watch?v=8aGhZQkoFbQ)**


 <br>
 <br>

## 💡 **Notes:**
1. `querySelector`: this method returns the first element while `querySelectorAll`: this method returns a NodeList containing all elements that match the specified selector

 <br>
 <br>

## Coding Exercises for challenges: 🔥💪
1. [Write Concise Declarative Functions with ES6](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/write-concise-declarative-functions-with-es6)
My solution:
```javaScript
// Only change code below this line
const bicycle = {
  gear: 2,
  setGear(newGear) {
    this.gear = newGear;
  }
};
// Only change code above this line
bicycle.setGear(3);
console.log(bicycle.gear);
```

2. [Use class Syntax to Define a Constructor Function](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/use-class-syntax-to-define-a-constructor-function)
My solution:
```javaScript
// Only change code below this line
class Vegetable {
  constructor (name){
    this.name = name
  }
}
// Only change code above this line

const carrot = new Vegetable('carrot');
console.log(carrot.name); // Should display 'carrot'
```

3. [Use getters and setters to Control Access to an Object](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/use-getters-and-setters-to-control-access-to-an-object)
My solution:
```javaScript
// Only change code below this line
class Thermostat {
  constructor(fahrenheit) {
    this.fahrenheit = fahrenheit;
  }
  
  get temperature() {
    return (5 / 9) * (this.fahrenheit - 32);
  }
  
  set temperature(celsius) {
    return this.fahrenheit = (celsius * 9.0) / 5 + 32;
  }
}
// Only change code above this line

const thermos = new Thermostat(76); // Setting in Fahrenheit scale
let temp = thermos.temperature; // 24.44 in Celsius
thermos.temperature = 26;
temp = thermos.temperature; // 26 in Celsius
```

4. [Create a Module Script](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/create-a-module-script)
My solution:
```javaScript
<html>
  <body>
    <!-- Only change code below this line -->
    <script type="module" src="index.js"></script>
    <!-- Only change code above this line -->
  </body>
</html>
```

5. [Use export to Share a Code Block](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/use-export-to-share-a-code-block)
My solution:
```javaScript
const uppercaseString = (string) => {
  return string.toUpperCase();
}

const lowercaseString = (string) => {
  return string.toLowerCase()
}

export { uppercaseString, lowercaseString };
```

 <br>
 <br>
  
## Problem Solving: 💪🚀
1. [Find the next perfect square!](https://www.codewars.com/kata/56269eb78ad2e4ced1000013/train/javascript)
My solution:
```javaScript
function findNextSquare(sq) {
    const root = Math.sqrt(sq)
    return Math.sqrt(sq)===Math.ceil(Math.sqrt(sq)) ? (root+1)**2  : -1
  }
```

2. [Two to One](https://www.codewars.com/kata/5656b6906de340bd1b0000ac/train/javascript)
My 1st solution:
```javaScript
function longest(s1, s2) {
    let mySet = new Set()
    let ans = ""
    for(let s of s1+s2){
        if(!mySet.has(s)){
            mySet.add(s)
            ans+=s
        }
    }
    
    return ans.split('').sort().join('')
  }
```

My 2nd solution:
```javaScript
 const longest = (s1, s2) => [...new Set(s1+s2)].sort().join('')
```

