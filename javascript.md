# JavaScript Cheatsheet

## 0 &ensp; Syntax Notes
In JavaScript code, if you see ``<parameter>``, you should replace ``<parameter>`` with an actual value.

For example, ``Array.push(<newItem>)`` might become ``names.push("Matt")``, where ``names`` is type ``Array``, and ``"Matt"`` is the new item I want to add. There should not be any angle brackets (`<`, `>`).

## 1 &ensp; Introduction to JavaScript, Lecture 1

### 1.1 &ensp; Adding JavaScript to your Web Page
```html
<html>
  <head> <!-- ... --> </head>
  <body>
    <!-- ... -->
    
    <!-- METHOD 1: Write code directly in HTML file -->
    <script> 
      // my JavaScript code
    </script>
    
    <!-- METHOD 2: Load from external file -->
    <script src="code.js"></script>
   </body>
</html>
```

### 1.2 &ensp; User Input/Output (I/O)
```js
// Ask a question in a pop-up
prompt("Question");
// Display a message in a pop-up
alert("Popup Message");
// Display a message on the webpage
document.write("Message");
// Write a message to the console (typically used for debugging)
console.log("Debug message");
```

### 1.3 &ensp; Variables
```js
// Declare a variable
var myName = "Matthew";
var myAge = 19;
// Change variable value
myName = "Matt";
```

### 1.4 &ensp; Numbers
```js
var bankBalance = 120;
// Convert a Number to a String
// Number.toString();
bankBalance.toString(); // "120"

// Convert a Number to a String with <digits> number of digits after the decimal, always
// Number.toFixed(<digits>);
bankBalance.toFixed(2); // "120.00"

// Convert a Number to a String with <digits> total
// Number.toPrecision(<digits>);
bankBalance.toPrecision(4); // "120.0"
```

### 1.5 &ensp; Strings
```js
// Convert a String to a floating-point Number
// parseFloat(<string>)
parseFloat("50.34"); // 50.34

// Convert a String to an integer Number
// parseInt(<string>)
parseInt("15"); // 15

// Remove the whitespace from the ends of a String
// String.trim();
"  hello  world  ".trim(); // "hello  world"

// Get a substring (also called a "slice") from a string
// String.substring(<start>, <end>)
// <start> is the index of the first character you want
// <end> is the index of the first character you don't want
var fullName = "Matthew Feng"
var firstName = fullName.substring(0, 7); // "Matthew"
var lastName = fulllName.substring(8, 12); // "Feng"

// Split String into an Array
// String.split(<divider>)
var names = fullName.split(" "); // ["Matthew", "Feng"]

// Convert String to all uppercase - doesn't modify the original String
// String.toUpperCase();
var message = "Hi There";
message.toUpperCase(); // "HI THERE"

// Convert String to all lowercase - doesn't modify the original String
message.toLowerCase(); // "hi there"
```

### 1.6 &ensp; Arrays
```js
// Create a new array
var empty = [];
var colors = ["red", "yellow", "tree"];

// Edit a value in the array
colors[2] = "green"; // ["red", "yellow", "green"]

// Add a value at the end of the array
// Array.push(<newItem>);
colors.push("blue"); // ["red", "yellow", "green", "blue"]

// Get the length of the array
// Array.length <-- NO PARENTHESES!
colors.length // 4

// Insert a value at position <pos>
// Array.splice(<pos>, 0, <newItem>);
colors.splice(1, 0, "orange"); // ["red", "orange", "yellow", "green", "blue"]

// Sort the array - modifies the array!
// Array.sort();
colors.sort(); // ["blue", "green", "orange", "red", "yellow"]

// Reverse the array - modifies the array!
// Array.reverse();
colors.reverse(); // ["yellow", "red", "orange", "green", "blue"]
```

### 1.7 &ensp; Conditionals
```js
/* 'if-else if-else' statements:
if (<condition1>) {
  // do things
} else if (<condition2>) {
  // do other things
} else if (<condition3>) {
  // do other other things
} else {
  // do these if nothing matches
} */

var number = 10;
if (number < 5) {
  console.log("number is too small");
} else if (number > 15) {
  console.log("number is too big");
} else {
  console.log("number is just right!");
}

/* 'switch' statements:
switch (<var>) {
  case <case1>:
    // do stuff
    break; // DON'T FORGET THE BREAK AFTER EACH CASE!
  case <case2>:
    // do other stuff
    break;
  default:
    // do this otherwise (if none of the other cases match)
} */

var fruit = "apple";
switch (fruit) {
  case "apple":
    console.log("I love apples");
    break;
  case "pear":
    console.log("Pear is ok");
    break;
  default:
    console.log("All other fruit is awesome");
}
```

#### 1.7.1 Comparisons
```js
// Logical AND: Both <condition 1> and <condition 2> must be true
// <condition 1> && <condition 2>

// Logical OR: Either <condition 1> or <condition 2> must be true
// <condition 1> || <condition 2>

// Logical NOT: Change <condition> from true to false, or false to true
// !<condition 1>

// Comparison operators (less than, less or equal, greater than, greater or equal, not equal, equals
// <, <=, >, >=, !=, ==

// Strict equality or inequality: Checks both VALUE and TYPE
// !==, ===
```

### 1.8 &ensp; Loops
```js
/* 'for' loop:
for (<initialize>; <continuing condition>; <increment>) {
  // do stuff 
} */

for (var i = 0; i < 10; i++) {
  console.log(i);
}

/* 'while' loop:
while (<continuing condition>) {
  // do repeating things
} */

var gameEnded = false;
while (!gameEnded) {
  // play game
}
```

### 1.9 &ensp; Functions
```js
// Define a new function
function myFunction() {
  // your code here
}

// Define a function that has two parameters and returns a value
function add(a, b) {
  return a + b;
}
```

### 1.10 &ensp; Error Handling
```js
/* 'try-catch' statements
try {
  // code that can go wrong
} catch (error) {
  // do something with the error
}

// Throw (also known as 'raising an error') custom error if something isn't right, for example
//   if the user supplied a String instead of a Number
throw new Error("what went wrong");
*/

var a = 10;
var b = 0;

try {
  if (b == 0) {
    throw new Error("Division by 0");
  }
  document.write(a / b);
} catch (error) {
  console.log(error.message);
}
```

## 2 &ensp; Introduction to JavaScript, Lecture 2

### 2.1 &ensp; Objects
#### 2.1.1 &ensp; Object literals
```js
/* 
Explicitly write out the values for the properties of an Object
Objects in JavaScript are similar to dictionaries in Python: key -> value pairs.

var objectName = {
    property1: value1,
    property2: value2,
    property3: value3
}
*/

var person = {
    firstName: "Matthew",
    lastName: "Feng",
    age: 19,
    favoriteFoods: ["dumplings", "kiwi"], // you can have arrays in objects
    job: { // you can embed objects in objects
        position: "Research Intern",
        company: "NIST"
    },
    fullName: function () { // you can even have functions in objects!
        this.firstName + " " + this.lastName;
    }
}
```

#### 2.1.2 &ensp; Object constructors
```js
/*
Define an Object constructor 
function ObjectName(param1, param2, param3) {
    this.property1 = param1;
    this.property2 = param2;
    this.property3 = param3;

    this.method = function () {
        // do something 
    }
}

// Creating a new object using the constructor
object1 = new ObjectName('a', 'b', 'c');
*/
```

### 2.2 &ensp; JSON
```js
var harryPotter = {
    title: "Harry Potter and the Philosopher's Stone",
    author: "J. K. Rowling"
}

// Convert an Object into a JSON string
// JSON.stringify(<object>)
harryPotterString = JSON.stringify(happyPotter);

// Convert an JSON string into an object
// JSON.parse(<json-string>)
JSON.parse(harryPotterString);
```

### 2.3 &ensp; Selecting and Modifying Elements on the DOM
```js
/*
document.getElementById(<id>) // gets a unique element from the DOM using the id attribute
document.getElementsByClassName(<class>) // returns a list of elements that have class <class>
document.getElementsByTagName(<tag>) // returns a list of elements that have tag <tag>
*/

document.getElementById("myButton") // selects the element with id of "myButton"
document.getElementsByClassName("message") // selects ALL ELEMENTS with class of "message"
document.getElementsByTagName("p") // selects all paragraphs on the page

/*
Editing properties of DOM elements
DOMElement.style // change the style of an element
DOMElement.innerHTML // change the content of an element
*/

var btn = document.getElementById("myButton");
btn.style.backgroundColor = "red";
btn.innerHTML = "I'm different now!";
```

### 2.4 &ensp; Events
```html
<!-- Call functionName() when eventName happens -->
<tag eventName="functionName()">...</tag>
<!-- If you want to pass the object that got the event -->
<tag eventName="functionName(this)">...</tag>
```

In `my-page.html`:
```html
<button onclick="alertMe()">Surprise!</button>
<button onclick="changeText(this)">Click me!</button>

<script src="events.js"></script>
```

In `events.js` (a separate file!):
```js
function alertMe() {
    alert("Hi!");
}
function changeText(object) {
    object.innerHTML = "You clicked me!";
}
```

### 2.5 &ensp; Event Listeners
```js
/* Attach an event listener to DOMElement
DOMElement.addEventListener(<eventName>, function (event) {
    // do stuff here
    // event.target is the object that was clicked
});
*/

// we have to add the [0] because the function ALWAYS returns a list.
var body = document.getElementByTagName("body")[0];
body.addEventListener("click", function (event) {
    alert("You clicked!");
});
```
