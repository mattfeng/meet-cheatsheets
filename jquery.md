# jQuery Cheatsheet
## 0 &ensp; Syntax Notes

`JQueryElement` refers to any element that was selected using JQuery (see **section 1.1**).

## 1 &ensp; JQuery Lecture 1: Selectors, Events, and DOM Manipulation

### 1.1 &ensp; Selecting Elements
```js
/*
Select element by tag:
    $("tag").eq(<index in array>)

Select element by class:
    $(".className").eq(<index in array>)

Select element by id:
    $("#idName")
 */

var thirdParagraph = $("p").eq(2) // select the third paragraph
var firstHeader = $("h1").eq(0) // select the first header

var secondImportant = $(".important").eq(1) // select the second element with the "important" class
var firstSecret = $(".secret").eq(0) // select the first element with the "secret" class

var aboutMe = $("#aboutMe") // select the element with id "aboutMe"
var heroBanner = $("#heroBanner") // select the element with the id "heroBanner"
```

#### 1.1.1 &ensp; Other Resources
- W3Schools: https://www.w3schools.com/jquery/jquery_selectors.asp

### 1.2 &ensp; Modifying Styles
```js
/*
Modify the CSS of a JQuery-selected element.

    JQueryElement.css(<property>, <value>)

*/

thirdParagraph.css("backgroundColor", "red");
secondImportant.css("color", "green");
aboutMe.css("fontSize", "60pt");
```
#### 1.2.1 &ensp; Other Resources
- W3Schools: https://www.w3schools.com/jquery/jquery_css.asp

### 1.3 &ensp; Creating Event Listeners
```js
/*
Add an event listener for events called <eventName> onto a JQuery-selected element.

    JQueryElement.on(<eventName>, function() {
        // do an action
    });

*/

aboutMe.on("click", function() {
    $(this).css("color", "aqua");
});
```

#### 1.3.1 &ensp; Other Resources
- W3Schools: https://www.w3schools.com/jquery/jquery_events.asp

### 1.4 &ensp; Modifying Content
```js
/*
Modify the HTML of a JQuery-selected element.

    JQueryElement.html(<newHTML>)

*/

firstSecret.html("The secret is <b>changed</b>.");
```

#### 1.4.1 &ensp; Other Resources
- W3Schools: https://www.w3schools.com/jquery/jquery_dom_set.asp

### 1.5 &ensp; Modifying Classes
```js
/*
Add, remove, or toggle classes for a JQuery-selected element.

    JQueryElement.addClass("className");
    JQueryElement.removeClass("className");
    JQueryElement.toggleClass("className");

*/

thirdParagraph.addClass("big");
secondImportant.removeClass("important");
aboutMe.toggleClass("hidden");
```

#### 1.5.1 &ensp; Other Resources
- W3Schools: https://www.w3schools.com/jquery/jquery_css_classes.asp

## 2 &ensp; JQuery Lecture 2: AJAX
### 2.1 &ensp; GET and POST requests
```js
/*
Make a GET request to <url> with parameters <dataToSend>. 
The variable `data` contains the information that is 
returned from the server.

    $.get(<url>, <dataToSend>, function (data, status) {
        // your code goes here
    })

Make a POST request to <url> with parameters <dataToSend>.
The variable `data` contains the information that is 
returned from the server.

    $.post(<url>, <dataToSend>, function (data, status) {
        // your code goes here
    })
*/

$.get("https://api.meet.sh/greet", {
    name: "Matt"
}, function(data, status) {
    // update page here
});

$.post("https://api.meet.sh/newMessage", {
    from: "Matt",
    message: "I love MEET"
}, function(data, status) {
    // update page here
});
```
