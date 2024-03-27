# Class 8

Notes:

Midterm from Sun - Wed

Make a study guide that lists what we covered every class for easier review

will be open-note

## Review

### URLs and HTTP Requests
- client/browser vs server
- how do http requests work?
- role of the client vs the server
- how is an SPA different from a website?
    - in non SPA: client sends http request and server send new page thru http response
    - in SPA: client sends http request to server with placeholder requestsand server will respond but it won't send new page but will instead fill in the placeholders
- pros and cons of an SPA
    - SPAs are faster and can run asynchronously, which lets you do two things at the same time
    - unfortunately they're nto good for SEOs bc SEOs work better when you have multiple pages to index

### HTML Refresher
- tags
    - container tags
- attributes and values
- entities
    - start with a & and end with a ; and they stand for symbols, like &copy; &hearts;
- commonly used tags
    - h1, ul, ol, li, form, input, select, a, div, span, img

### CSS Refresher
- selector
- property/value pairs
- selector variations
    - .a
    - a b
    - a,b
    - a:hover
    - a:first-child
    - etc
- where styles live
    - external (separate file)
    - internal(at top of the file)
    - inline(at the tag level)
- hex colors vs rgb bs rgba
    - #123456
    - rgb(1,2,3)
    - rgba(1,2,3,0.5)
        - the a is for opacity
- box model (padding, margin, box-sizing: border-box)
- display, position, z-index
    - display refers to whether something is inline-block or hidden
    - position can be relative or absolute or fixed (in the same place no matter what)

### Javascript
- javascript vs ECMAScript vss ES6
    - javascript and ECMAscript are basically the same thing
    - ES6 is the latest version of javascript, lets us use arrow functions
- `<script>` tag
- var vs const vs let
    - var x = 6 is the same as x = 6, but sometimes when you're using objects, you'll need to use var
    - let has a different scope-- `var` is function scoped and `let` is block scoped and lets you reuse the function name later in a different place
    - `const` is function scoped and can't be changed
    - `global` variables are defined outside of the function and apply to the whole file
- scope
- null
- loosely typed, parseInt, parseFloat
    - loosely typed means javascript deduces the type of data you're working with
- strings
    - anything in "" or ''
- operators: arithmetic, comparison, logical, assignment, conditional
- precedence, associativity, unary vc binary vs ternary operators
    - precedence means some operators are more important than others a la PEMDAS

### Loops and Conditionals
- if, else if, else
- for
- for __ in __ (objects)
- for __ of __ (arrays)
- while, do while
- break, continue

### Functions
- basic syntax
- arrow functions
- function definition as a value
- functions as expressions
- assigning a function to a variable
- functions as return values
- functions as object methods

### Event-driven Programming
- onclick
- onchange
- when/where to associate an event with an event handler
    - you can do this at the tag level, but that's not best practice
    - best to do these after you've loaded the page with window.onload =
- displaying results from an event handler

### Arrays
- the array object
    - sort
    - join
    - map
    - forEach
    - reduce
    - filter
- immutable vs mutable methods
- destructuring an array
    - turn the array into some variable
    - var [a, b, c] = [1, 2, 3, 4]
- the spread operator
    - gets you the rest of something
    - var numbers = [1, 2, 3, 4]
    - x = [...numbers, 5];
- associative arrays
    - associates a key with a value

### Asynchronous Operations and APIs
- callback function
    - function that is called when the asynchronous operation is done
    - there are also event functions, which happen after an event occurs
    - also poll functions
- XMLHttpRequest
    - object that encampsulates everything we need to send a request to a server
        - status
        - response text
        - events (onreadystatechange)
    - status codes
- CORS
    - cross origin request sharing
    - from a server perspective, something not on the server is trying to access the server, and the server sets a policy as to whether or not that would be allowed
- APIs
    - application programming interface
    - you can access these for free, or with api keys
- postman.com
- promises and fetch
    - promises create a placeholder for the data and let you proceed with other tasks knowing that the data will be coming through
- await/async
    - await means you wait until something completes before proceeding

### Using Objects
- remember that by convention when you name these they should start with a Capital Letter
- constructor
- methods, properties, members
    - method is a characteristic/state of the object
- instance an object with new
- this
- dot notation to access a member of an object
- extends
- private members (#)
    - not accessible using the dot notation

### Associative Arrays and Objects
- associative array and simple object
- function object and class object
    - function object is both the definition ofthe constructor and the class
    - class creates a function called a constructor that contains additional methods in it to initialize the object, and also lets you add additional functions
    - these are both used the same way, tho the functional object is slightly preferred for declarative programming
- JSON object
    - JSON.parse()

### OOP - The Process
1. identify all possible object types
2. identify data elements in each object
3. identify actions for each object
    - setter (something that sets an item/property of a class)
    - getter (something that gets the value of an item/property of a class)
    - page update
4. identify nesting - which objects manage.control other objects
- REMEMBER: each object should handle its own tasks, sort of like how an orchestra has multiple musicians for multiple instruments

### Example: Card Game
- objects:
    - card
    - deck
    - game
- hierarchy
    - game uses the deck
    - deck has hards
- class members: Card
    - suit
    - rank
    - value
    - getValue()
    - display()
- class members: Deck
    - cardsLeft
    - shuffle()
    - deal()
- class members: Game
    - players []
    - startGame()
    - playGame()
    - checkWin()

## React

### React Elements
- react libraries:
    - src="https://unpkg.com/react@17/umd/react.development.js">
    - crossorigin src="https://unpkg.com/react-dom@17/umd/react-dom.development.js">
- front end user interface wth declarative programming
- a react element defines what is supposed to happen on the page
- it builds/manipulates a "virtual" DOM and then writes it to the page vs the browser DOM, which is written directly on the page
- document.createElement and document.appendChild are examples of methods that build the browser DOM
- create a React element using `React.createElement()`
- render the element to the page using `ReactDOM.render()`

### The React Element Object
- React objects take an element and break it into parts
    - type property defines the type of element
    - key provides unique iden
    - props is what's contained as children of the element, like id, class, etc
    - ref gives direct access to an element

### createElement
- createElement() sets up a React object
```
React.createElement(
    "h1",
    {id: "main", className: "title"},
    "Hi there"
)
```

### Render to the Page
- ReactDOM.render(my_react, root_element)
    - my_react is the thing you're appending
    - root_element is the thing you're appending to
- you MUST render within a root element, like to a <div> or something. this means your page must have at least one element defined. don't just append to <body>
- create and render: given a root element with id, "myapp"
```
<div id="myapp"></div>
<script>
    var hello = React.createElement("h1", {id: "main", className: "blue"}, "Hello React World!");
    ReactDOM.render(hello, myapp);
</script>
```

### Example: Add Attributes
- render this to react and add a css style for the quote class to set a width of 400px and have it centered in the page

```<p class="quote">Four Score and Seven Years</p>```

```
<style>
    .quote {
        width: 400px;
        margin: 0 auto;
    }
</style>

var hello = React.createElement("p", {className: "quote}, "Four Score and Seven Years)
ReactDOM.render(hello, myapp)
```

use react to create a link to access weather.com

var weather = React.createElement("a", {href: "weather.com", target: "_blank"}, "weather link")
ReactDOM.render(weather, myapp)

### Adding Child Elements
- createElement can be nested to include child elements and can render nested HTML elements

- create ordered list with items finance, weather, sports

```
var hello = React.createElement("ol", {id: "my_list"},
    React.createElement("li", null, "Finance"),
    React.createElement("li", null, "Weather"),
    React.createElement("li", null, "Sports"),
);
```

### Using React to implement a nested element
- update previous list so that each item has a link in it
```
var hello = React.createElement("ol", {id: "my_list"},
    React.createElement("li", null, React.createElement("a", {href: "finance.com", target: "_blank"}, "Finance")
    ),
    React.createElement("li", null, React.createElement("a", {href: "weather.com", target: "_blank"}, "Weather")
    ),
    React.createElement("li", null, React.createElement("a", {href: "sports.com", target: "_blank"}, "Sports")
    ),
);
```
