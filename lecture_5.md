# Week 5

callback functions are called once a specified task is done

remember to make a postman account for next week's class!

## Associative Arrays

the index to an array can be a string. this cerates a key-value pair.

flowers = [];
flowers["daisy"] = 12
flowers["rose"] = 15
flowers["carnation"] = 8
document.write(flowers["rose"])
// displays 15

if there's no value associated with the key, it adds a value to it. if there is, it updates it.

for (key in flowers) 
    document.write(key + " $" + flowers[key] + "-")
    // output: daisy $12 - rose $15 - carnation $8

associative array of (5) cities and the state they are on. cities should be the keys. display cities only. create a function to locate a city and return its state using the array as a parameter to the function

cities = []
cities["philly"] = "PA"
cities["boston"] = "MA"
cities["atlanta"] = "GA"

function citylister(array) {
    for (city in cities) 
        document.write(city + "<br>")   
}

function statefinder(array, city) {
    return array[city];
}

what if you want to find the city?

function cityfinder(array, state) {
    for (city in array) {
        if (array[city] == state) {
            return city;
        }
        return "not found..."
    }
}

## Simple Objects

an object can be a set of name-value pairs

var flowers = {
    daisy: 12,
    rose: 15,
    carnation: 8
}
^ doing the same as the same as making the associative array as pictured in the previous section
document.write (flowers)
is the same as 
document.write (Object.keys(flowers).join("<br>"))

## Destructuring an Array

destructuring assigns parts of the array to other variables
given:
x = [33, 5, 44, 63]

we could do 
first = x[0]
second = x[1]
third = x[2]

using destructuring:
var[first, second, third] = x;

creates an array of the variable. can be a mechanism to quickly create several variables

use destructuring to assign the age of tom, bill, pat, and jen the values 45, 34, 28, and 38 respectively
ages = [45, 34, 28, 38]
var["tom", "bill", "pat", "jen"] = ages
document.write(tom)
// output is 45

you can get current date/time using new Date()
there are several methods to extract the various parts of the sate
create an array consisting of the numeric month, day, and year
assign the array to variables month, day, year using destructuring
display in the form 1/1/2020
today = new Date()
document.write(today)
// the +1 is bc some of these measurements start at 0
var[month, day, year] = [today.getMonth()+1, today.getDate(), today.getFullYear()]
document.write(month + "/" + day + "/" + year)

## Spread Operator (...)

takes the subset of an array

given 
x = ["apples", "pears", "berries", "oranges];
var [pie, ... fruits] = x;
document.write(fruits);
// here fruits takes whatever's left adter pie. so it gets pears, berries, and oranges

can also combine two arrays
fruitpies = ["apple", "blueberry", "peach"];
creampies = ["lemon"];
allpies = [...fruitpies, ...creampies]

can be used in conjunction with a function parameter 

follow these instructions to create spread operator to create function with variable number of arguments
create a function with 2 arguments, first is a value and second uses spraed operator
initialize sum to the value
use forEach with the second argument, which is an array, to iterate throuhgh the values in the array and add them to the start value
display thesum at the end

function (startvalue, ...numbers) {
    sum = startvalue;
    numbers.forEach(item => {sum +item})
    document.write("the sum is: ")
}
addThem(10, 1, 2, 3, 4)

you have a list of students in class 1 (jane, alex, harvey) and a lsit from class 2 (seymout, emily, frank)
pass them to a functuiin as 2 string, then split them into two arrays, then combine into one array using spread operator
then sort the names
use map to display as numbered list

function combine_and_sort(class1, class2)
{
    class1 = class1.split(" ")
    class2 = class2.split(" ")
    document.write(class1 + " " + class2)
    wholeclass = [...class1, ...class2]
    document.write("<br>" + wholeclass)
    wholeclass.sort()
    document.write("<br>" + wholeclass)
    list = wholeclass.map(item => ("<li>" + item + "</li>"))
    document.write("<ol>" + list.join("") + "</ol>")
}
combine_and_sort("Jane Alex Harvey", "Seymour Emily Frank")

you could also do

document.write("<ol>" + [...class1, ...class2].sort().map(item => ("<li>" + item + "</li>")),join("") + "</ol>")

## Putting it all together

``` javascript
function findLess(arr, target)
{
    matches = []
    for (var i=0; i<arr.length; i++)
    {
        if (arr[i] < target)
        matches.push(arr[i])
    }
}
// find the largest number that is also less than 35
x = [33. 5, 40]
var [lastMatch] = findless
```

.filter() - creates a new array based on filter
arguments - a function  that provides the criteria for which items to "keep"

for example it could be simplified to

function findless(array, target)
{
    return array.fulter(item => item < 35>);
}

also look up reduce, which reduces arrays to a single value

## Objects using JSON

short for Javascript Object Notation
for data transmission (moving data from one place to another, commonly used with APIs) and representation
comprised of key value pairs
text based

mminimal and portable
based on conventions seen in many languages
code for parsing JSON is available in many languages

"key": value
start and end with {}
the keys are quotes
values can be strings, numbers, booleans, null, array, or other object containing this stuff

{
    "first name" : "Julie",
    "last name" : "Smith",
    "course" : "Web Apps",
    "grades" : [88, 95, 78, 93]
}

a JSON object can contain other objects
you can create a collection/array of json objects using []
you can turn an array into a string, do whatever you need to do, then turn that string back into an array
this is called SERIALIZATION, btw
serializing is turning it into a string
deserializing is turning it from a string back into its original form

### Built in JS Functions

parse(): parses a JSON serialized string back into an object
stringify(): serializes a JSON object into a string

student = {
    "name": "suzie",
    "course": "math"
}

str_student = JSON.stringify(student)
and then
obj_student = JSON.parse(str_student)

what's the difference between a simple object and a json?
the quotes around the key
otherwise, they're the same
you can use stringify on simple objects, actually

## Objects in JS

a class is the definition for a set of objects
they have properties (cvcharacteristics, state), methods (things it can do), and events (things the object can respond to)

instances are like a recipe, and properties are like ingredients

use "new" to create an instance/object for a class (sometimes there are shorrtcuts that don't require new)
new implicitly calls the constructor (an initializer, which generally has some parameters) for the class

you can call class to create a new object

## Creating Objects with Functions

the function defines the class and is the constructor method

by convention, classes start with capital letters

use the keyword "this" to refere to the current instance
here the name of the class is "Rectangle"
function is the conbnstructor of the class
len and wid are properties of the class

function Rectangle(len, wid)
{
    this.length = len;
    this.width = wid;
}

instance the clas using new:
r = new Rectangle(3,4);

access the data members using the dot notation
area = r.length * r.width;

craete a class in JS called flower w/ two properties, name and price, that are set in the constructor
instance the three flowers cerated previouslt
display name/price of one of the flower objects

function Flower(name, price)
{
    this.name = name;
    this.price = price;
}

f1 = new Flower("rose", 15)
f2 = new Flower("daisy", 12)
f3 = new Flower("lily", 10)

document.write(f.name + f.price)

## Methods

methods help the object to do something
it's a function that uses the keyword this to refer to members of the object
attach the method to the class by assigneing it in the constructor

function area()
{
    return this.length * this.width
}

modify flower class to add a method called "show" that returns a string with the name and price
remember to always use "this" when doing stuff with class constructing bc you're not referring to a specific instant

function Flower(name, price)
{
    this.name = name;
    this.price = price;
    this.show = function () {return this.name + " $" + this.price}
}

create an array of the three flower instances
flowers = [new Flower("rose", 9), new Flower("carnation", 7)]
use map() to create a new collection with the flower data
collection = flowers.map(f => f.show())

flowers.map(f => s.show()).join("<br>")

function find (arrFlowers, name)
{
    // return price of item
    return arrFlowers.filter(f => (f.name == name)[0])
}
