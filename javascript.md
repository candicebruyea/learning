# Javascript Basics

## Backround

### A Client Side Language
It waits to execute code until it's on the computer, using the browser. The browser engine executes the code. Can Render, Post or Get: change the display, send data, or fetch more data from the server.

### An Interpreted Language
Code is read line by line instead of having to go through a compiled step where it's converted to a machine code (0's and 1's). Compilers have sped up this process.

### A C-Like Language
It stole much of its syntax from C. This includes if statements, for loops, while loops and more.

### Javascript Environments
* Node JS
    * for doing backend stuff (write apis, talk to databases or other servers).
* Go
    * for more performance intensive uses
* C++
    * Even faster than go.

## Syntax

### Variables

Primitives
* Numbers
* Booleans
* Strings of text

Compound Data
* Arrays []
    * lists
* Objects {}
    * also known as 'dictionaries' in other languages. You give it a word and it retrieves the definition. 

kinda like this...

    const arr= [1,2,3]
    const obj= {
        name: "Aaron"
        age: 26
        }

So if you give it the key 'name' it'll retrieve 'aaron'

Declaring variables
* let
    * Use if you plan to chang the variable later
* const
    * Use if you don't plan to change the variable later.

### The DOM (The Document Object)
It's a javascript representation of the structure of our html. Is present in the variable document when we load the page.

#### Contains many element objects
Can search for specific elements, add user event listeners or change how the page looks.
all this is possible through a set of methods called the Browser API

### Loops
#### for in loop
used to iterate over an object

    {name: "Aaron",
    age: 26}

    for (let key in obj) {
        console.log(key, obj);
    }

    'name' 'Aaron'

#### for of loop
used to iterate over an array

    [1,2,3]

    for (let num of nums) {
        console.log(num);
    }

    1
    2
    3

### Functions
Any code we want to use more than once.

delclare with keyword 'function' + function name + variables we want to input + the output/result we want to return

    function add(first,second){
        return first+second
    }

Arguments
Call a function with its name and by passing in unputs as arguments.

    add(1,2)

Methods
The same as functions but they're attached to different data types. We call them with a '.'

    "hi".toUpperCase()  --> "HI"
    ['c','b','a',].sort() --> ['a','b','c']
    [1,2,3].indexOf(1) --> 0

Arrow Functions
Written with paramaters on the left and auto return on 1 line. 

    (a,b) => a+b

    Generally used in array methods. Takes a function as an argument and runs it on every item in the array.
    [1,2].map(n=>n+1)

