Assignment this week: Create Tic-Tac-Toe board with HTML and Javascript

Assignment next week: Create functional Tic-Tac-Toe with Javascript

# Week 2

DID YOU KNOW:

You can comment out things in html `<!--like this-->`

### HTML Tables
Create a table with the `<table>` tag
- `<tr>` - make rows
- `<td>` - elements (table data), aka columns, whichmake up the table rows
- `<th>` - header rows, these are bold and centered
- you can use an attribute called "border" to customize the lines (eg. `<table border="1">`)
- use cell padding (space between content and the edges) to customize how cells look
- cell spacing is the space between the cells themselves
- rows are autosized to the tallest item and columns are autosized to the widest
- css used to align elements
- use id

``` html
<table border="1" cellpadding="20" cellspacing="0">
    <tr>
        <th>1</th><td>2</td>
    </tr>
</table>
```
### HTML Forms
make these with the `<form>` tag
`<input>` allows you to input information, and can take the form of text box, radio buttons, checkbox, submit buttons, reset, etc
use textboxes for random input, where you don't know what kind of input the user will give
you can hide these and store info in them you don't want the user to see
checkboxes are not mutually exclusive. radio buttons are.
radio buttons in the same group all have the same name
submit means to do the action

attributes
method - how the information is being sent (query string? file?)
action - serverside program that form data will be sent to
name - name of the form, which is how we'll refer to it
type - what kind of input?

label - mostly used for styling

use value instead of id so you don't have to look at each element individually, and so that you CAN use a loop to cycle through with JS

in dropdown, size is how many choices you can see at once

```html
<form method="" action="" name="">
    <h1>Form Demo</h1>
    <label>Enter your name:</label>
    <input type="text" name="your_name">
    <br>
    <label for="checkme1">check me</label><input type="checkbox" name="checkme1" id="checkme1">
    <label>check me too</label><input type="checkbox" name="checkme2" id="checkme2">
    <br>
    pick one
    <label>me</label><input type="radio" name="pickme" id="pickme1" value="pickme1">
    <label>me too</label><input type="radio" name="pickme" id="pickme2" value="pickme2">
    <br>
    drop down time
    <select name="select_food" size="1">
        <option>Red</option>
        <option>Blue</option>
        <option>Green</option>
    </select>
    <br>
    <textarea name="mylist">Enter your list of other favorites</textarea>
    <button>Submit</button>
</form>
```

### CSS (Cascading Style Sheet)
allows formatting to be separate from content and defines style instructions through style rules
each rule has a selector and a set of property/value pairs that decide how things will work
h1 {
    text-align:center
}
selector = h1
properrty: text-align
value = center
this rule states heading 1 shoudl be centered

you can place these inline (in the html tag), internal (within `<style>` tag), or external (in separate file, by convention style.css)

the closer a rule is to the selected element the stronger the precedence

ids are all individual
give same class to things which all have the same purpose so you can style them together

#### Selectors
html tag - h1
style class - .my-class
id - #the-id
pseudo-element(modifies another selector) - li:first-child (aka first thing in a list)

selector combinations
a:hover - rule appplies when mouse is over the link
a,b - rule appplies to both a and b
a b - rule applies when b is contained within a 
    h1 em = <h1><em>here is text</em></h1> <- here is means whenever em is contained within h1
tag[attr=value] - rule applies to specified tag onle when the attribute is set to the given value
tag.x - rule applies for tag when its class="x"

```html
<head>
    <style type="text/css">
        .div1 {
            border:1px solid #123123;
            width: 200px;
            padding: 10px 20px;
            text-align: center;
            display: inline-block;
        }
        .div1:last-child {
            width: 300px;
        }
        .div1:hover {
            font-weight:700;
        }
    </style>
</head>
    <body>
        <div class="div1">Content!</div>
        <div class="div1">Content!</div>
        <div class="div1">Even More Content!</div>
    </body>
</style>
```

DIVS

divs are container that create a new line, but otherwise don't do anything by themselves

### Colors
use hex, rgb, or rgba colors
hexadecimal colors:
RGB: red green blue
begin with #
values go up to 255
#rrggbb, where each extion ranges from 00 to FF (hexadecimal notation)

rgb() color
- rgb(12, 120, 155)
- rgba(23.45,65,0.75) where the last digit refers to opacity, 1 is totally opaque and 0 is totally transparent

## Javascript

programming with JS is similar to C or C++
it's an interpreted (browser will look at it and execute it one line at a time) scripting language that supports object oriented programming
object libraries: DOM (document object model)
incorporate into HTML page using the `<script>` tag
we'll be learning ES6 (ECMAScript6), which is the latest version, used by React

output to the page:
document.write() or alert() or console.log()

document.getElementById("results").innerText= "This is the result"
- this fills the element that has id "results" with the text "this is the result"

store values in variables. you can do this a couple ways
var x; x=10;
let x = 10;
const x=10;
x = 10;

const cannot be reassigned
var and let differ in scope
var is function scoped (scoped to a whole function)
let and const are block scoped (within one particular code block, denoted by {})
declare several variables at the same time
var x; y;
let x = 10, y;
null assigns a non-value to a variable, essentially keeps it blank

start a procedure/function like this
function foo() {

}
then call it at the end to actually run it
foo()

if(true) means it will always happen

Data Types in Javascripts:
JS is loosely typed, meaning data types are deduced

numbers:
- integral = no decial point
floating

parseInt - takes string and makes it into a number
parse float - turns integer into number
NaN = not a number

use + to concatenate strings
if you concatenate a number with a string, the result is a string

<body>
    <script>
        document.write("written with JS!")
        alert("Wow! It's JS!")
        console.log("JS......") <--! can only be seen in inspect mode-->
    </script>
</body>
