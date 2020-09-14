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

## Less - Nested Rules

### Description

It is a group of CSS properties which allows using properties of one class into another class and includes the class name as its properties. 

In LESS, you can declare **mixin** in the same way as CSS style using class or id selector. 

It can store multiple values and can be reused in the code whenever necessary.

### Example

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

### Description

You can nest the directives such as **media** and **keyframe** in the same manner, the way you nest the selectors. 

You can place the directive on top and its relative elements will not be changed inside its rule set. This is known as the bubbling process.

### Example

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

### Description

LESS provides support for some arithmetical operations such as plus (+), minus (-), multiplication (*) and division (/) and they can operate on any number, color or variable. 

Operations save lot of time when you are using variables and you feel like working on simple mathematics.

### Example

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

### Description

It builds selectors dynamically and uses property or variable value as arbitrary string.

### Example

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

### Description

LESS maps JavaScript code with manipulation of values and uses predefined functions to manipulate HTML elements aspects in the style sheet.

 It provides several functions to manipulate colors such as round function, floor function, ceil function, percentage function etc.

### Example

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

### Description

Namespaces are used to group the mixins under a common name.

Using namespaces, you can avoid conflict in name and encapsulate a group of mixins from outside.

### Example

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

### Description

Variable scope specifies the place of the available variable.

 The variables will be searched from the local scope and if they are not available, then compiler will search from the parent scope.

### Example

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