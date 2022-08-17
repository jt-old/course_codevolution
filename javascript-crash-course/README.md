# JavaScript Crash CourseNotes

[JavaScript Crash Course](https://www.youtube.com/watch?v=XIOLqoPHCJ4&list=PLC3y8-rFHvwhuX4qGvFx-wPy_MEi6Jdp7&index=5)

Timestamps

00:00 Intro
00:27 Before we begin
02:12 What is JavaScript?
05:14 Setup
07:30 How to run JavaScript
13:55 Adding comments
14:47 Variables
18:38 Data types
28:28 Operators
37:54 Type Conversions
45:44 Equality
49:26 Conditional statements
57:47 Looping code
01:08:07 Functions
01:16:17 Scope

## Primitives

string
number
boolean
undefined
null
bigint
symbol

## Non-primitves

objects

## Operators

- Assignment
- Arithmetic
- Comparison
- Logical
- String
- Other

## Type Conversions

## Equality

==

strict ===

## Conditional Statements

if
else
else if
switch

## Loops

### For Loops

for (initializer; condition; final-expression) {
//code to run
}

ex.
for(let i = 1; 1 <=5; i++) {
console.log('Iteration number ' + i)
}

### While Loops

Same execution as For loops

- variable is set
- condition is evaluated
- code is run while the condition is true
- code is terminated once the condition is false

initializer
while (condition) {
//code to run
final-expression
}

ex.
let i = 1
while(i <=5>){
console.log('Iteration number ' + i)
i++
}

### Do..While loop

Executes the code block once and then evaluates the condition

initializer
do {
//code to run
final-expression
} while (condition)

ex.
let i = 6
do {
console.log('Iteration number ' + 1)
i++
} while(i <=5)

// since 6 is greater than 5, the loop is exectuted once and then terminated

### For..of Loop

Used to loop over a collection of data, like looping over an array

for (const item of array) {
//code to run
}

ex.
const numArray = [1,2,3,4,5]

for (const num of numArray){
console.log('Iteration of number ' + num)
}

- automatically iterates of array, and in each iteration, assigns the value of the element as num. ie. in the first iteration num = 1, first iteration num = 2, etc...

- best suited for a collection of data since it abstracts away two things.

  - 1. you don't have tp keep track of a variable ot increment the iteration count.
  - 2. you don't have to figure out how to access the item in the collection

## Functions

A JavaScript function is a block of code designed to perform a particular task. ie, add two numbers, multiply two numbers, etc...

Functions are reusable as they can be defined once and can be called with different values, resulting in different results

Functions help divide a complex problem into smaller chunks and makes your program easy to understand and maintain

ex. function name (parameter1, parameter2, paramter3) {
//code to be executed
}
name(argument)

ex.
function greet(username) {
console.log('Good morning ' + username)
}
greet('Bruce')

ex.
function add(a,b){
return a + b
}
const sum = add(5,10)
console.log(sum)

a + b are two input paramters. in the function body, we add the two paramters and return the sum of the two parameters.

### Arrow Functions

Give you a more precise syntax

const arrowSum = (a,b) => {
return a + b
}
const sum = arrowSum(25,25)
console.log(sum)

// since we just have a single return statement, we can ommit the curly braces and the return statement and inline the return statement on the same line. The new function looks like:

const arrowSum = (a, b) => a + b
const sum = arrowSum(25, 25)
console.log(sum)

// if you just have one argument, you can ommit the parathesis around the argument

ex.
const addFive = num => num + 5

## Scope

Scope determines the accessibility or visibility of variables

There are Three types of Scope

1. Block Scope
2. Function Scope
3. Global Scope

### Block Scope

Dictates that variables declared inside a set of curly braces cannnot be accessed outside the curly braces

### Function Scope

Variables declared inside a function are not accessible from outside the function

### Global Scope

The scope outside any block or function. A global scoped variable is accessible both inside a block and inside a function
