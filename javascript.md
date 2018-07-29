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

### 1.8 &ensp; Loops

### 1.9 &ensp; Functions

### 1.10 &ensp; Error Handling

## 2 &ensp; Introduction to JavaScript, Lecture 2

### 2.1

### 2.2
