# Less Basic Tutorial

##  Less - Home

LESS is a CSS pre-processor that enables customizable, manageable and reusable style sheet for website.

LESS is a dynamic style sheet language that extends the capability of CSS.

LESS is also cross browser friendly.

## Less - Overview

CSS Preprocessor is a scripting language that extends CSS and gets compiled into regular CSS syntax, so that it can be read by your web browser.

It provides functionalities like *variables*, *functions*, *mixins* and *operations* that allow you to build dynamic CSS.

### Why LESS?

Let us now understand why do we use LESS.

- LESS supports creating cleaner, cross-browser friendly CSS faster and easier.
- LESS is designed in JavaScript and also created to be used in *live*, which compiles faster than other CSS pre-processors.
- LESS keeps your code in modular way which is really important by making it readable and easily changeable.
- Faster maintenance can be achieved by the use of LESS *variables*.

### History

LESS was designed by **Alexis Sellier** in 2009. 

LESS is an open-source. The first version of LESS was written in Ruby; in the later versions, the use of Ruby was replaced by JavaScript.

### Features

- Cleaner and more readable code can be written in an organized way.
- We can define styles and it can be reused throughout the code.
- LESS is based on JavaScript and is a super set of CSS.
- LESS is an agile tool that sorts out the problem of code redundancy.

### Advantages

- LESS easily generates CSS that works across the browsers.
- LESS enables you to write better and well-organized code by using *nesting*.
- Maintenance can be achieved faster by the use of *variables*.
- LESS enables you to reuse the whole classes easily by referencing them in your rule sets.
- LESS provides the use of *operations* that makes coding faster and saves time.

### Disadvantages

- It takes time to learn if you are new to CSS preprocessing.
- Due to the tight coupling between the modules, more efforts should be taken to reuse and/or test dependent modules.
- LESS has less framework compared to older preprocessor like SASS, which consists of frameworks *Compass*, *Gravity* and *Susy*.

## Less - Installation

### Installation steps

1. install **NodeJs** 
2. Install **LESS** using npm :`npm install -g less`
3. `lessc -v`

### basic demo

**hello.html**

```html
<!doctype html>
   <head>
      <link rel = "stylesheet" href = "style.css" type = "text/css" />
   </head>
   
   <body>
      <h1>Welcome to TutorialsPoint</h1>
      <h3>Hello!!!!!</h3>
   </body>
</html>
```

**style.less**

```less
@primarycolor: #FF7F50;
@color:#800080;
h1 {
   color: @primarycolor;
}

h3 {
   color: @color;
}
```

Compile **style.less** file to **style.css** by using the following command −

```
lessc style.less style.css
```

When you run the above command, it will create the *style.css* file automatically. 

Whenever you change the LESS file, it's necessary to run the above command in the **cmd** and then the *style.css* file will get updated.

**style.css**

```css
h1 {
  color: #FF7F50;
}

h3 {
  color: #800080;
}
```

**Output**

Let us now carry out the following steps to see how the above code works −

- Save code `index.html`, `style.less`, and generate `style.css`.
- Open this HTML file in a browser, the following output will get displayed.

# Language Feature

## LESS - Nested Rules

**Description**

It is a group of CSS properties which allows using properties of one class into another class and includes the class name as its properties. 

In LESS, you can declare **mixin** in the same way as CSS style using class or id selector. 

It can store multiple values and can be reused in the code whenever necessary.

**Example**

index.html

```html
<html>
   <head>
      <title>Nested Rules</title>
      <link rel = "stylesheet" type = "text/css" href = "style.css" />
   </head>
   
   <body>
      <div class = "container">
         <h1>First Heading</h1>
         <p>LESS is a dynamic style sheet language that extends the capability of CSS.</p>
         <div class = "myclass">
            <h1>Second Heading</h1>
            <p>LESS enables customizable, manageable and reusable style sheet for web site.</p>
         </div>
      </div>
   </body>
</html>
```

style.less

```less
.container {
   h1 {
      font-size: 25px;
      color:#E45456;
   }
   p {
      font-size: 25px;
      color:#3C7949;
   }

   .myclass {
      h1 {
         font-size: 25px;
         color:#E45456;
      }
      p {
         font-size: 25px;
         color:#3C7949;
      }
   }
}
```

compile the *style.less* file to *style.css*

```
lessc style.less style.css
```

check the output of index.html in browser.



## LESS - Nested Directives and Bubbling

**Description**

You can nest the directives such as **media** and **keyframe** in the same manner, the way you nest the selectors. 

You can place the directive on top and its relative elements will not be changed inside its rule set. This is known as the bubbling process.

**Example**

index.html

```html
<html>
   <head>
      <title>Nested Directives</title>
      <link rel = "stylesheet" type = "text/css" href = "style.css" />
   </head>
   
   <body>
      <h1>Example using Nested Directives</h1>
      <p class = "myclass">LESS enables customizable, 
      manageable and reusable style sheet for web site.</p>
   </body>
</html>
```

style.less

```less
.myclass {
   @media screen {
      color: blue;
      @media (min-width: 1024px) {
         color: green;
      }
   }
   @media mytext {
      color: black;
   }
}
```

compile the *style.less* file to *style.css*

```
lessc style.less style.css
```

style.css

```css
@media screen {
   .myclass {
      color: blue;
   }
}
@media screen and (min-width: 1024px) {
   .myclass {
      color: green;
   }
}
@media mytext {
   .myclass {
      color: black;
   }
}
```

check the output of index.html in browser.



## LESS - Operations

**Description**

LESS provides support for some arithmetical operations such as plus (+), minus (-), multiplication (*) and division (/) and they can operate on any number, color or variable. 

Operations save lot of time when you are using variables and you feel like working on simple mathematics.

**Example**

index.html

```html
<html>
   <head>
      <title>Less Operations</title>
      <link rel = "stylesheet" type = "text/css" href = "style.css" />
   </head>
   
   <body>
      <h1>Example using Operations</h1>
      <p class = "myclass">LESS enables customizable, 
      manageable and reusable style sheet for web site.</p>
   </body>
</html>
```

style.less

```less
@fontSize: 10px;
.myclass {
   font-size: @fontSize * 2;
   color:green;
}
```

compile the *style.less* file to *style.css*

```
lessc style.less style.css
```

style.css

```css
.myclass {
   font-size: 20px;
   color: green;
}
```

check the output of index.html in browser.



## LESS - Escaping

**Description**

It builds selectors dynamically and uses property or variable value as arbitrary string.

**Example**

index.html

```html
<html>
   <head>
      <title>Less Escaping</title>
      <link rel = "stylesheet" type = "text/css" href = "style.css" />
   </head>
   
   <body>
      <h1>Example using Escaping</h1>
      <p>LESS enables customizable, manageable and reusable style sheet for web site.</p>
   </body>
</html>
```

style.less

```less
p {
   color: ~"green";
}
```

compile the *style.less* file to *style.css*

```
lessc style.less style.css
```

style.css

```css
p {
   color: green;
}
```

Anything written inside ***~"some_text"*** will be displayed as *some_text* after compiling the LESS code to CSS code.



check the output of index.html in browser.



## LESS - Functions

**Description**

LESS maps JavaScript code with manipulation of values and uses predefined functions to manipulate HTML elements aspects in the style sheet.

 It provides several functions to manipulate colors such as round function, floor function, ceil function, percentage function etc.

**Example**

index.html

```html
<html>
   <head>
      <title>Less Functions</title>
      <link rel = "stylesheet" type = "text/css" href = "style.css" />
   </head>
   
   <body>
      <h1>Example using Functions</h1>
      <p class = "mycolor">LESS enables customizable, 
      manageable and reusable style sheet for web site.</p>
   </body>
</html>
```

style.less

```less
@color: #FF8000;
@width:1.0;
.mycolor {
   color: @color;
   width: percentage(@width);
}
```

compile the *style.less* file to *style.css*

```
lessc style.less style.css
```

style.css

```css
.mycolor {
   color: #FF8000;
   width: 100%;
}
```

check the output of index.html in browser.



## LESS - Namespaces and Accessors

**Description**

Namespaces are used to group the mixins under a common name.

Using namespaces, you can avoid conflict in name and encapsulate a group of mixins from outside.

**Example**

index.html

```html
<html>
   <head>
      <title>Less Namespaces and Accessors</title>
      <link rel = "stylesheet" type = "text/css" href = "style.css" />
   </head>
   
   <body>
      <h1>Example using Namespaces and Accessors</h1>
      <p class = "myclass">LESS enables customizable, 
      manageable and reusable style sheet for web site.</p>
   </body>
</html>
```

style.less

```less
.class1 {
   .class2 {
      .val(@param) {
         font-size: @param;
         color:green;
      }
   }
}

.myclass {
   .class1 > .class2 > .val(20px);
}
```

compile the *style.less* file to *style.css*

```
lessc style.less style.css
```

style.css

```css
.myclass {
   font-size: 20px;
   color: green;
}
```

check the output of index.html in browser.



## LESS - Scope

**Description**

Variable scope specifies the place of the available variable.

 The variables will be searched from the local scope and if they are not available, then compiler will search from the parent scope.

**Example**

index.html

```html
<html>
   <head>
      <title>Less Scope</title>
      <link rel = "stylesheet" type = "text/css" href = "style.css" />
   </head>
   
   <body>
      <h1>Example using Scope</h1>
      <p class = "myclass">LESS enables customizable, 
      manageable and reusable style sheet for web site.</p>
   </body>
</html>
```

style.less

```less
@var: @a;
@a: 15px;

.myclass {
   font-size: @var;
   @a:20px;
   color: green;
}
```

compile the *style.less* file to *style.css*

```
lessc style.less style.css
```

style.css

```css
.myclass {
   font-size: 20px;
   color: green;
}
```

check the output of index.html in browser.



## LESS - Comments

**Description**

Comments make the code clear and understandable for the users. 

You can use both the block style and the inline comments in the code, but when you compile the LESS code, the single line comments will not appear in the CSS file.

**Example**

index.html

```html
<html>
   <head>
      <title>Less Comments</title>
      <link rel = "stylesheet" type = "text/css" href = "style.css" />
   </head>

   <body>
      <h1>Example using Comments</h1>
      <p class = "myclass">LESS enables customizable, 
      manageable and reusable style sheet for web site.</p>
      <p class = "myclass1">It allows reusing CSS code and 
      writing LESS code with same semantics.</p>
   </body>
</html>
```

style.less

```less
/* It displays the
green color! */
.myclass {
   color: green;
}

// It displays the blue color
.myclass1 {
   color: red;
}
```

compile the *style.less* file to *style.css*

```
lessc style.less style.css
```

style.css

```css
/* It displays the
green color! */
.myclass {
   color: green;
}

.myclass1 {
   color: red;
}
```

check the output of index.html in browser.



## LESS - Importing

**Description**

It is used to import the contents of the LESS or CSS files.

**Example**

index.html

```html
<html>
   <head>
      <title>Less Importing</title>
      <link rel = "stylesheet" type = "text/css" href = "style.css" />
   </head>

   <body>
      <h1>Example using Importing</h1>
      <p class = "myclass">LESS enables customizable, 
      manageable and reusable style sheet for web site.</p>
      <p class = "myclass1">It allows reusing CSS code and 
      writing LESS code with same semantics.</p>
      <p class = "myclass2">LESS supports creating cleaner, 
      cross-browser friendly CSS faster and easier.</p>
   </body>
</html>
```

file/myfile.less

```
.myclass {
   color: #FF8000;
}

.myclass1 {
   color: #5882FA;
}
```

style.less

```less
// @import "file/myfile.less";
@import url('file/myfile.less');

.myclass2 {
  color: #FF0000;
}
```

compile the *style.less* file to *style.css*

```
lessc style.less style.css
```

The *myfile.less* file which will be imported into *style.less* from the path `https://www.tutorialspoint.com/less/myfile.less`

style.css

```css
.myclass {
   color: #FF8000;
}

.myclass1 {
   color: #5882FA;
}

.myclass2 {
   color: #FF0000;
}
```

check the output of index.html in browser.

## LESS-Variables-*

In this chapter, we will discuss the Variables in LESS.

 LESS allows *variables* to be defined with an `@` symbol. 

The *Variable* assignment is done with a **colon(:)**.

### Variable Overview

**Description**

Repetition of the same value many times is usually seen across your stylesheet. 

Instead of using the same value multiple times, *variables* can be used. 

It makes maintenance of code easier and those values can be controlled from single location.

**Example**

index.html

```html
<html>
   <head>
     <link rel = "stylesheet" href = "style.css" type = "text/css" />
     <title>LESS variables overview</title>
   </head>

   <body>
      <h1>Welcome to Tutorialspoint</h1>
      <div class = "div1">
         <p>LESS is a CSS pre-processor that enables customizable, 
            manageable and reusable style sheet for web site.</p>
      </div>
         
      <div class = "div2">
         <p>LESS is a dynamic style sheet language that extends the capability of CSS. 
            LESS is also cross browser friendly.</p>
      </div>
   </body>
</html>
```

style.less

```less
@color1: #ca428b;
.div1 {
   background-color : @color1;
}

.div2 {
   background-color : @color1;
}
```

compile the *style.less* file to *style.css*

```
lessc style.less style.css
```

style.css

```css
h1 {
   color: #D0DC11;
}

.div1 {
   background-color: #ca428b;
   color: #D0DC11;
}

.div2 {
   background-color: #ca428b;
   color: #D0DC11;
}
```

check the output of index.html in browser.

### Variable interpolation

**Description**

The variable interpolation is the process of evaluating an expression or literal containing one or more variables, yielding output in which the variables are replaced with their corresponding values. 

The variables can also be used in other places like *selector names*, *property names*, *URL*s and *@import* statements.

#### Selectors

**Description**

The selector can reference any variable and it is built during the compile time. 

The variable name must be placed inside the curly braces( **{ }** ) prefixed with the **@** symbol.

**Example**

index.html

```html
<html>
   <head>
      <link rel = "stylesheet" href = "style.css" type = "text/css" />
      <title>LESS selectors</title>
   </head>
	
   <body>
      <h2>Welcome to Tutorialspoint</h2>
         
      <div class = "div1">
         <p>LESS is a CSS pre-processor that enables customizable, 
            manageable and reusable style sheet for web site.</p>
      </div>
      
      <div class = "div2">
         <p>LESS is a dynamic style sheet language that extends the capability of CSS. 
            LESS is also cross browser friendly.</p>
      </div>
   </body>
	
</html>
```

style.less

```less
@selector: h2;

@{selector} {
   background: #2ECCFA;
}
```

compile the *style.less* file to *style.css*

```
lessc style.less style.css
```

style.css

```css
h2 {
   background: #2ECCFA;
}
```

check the output of index.html in browser.



#### URLs

**Description**

The variables can be used to hold the URLs.

**Example**

index.html

```html
<html>
   <head>
      <link rel = "stylesheet" href = "style.css" type = "text/css" />
      <title>LESS URLs</title>
   </head>

   <body>
      <div class = "myclass">
      </div>
   </body>
</html>
```

style.less

```less
@images: "http://www.tutorialspoint.com";

.myclass {
   background : url("@{images}/less/images/less_variables/birds.jpg");
   width:800px;
   height:500px;
}
```

compile the *style.less* file to *style.css*

```
lessc style.less style.css
```

style.css

```css
.myclass {
   background: url("http://www.tutorialspoint.com/less/images/less_variables/birds.jpg");
   width: 800px;
   height: 500px;
}
```

check the output of index.html in browser.



#### Import Statements

**Description**

An import statement can have a variable which holds a path. 

This is very useful when you are referring a common parent directory.

**Example**

index.html

```html
<html>
   <head>
      <link rel = "stylesheet" href = "style.css" type = "text/css" />
      <title>LESS Variables in Import Statements</title>
   </head>

   <body>
      <div class = "myclass">
         <h2>Welcome to Tutorialspoint</h2>
         <p>LESS is a CSS pre-processor that enables customizable, 
         manageable and reusable style sheet for web site.</p>
      </div>
   </body>
</html>
```

./file/myfile.less

```
.myclass {
  background-color: #C0C0C0;
}
```

style.less

```less
@path: "./file";
@import "@{path}/myfile.less";
.myclass {
  color: #A52A2A;
}
```

compile the *style.less* file to *style.css*

```
lessc style.less style.css
```

The following code will import the *external.less* file into *style.less* from the https://www.tutorialspoint.com/less/external1.less path −

style.css

```css
.myclass {
  background-color: #C0C0C0;
}
.myclass {
  color: #A52A2A;
}
```

check the output of index.html in browser.



#### Properties

**Description**

The variables can be referenced by properties.

**Example**

index.html

```html
<html>
   <head>
      <link rel = "stylesheet" href = "style.css" type = "text/css" />
      <title>LESS Variables Interpolation Properties</title>
   </head>

   <body>
      <div class = "myclass">
         <h2>Welcome to Tutorialspoint</h2>
         <p>LESS is a CSS pre-processor that enables customizable, 
         manageable and reusable style sheet for web site.</p>
      </div>
   </body>
</html>
```

style.less

```less
@my-property: color;
.myclass {
   background-@{my-property}: #81F7D8;
}
```

compile the *style.less* file to *style.css*

```
lessc style.less style.css
```

The following code will import the *external.less* file into *style.less* from the https://www.tutorialspoint.com/less/external1.less path −

style.css

```css
.myclass {
   background-color: #81F7D8;
}
```

check the output of index.html in browser.



### Variable Names

**Description**

We can define the variables with a variable name consisting of a value.

**Example**

index.html

```html
<html>
   <head>
      <link rel = "stylesheet" href = "style.css" type = "text/css" />
      <title>LESS Variable Names</title>
   </head>

   <body>
      <div class = "myclass">
         <h2>Welcome to Tutorialspoint</h2>
         <p>LESS is a CSS pre-processor that enables customizable, 
         manageable and reusable style sheet for web site.</p>
      </div>
   </body>
</html>
```

style.less

```less
.myclass {
   @col: #ca428b;
   @color: "col";
   background-color: @@color;
}
```

compile the *style.less* file to *style.css*

```
lessc style.less style.css
```

The following code will import the *external.less* file into *style.less* from the https://www.tutorialspoint.com/less/external1.less path −

style.css

```css
myclass {
   background-color: #ca428b;
}
```

check the output of index.html in browser.



### Variable Lazy Loading

**Description**

In lazy loading, variables can be used even when they are not declared.

**Example**

index.html

```html
<html>
   <head>
      <link rel = "stylesheet" href = "style.css" type = "text/css" />
      <title>LESS Lazy Loading</title>
   </head>

   <body>
      <h2>Welcome to Tutorialspoint</h2>
      <p>LESS is a CSS pre-processor.</p>
   </body>
</html>
```

style.less

```less
p {
   font-size: @a;
   color: #ca428b;
}
@a: @b;
@b: 25px;
```

compile the *style.less* file to *style.css*

```
lessc style.less style.css
```

The following code will import the *external.less* file into *style.less* from the https://www.tutorialspoint.com/less/external1.less path −

style.css

```css
p {
   font-size: 25px;
   color: #ca428b;
}
```

check the output of index.html in browser.



### Variable Default Variables

**Description**

Default variable has an ability to set a variable only when it's not already set. 

This feature is not required because variables can be easily overridden by defining them afterwards.

**Example**

index.html

```html
<html>
   <head>
      <link rel = "stylesheet" href = "style.css" type = "text/css" />
      <title>LESS Default Variables</title>
   </head>

   <body>
      <h1>Welcome to Tutorialspoint</h1>
      <p>LESS is a CSS pre-processor that enables customizable, 
      manageable and reusable style sheet for web site.</p>
   </body>
</html>
```

style.less

```less
@import "http://www.tutorialspoint.com/less/lib.less"; // first declaration of @color
@color: green; // this will override @color defined previously
p {
   color : @color;
}
```

compile the *style.less* file to *style.css*

```
lessc style.less style.css
```

The following code will import the *external.less* file into *style.less* from the https://www.tutorialspoint.com/less/external1.less path −

style.css

```css
p {
   color: green;
}
```

check the output of index.html in browser.

## LESS - Extend

**Description**

Extend is a LESS pseudo class which extends other selector styles in one selector by using **:extend** selector.

**Example**

index.html

```html
<!doctype html>
   <head>
      <link rel = "stylesheet" href = "style.css" type = "text/css" />
   </head>

   <body>
      <div class = "style">
         <h2>Welcome to TutorialsPoint</h2>
         <p>Hello!!!!!</p>
      </div>
   </body>
</html>
```

style.less

```less
h2 {
   &:extend(.style);
   font-style: italic;
}

.style {
   background: green;
}
```

compile the *style.less* file to *style.css*

```
lessc style.less style.css
```

style.css

```css
h2 {
  font-style: italic;
}
.style,
h2 {
  background: green;
}
```

check the output of index.html in browser.



### Extend Syntax

**Description**

Extend is placed into ruleset or attached to a selector.

It is similar to a pseudo class containing one or more classes, which are separated by comma. Using the optional keyword **all**, each selector can be followed.

**Example**

index.html

```html
<!doctype html>
   <head>
      <link rel = "stylesheet" href = "style.css" type = "text/css" />
   </head>

   <body>
      <div class = "style">
         <h2>Welcome to TutorialsPoint</h2>
         
         <div class = "container">
            <p>Hello!!!!!</p>
         </div>
      
      </div>
   </body>
</html>
```

style.less

```less
.style:extend(.container, .img) {
   background: #BF70A5;
}

.container {
   font-style: italic;
}

.img {
   font-size: 30px;
}
```

compile the *style.less* file to *style.css*

```
lessc style.less style.css
```

style.css

```css
.style {
   background: #BF70A5;
}

.container,
.style {
   font-style: italic;
}

.img,
.style {
   font-size: 30px;
}
```

check the output of index.html in browser.