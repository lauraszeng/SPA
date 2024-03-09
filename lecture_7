# Week 7

we use AJAX to handle asynchronous operations 

an XMLHttpRequest object can be used to encapsulate all the methods and objects you need to fetch data asynchronously

API - application programming interface
commercially, these are either providing a service (likelier will charge to be used) or getting some sort of marketing out of it (likelier not to be charged). sometimes they're just for fun tho.

example of a fun API: https://funtranslations.com/api/yoda

each API's function is called an "endpoint"

is it a post API or a get API?
we send data using either POST or GET. 
POST - you send the info along with the request
GET - you append the info to the end of the query string, used for non-sensitive or not lengthy info bc it'll show up in the URL

URL may or may not include the query string

find out what parameters the API requires-- sometimes the API needs info in order to function

you might need an API key, which is a designated access for the API

XMLHttpRequest is an object with a number of properties, some methods, and an event 

## Wordle: Breaking it Down

how do you test an incomplete application?

start with the visuals. when you can see it, testing is much easier. 
start by creating one row of the board, then add more
then maybe figure out the answer that we're guessing

add one small element at a time. what's the next minimum step to see a result? there's no such thing as a step that's too small btw

"fake" what you are able to
writing code is like filming a movie, sometimes it's good to shoot scene 8 before scene 2
use placeholders for what you don't have

save less predictable elements for the end, such as the results of elements like the API, that way you know everything works

take it outside of the app-- whenever possible, create a separate mini app to test one part of your app

## Functional Programming

it's a declarative programmiong paradism in which function definitions are trees of expressions that map values to other values rather than a sequence of imperative statements, which update the running state of the funciton

imperative programming - HOW is it supposed to happen?
if you were baking a vake:
turn on over and preheat to 180, add 1 cup flour and 1 cup cocoa, add 1 cup water, etc etc

declarative - WHAT is supposed to happen
prehead oveb, mix dry ingredients, add wet ingredients, put into over for 30 min, remove cake and frost it
defines what should happen
is more descriptive
will use functions to define what is happening
often the results from one function will be passed to the next

you can use functions as a return value

immutability:
the underlying ovject doesn't change
sort() is NOT immutable
map() IS immutable

pure functions
computes a return value based solely on its inputs, there are no "side effects"

higher order functions
these take other functions as parameters, or return functions as values
they'll often use other functions to help them do their job
example: .map() or forEach()

recursion
occurs when a function calls itself
recursing by calling the same function repeatedly can happen in lieu of a loop
this can be useful when traversing a "tree" type object such as a complex object
these won't stop unless specified to

composition
involves combining several small, often pure, functions together
this can be done by chaining methods together by using the dot notation or passing the output from one funciton to the next

## array functions
join()
filter()
map()
reduce()

### filter()
cerates a new array, but only elements that pass a criteria test are kept
like map(), it is immutable

numbers = [1, 3, 5, 6, 7, 8]
// keep the odd numbers
oddNumbers = numbers.filter(n => n%2)
it operates on a true/false basis. if it passes it, then it is included. 0 is always false

### reduce()
produces a single valiue from an array
var value = myArray.reduce(((a,n)=> <do something that will update the accumulator>), startValue)
// add all of the odd numbers from the previous slide
newSum = oddNumbers.reduce(((sum,n) => sum+n), 0)
document.write(newSum)
accumulator gets updated by the new value

given an object called Product:
function Product (name, inStock)
{
    this.name = name;
    this.amount = inStock;
}
// add a method called show() that returns a string that includes the name and numbers in stock
function Product (name, inStock)
{
    this.name = name;
    this.amount = inStock;
    this.show = function() {return this.name + " amount: " + this.amount}
}
pens = New Product("Pens", 22);
// create an arrow function called writeLine that writes a string to the page followed by <hr>
function writeLine(str)
{
    document.write(str + "<hr>")
}
writeLine(pens.show())

// create an array of 44 products calles inventory and use foreach() and writeline() to show them all
inventory = [
    new Product("Pen", 22),
    new Product("Paper", 10),
    new Product("Clipboard", 0),
    new Product("Pencil", 40)
]
inventory.forEach(n => writeLine(n.show()))

// now use filter to create a new array with onlt the available items
// then convert each item to a string with map
// then use join to create a string consisting of each item produced from map followed by an <hr>
// use document.write to display this to the page
document.write(inventory.filter(n => n.amount).map(n => n.show()).join("<hr>"))

instock = inventory.filter(n => n.amount)
displayedItems = instock.map(n=> n.show())
displayString = displayedItems.join("<hr>")
document.write(displayString)

// then use reduce to get a count of all the items you have on hand
sum = inventory.reduce(((sum, n) => sum + n.amount), 0)
document.write("total items on hand: " + sum)

## React Introduction
React is a front-end JS framework originally created by facebook
the key to it is the render() function which creates a page view given a specification of a set of components
has building blocks called "components" that can be combined to create the UI for an application
uses declarative programming principles to construct an application that is function based
parts of React need a server to process advanced JS features and to cerate a React project
you should install node.js on your local system, as elements of node will be utilized, including npm (node package manager) and npx (node project execute)
tools we;ll be using include JSX (javascript.xml style language to create components), Babel (interpreter needed to convert JSX to JS), create_react_app (creates React applications that can then be executed)
React functionality is exposed through the React object-- find downloads at https://reactjs.org
you need the react,js and react-dom.js files
several variations exist for development and production
