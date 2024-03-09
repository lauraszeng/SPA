# Week 3

## Javascript
remember that when you concatenate them, numbers are read as strings. 
thus this list (0,3,6,9,12,15) would be ordered as thus (0,12,15,3,6,9)

### Operators
there are several types of these
arithmetic
arithmetic with assignment
assignment
comparison
logical
concatenation

(x + y) is an expression, where + is the operator, and x is the operand, and its purpose, like all expressions, is to generate a value

arithmetic contains:
+ addition
- subtraction 
++ increment - adds 1
-- decrememnt - subtracts 1
* multiplication
/ division
`#` modulus - calculates remainder of first operand divided by second operand

operator precedence follows PEMDAS
increment and decrement are first, then negation, then ! (aka NOT), then arithmetic, then concatenation, then comparisons, then == and !=

compound assitnment operators
(x = x + 3) is the same as (x += 3)

four ways to add 1 to a value
x = x +1
x++
++x
x += 1

assignment is a statement like (a = 8)
the value of the assignment operator is the thing that is being assigned 

comparison
== equality - true if operands have the same value
=== is strict equality between data types
!= inequality
also >, >=, <, <==

conditional operator
test ? result1 : result2
this means fo the test, if the result is true, then the calue of the operator is result 1, otherwise it is result 2

this is an operator, there is no implied assignment

logic operands (and, or, not) glue two comparison operators together
&& AND - true when two opeands are both true
|| OR - true when eitehr of two operands is true
! NOT - true when an operanc is false
you can use a forcing funcgtion, which is when the value of one input expression forces the output result of a logical operator
the function for AND is false
the forcing function for OR is true
shortcut calculation - if there are two parts of an expression and the first part foces the value, the second part is not considered

+ operator
string + string is concatenation
string + number converts number to string and then concatenates
number + number is just addition

comparison operators
string > string defaults to alphabetical order
string > number converts string to number and compares numerically
number > number is just numerical value

prefix v postfix notation
X++
value is c
add one to x
++x
value is x+1
add one to X

conditionals
the IF construct helps determind program flow based on a yes/no question
if (n>1)
    alert("do something");
you don't need {} if it's just the one statement
if we watn to take differnt actions when the conditional statement is false, we use ELSE and ELSE IF
each part of an if/else if/ekse statement is mutually exclusive
conditions shouldn't follow else. use conditions for else if

switch
shorthand for if
switch(expression)
{
    case value1: do this; break;
    case value2: do this; break;
    default: do the otjher thing; break;
}
break keeps itfrom falling through
default is placed at the end and is optional

two kinds of loops, counting and waiting
in a counting loop, you do something for a specified number of times
do a for loop for these
in a waiting loop, you do something until something happens
do a while loop for these

for loop syntax
for (init; test; update)
    {
        // loop statement(s)
    }
init = statement that occurs prior to any iteration
test = conditional expression that is evaluates at the beginning of each iteration, when it evaluates as false, exit the loop
update = statement taht occurs at the end of each iteration. often used to update a counter

while loop syntac
continues to uterate as long as the conditional expression is true
while (test)
{
    // loop statements
}
do {
    // loop statements
} while (test);
while loops are guarabteed to run at least once

break and continue
these are statements that provide additional control
break exits a loop, geenrally used as part of an if construct, used to provide an alternate place to exit from the loop
use these carefully to avoid unreadable code
continue ends teh current iteration fo a loop
in a whhile loop goes directly to the update
in a for loop goes directly to the test

i = 40
while (i >= 40) {
    i -= 2
    if i == 0; break;
}

for (i=40; i>=10; i-=2)
{
    document.write(i + "</br>")
}

x = prompt("give number")
do {
    x += x
} while x <= 20;

functions
funcitons are procudures, or a named sed ot tasks that aren't executed until the function iss called
they are anonymous and are used a s aparameter to another function
they have inputs, outputs, and byproducts
use the return statement to end the funciton and return a value
function add1(parameter1,parameter2)
{
    var 1 = parameter1, b = parameter2, sum;
    sum = a + b;
    alert ("the sum is: " + sum)
}

add(3,4);

the return statement
function add2(parameter1,parameter2)
{
    var 1 = parameter1, b = parameter2, sum;
    sum = a + b;
    return sum;
}
this gives you the value only when you call the function

events and event handlers
events are things that happen on the page
using the js event property, we can do something like this
btn1.onclick = "dosomething"
btn.onclick = function()
{ /*do something*/ }
add an event listener
btn1.addEventListener("click", dosomething)
best to add these once everything has been loaded
window.onload= function()

arrow functions
use the arrow as a shortcut to define and then call a function
you can have a function serve as a parameter, similar to the concept of a function pointer
function hello() {return "hey"}
simplify to

simplify to 
hello = () => "Hello World!";

you can pass functions as parameters

arrays are implemented with the Array object
things = [1, 2, 3]
these can have differbnt data types, all that matters is the index
a loop counter can be used to iterate through an array
