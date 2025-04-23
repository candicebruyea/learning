# PHP Basics

It's a server side language: all of our php code runs on a server and only the result (not the code) gets sent to the visitor's browser

## Table of Contents

* [Begin and End PHP](#id-begin)
* [Echo](#id-echo)
* [Semi-colon](#id-semi)
* [Variable](#id-variable)
* [Function](#id-function)

<div id='id-begin'/>

## Begin and End PHP
Begin and end php mode with this: 
    
    <?php ?>

You can seamlessly jump in and out between php and html.

<div id='id-echo'/>

## Echo
echo is how you output something to the page while in php mode

    <?php echo 2+2 ?>

<div id='id-semi'/>

## Semi-colon
A semi-colon tells php that we're done with the current task and ready to move on to a new task.

    <?php echo 2+2; ?>

<div id='id-variable'/>

## Variable 

### Creating a variable
A $ is how you create a variable. 

    <?php echo 2+2; 
    $myname='Brad';
     ?>

### Referencing a variable:

Reference a variable like this:

    <?php echo $myname ?>

<div id='id-function'/>

## Function 

### Defining a Function

To define a function, write function + a name for the function.

    <?php
        function myFirstFunction() {
        echo "<p>Hello, this is my first function.</p>";
    }
    ?>

### Calling a Function
Call a function like this (must be writing in php mode):

    myFirstFunction();

All together it'll look like this:

    <?php
        function myFirstFunction() {
        echo "<p>Hello, this is my first function.</p>";
    }

    myFirstFunction();
    ?>

You can call a function multiple times, and you only have to define it once.





