# Week 4

## Review
Remember that when you're working with javascript, you can access everything as an element/object

When you know you're going to have multiple of something, give it a class. If you're only going to have one of an object, give it an id.

queryselectorall - returns an array of everything that shares that specific query

use line-height in CSS to vertically center things

always make sure that you're writing script to manipulate objects that have ALREADY BEEN CREATED FIRST

remember that with addeventlistener, the event is the trigger, and the event handler is the response to the trigger

use window.onload = function() {} to load the page before executing the function to bypass the problem of trying to manipulate objects that haven't been created yet

## Callback Functions
these are used frequently for asynchronous operations (whcih means you start something, don't necessarily finish it, have other things execute in the backgrounf, then retutn to it at some point)

the operation executes the callback function when it's complete

example- setTimeout, this takes a callback as a parameter to indicate what happens when the timer goes off

``` js
setTimeout(hey, 2000)
function hey()
{
    alert("hey")
}
```
^ after 2000 milliseconds, function "hey" is called, which sets off an alert that says "hey"

## Arrays
Things we can do with array:
forEach
map
destructuring
spread operator
arrays as return values
associative arrays

### forEach

``` js
// sum all items
sum = 0
numbers = [2, 4, 6, 8, 10]
numbers.forEach(function(item) {
    sum+= item;
}) //end forEach
```

forEach doesn't take index values into account the way that for loops do

you can also do numbers.forEach(item=>{sum+=item})

you can use querySelectorAll() to create arrays that you can use forEach with

note that document.querySelector only returns the first result

var sentence = "how now brown cow"
vowels = [a, e, i, o, u]
result = 0
sentence = sentence.split("")
sentence.forEach(function(letters) {
    if (vowels.includes(letters))
    result ++;
})

### map

map() produces a new array from an existing array. items in the new array are typically based on the original array and modified using a function

``` js
//given:
x = [33, 5, 44, 63];
//create a new array with each item doubled
a = x.map(item => 2*item);
// curly brackets not needed bc we're just returning something. if we DO put curly brackets, we'd need a return statement
// turn a set of items into a list
a = x.map(item=>"<li>" + item + "</li>").join("")

<div id="red">X</div>
<div id="green">X</div>
<div id="blue">O</div>
<div id="yellow">X</div>

ids = "red green blue yellow".split(" ")
// get the content of the div indicated by the id
ids.map(id=>document.getElementById(id).innerHTML)
```
    