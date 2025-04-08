# HTML Basics

## Html is tags + content
We make content into html elements using opening and closing tags.

## Boilerplate
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <title>HTML 5 Boilerplate</title>
            <link rel="stylesheet" href="style.css">
        </head>
        <body>
        </body>
    </html>

### DOCTYPE
Tells the browser what version of html the page is written in.

    <!DOCTYPE html>

### HTML Root Element
The top level element of the file. Other tags nested inside. Lang attribuse sets the language for the page (good for accessibility).

    <html lang="en">

### Head
Contains
* meta info
* scripts we want to load before the page does
* stylesheets

### Meta Tags

#### UTF-8 character encoding
Can support many languages, and pages + forms in any mixture of those languages. 

Eliminates the need for server-side logic to individually determine the character encoding for each page served or each incoming form submission.

    <meta charset="UTF-8">

#### Viewport Meta Tag
Renders the width of the page to the width of the device's screen size. 

The initial-scale controls the zoom level. The value of 1 for the initial-scale prevents the default zoom by browsers.

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

### Title Tag
This text is shown in the browser's title bar.

    <title>HTML 5 Boilerplate</title>

### CSS stylesheet
Defines the relationship between the HTML file and the external stylesheet.

    <link rel="stylesheet" href="style.css">

### Script Tags
This is where you can link your external JavaScript code.

    <script src="index.js"></script>

### Body
Contains
* Elements we want to appear on the page
* Content

## HTML Elements

### 6 Headers
    <h1></h1>
    <h2></h2>
    <h3></h3>
    <h4></h4>
    <h5></h5>
    <h6></h6>

### Paragraph Elements
Used to separate long-form text content
    
    <p></p> 

    

### Text Elements
Used to modify existing text, but you can also use css to do this.
    <u></u>
    <strong></strong>
    <i></i>

## Attributes
Can modify your elements or add properties to them. They go inside the opening tag.

### Global attributes

#### Class
Lets you style an element or select with javascript later on, when you add css/javascript. Can apply multiple classes with a space
    
    <h1 class="title"></h1>

    <h1 class="title primary"></h1>


### Element-specific attributes
Image tags are examples of this. <img> tags require an src attribute to work, can also have alt, width attributes etc.

    <img src="">

#### Anchor tags
Links

    <a href=""></a>

#### Ordered and Unordered lists
    
    <ol>
        <li></li>
        <li></li>
        <li></li>
    </ol>
    <ul>
        <li></li>
        <li></li>
        <li></li>
    </ul>

#### Button elements
    
    <button></button>

#### Forms
Wrap the form tag around one or more input elements

    <form>
        <p>Text</p>
        <input type="text">
        <p>Email</p>
        <input type="email">
        <p>Password</p>
        <input type="password">
        <p>Checkbox</p>
        <input type="checkbox">
        <p>Radio</p>
        <input type="radio">
        <p>Select</p>
        <select>
            <option>Seventh</option>
            <option>Eight</option>
            <option>Ninth</option>
        </select>
    </form>

To link a label to an input element, use a 'for' attribute on the label. Clicking the label will then activate the input.

    <label for="cb1">First</label>
    <input type="checkbox" id="cb1">

 Submit action trigger: a button 
    
    <button type="submit">Submit</button>

For form submission, add the action attribute to the form tag, and name attributes to the individual inputs. this will put their values in the url when you submit.
    
    <form action="submit.html"></form>
    <p>Radio</p>
    <input type="radio" id="cb2" name="cb2">

Other attributes for inputs.

    <disabled></disabled>
    <autofocus></autofocus>
    <required></required>

### Container elements
You can put stuff inside a div or span, and then style or select this container.

    <div></div>
    <span></span>

Spans are for inline text, Divs are for sections

### Style and Script tags

#### Style
CSS can be written here

    <style></style>

#### Script
Javascript can be written here.

    <Script></Script>


### Semantic html
An anti-div movement

    Instead of using a bunch of <div> tags, use more descriptive tags like <header> <nav> <article> <figure> <footer>

## Comments

    <!-- This is a comment -->

Comments are used to help document your code (placing notes and explainations in your HTML).

