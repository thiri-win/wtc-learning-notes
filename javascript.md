- [What is JavaScript](#what-is-javascript)
- [Variables](#variables)
- [Data Types](#data-types)
  - [primitive data types:](#primitive-data-types)
  - [complex data types:](#complex-data-types)
- [Number](#number)
- [Boolean](#boolean)
- [String](#string)
  - [String Properties](#string-properties)
  - [String Methods](#string-methods)
- [Objects](#objects)
  - [Object Properties](#object-properties)
  - [Object Methods](#object-methods)
  - [how to create an object](#how-to-create-an-object)
  - [Accessing properties](#accessing-properties)
  - [Modifying the value of a property](#modifying-the-value-of-a-property)
  - [Adding a new property to an object](#adding-a-new-property-to-an-object)
  - [Deleting a property of an object](#deleting-a-property-of-an-object)
  - [Checking if a property exists](#checking-if-a-property-exists)
  - [Summary](#summary)
- [Arrays](#arrays)
  - [Creating JavaScript arrays](#creating-javascript-arrays)
  - [Accessing JavaScript array elements](#accessing-javascript-array-elements)
  - [Array properties](#array-properties)
  - [Array Methods](#array-methods)
  - [Array Destructuring](#array-destructuring)
  - [Spread Operator](#spread-operator)
- [Operator](#operator)
  - [Arithmetic Operator](#arithmetic-operator)
  - [Comparison Operator](#comparison-operator)
  - [logical operator](#logical-operator)
  - [Assignment Operator](#assignment-operator)
  - [conditional operator](#conditional-operator)
- [Control Flow](#control-flow)
- [Function](#function)
  - [anonymous function](#anonymous-function)
  - [arrow function](#arrow-function)
- [Document Object Model](#document-object-model)
  - [Selecting Elements](#selecting-elements)
  - [Travesing Elements](#travesing-elements)
  - [Manipulating Elements](#manipulating-elements)
  - [Events](#events)
- [Browser Object Model](#browser-object-model)
  - [window](#window)
  - [navigator](#navigator)

What is JavaScript
==================

*   JavaScript is a programming language initially designed to interact with elements of web pages. In web browsers, JavaScript consists of three main parts:
*   ECMAScript provides the core functionality.
*   The Document Object Model (DOM) provides interfaces for interacting with elements on web pages
*   The Browser Object Model (BOM) provides the browser API for interacting with the web browser.

Variables
=========

*   A variable is a label that references a value like a number or string. Before using a variable, you need to declare it.
*   declare a variable: To declare a variable, you use the var keyword followed by the variable name as follows: `var temp;`
*   Initialize a variable: To initialize a variable, you specify the variable name, followed by an equal sign (=) and a value: `var temp = 100;`
*   Change a variable: Once you initialize a variable, you can change its value by assigning a different value. For example: `var temp = 150;`
*   `var` and `let` create variables that can be reassigned another value.
*   `const` creates "constant" variables that cannot be reassigned another value.
*   An undefined variable is a variable that has been declared but not initialized while an undeclared variable is variable that has not been declared.
*   Use the const keyword to define a readonly reference to a value.
*   A constant holds a value that doesn't change.
*   To declare a constant, you use the const keyword. When defining a constant, you need to initialize it with a value. For example: `const number = 10;`

Data Types
==========

JavaScript is a dynamically typed language. It means that a variable doesn't associate with a type. In other words, a variable can hold a value of different types. For example:

primitive data types:
---------------------

*   number
*   boolean
*   undefined
*   null
*   string

complex data types:
-------------------

*   object

Number
======

*   JavaScript uses the number type to represent both integers and floating-point values.
*   Technically, the JavaScript number type uses the IEEE-754 format.
*   decimal integer: let number = 100; // 100
*   octal numbers: let number = 071 // 57
*   hexadecimal number: let number = 0X1a; // 26
*   floating numbers: let number = 0.99 // 0.99
*   big number: let number = 3.14e7; // 31400000
*   small number: let number = 5e-7; // 0.0000005
*   big integer: JavaScript introduced the bigint type starting in ES2022. The bigint type stores whole numbers whose values are greater than 253 - 1.
*   A big integer literal has the n character at the end of an integer literal like this:
*   big integer: let views = 9007199254740991n;
*   you can declare a variable that holds number as follows:
*   let number = new Number(100);
*   let number = 200
*   number properties:
*   MAX\_VALUE : Number.MAX\_VALUE // 1.7976931348623157e+308
*   MIN\_VALUE: Number.MIN\_VALUE //5e-324
*   Number.POSITIVE\_INFINITY // Infinity
*   Number.NEGATIVE\_INFINITY // -Infinity
*   number methods:
*   toExponential()
*   toFixed()
*   toLocaleString()
*   toPrecision()
*   toString()
*   valueOf()
*   numeric separator: The numeric separator allows you to create a visual separation between groups of digits by using underscores (\_) as separators.
*   const amount = 1\_000\_000\_000;
*   JavaScript allows you to use numeric separators for both integer and floating-point numbers.
*   Use underscores (\_) as the numeric separators to create a visual separation between groups of digits.

Boolean
=======

*   **Boolean primitive type:** JavaScript provides a Boolean primitive type that has two values of true and false.
*   **Boolean object:** In addition to the boolean primitive type, JavaScript also provides you with the global Boolean() function, with the letter B in uppercase, to cast a value of another type to boolean.
```javascript
    let a = Boolean('Hi');
    console.log(a); //true
    console.log(typeof(a)); // boolean
```
*   The Boolean is also a wrapper object of the Boolean primitive type. It means that when you pass either true or false to the Boolean constructor, it'll create a Boolean object.
*   To get the primitive value back, you call the valueOf() method of the Boolean object.
```javascript
    let b = new Boolean(false);
    console.log(b.valueOf()); //false
```

String
======

*   Syntax : `var val = new String(string);`
*   JavaScript strings are primitive values. Also, strings are immutable. It means that if you modify a string, you will always get a new string. The original string doesn't change.
*   To create literal strings, you use either single quotes (') or double quotes (") like this:
```javascript
    let str = "Hi";
    let greeting = "Hello";
```
*   ES6 introduced template literals that allow you to define a string backtick (\`) characters:
```javascript
    let name = `John`;
```
*   The template literals allow you to use the single quotes and double quotes inside a string without the need of escaping them.
```javascript
    let message = `"I'm good". She said"`;
```
*   Also, you can place the variables and expressions inside a template literal. JavaScript will replace the variables with their value in the string. This is called string interpolation. For example:
```javascript
    let name = 'John';
    let message = `Hi, I'm ${name}`;
    console.log(message); // Hi, I'm John
```
*   Escaping special characters: To escape special characters, you use the backslash `\` character. For example:
*   Windows line break: `'\r\n'`
*   Unix line break: `'\n'`
*   Tab: `'\t'`
*   Backslash `'\'`
*   Concatenating strings via `"+"` operator: To concatenate two or more strings,you use the `+` operator:
```javascript
    let name = "John";
    let str = 'Hello' + name;
    console.log(str); // "Hello John"
```
*   If you want to assemble a string piece by piece, you can use the `+=` operator:
```javascript
    let className = 'btn';
    className += ' btn-primary';
    className += ' none';
    console.log(className); // btn btn-primary none
```
*   Comparing strings : To compare two strings, you use comparison operators such as `>`, `>=`, `<`, `<=`, and `==` operators.
*   The comparison operators compare strings based on the numeric values of the characters. And it may return the string order that is different from the one used in dictionaries.
```javascript
    let result = 'a' < 'b';
    console.log(result); // true
    let result = 'a' < 'B';
    console.log(result); // false
``` 
String Properties
-----------------

*   string.length
*   string\[0\]

String Methods
--------------

*   charAt()
*   concat()
*   indexOf()
*   lastIndexOf()
*   match()
*   search()
*   slice()
*   split()
*   substr()
*   substring()
*   toLowerCase()
*   toUpperCase()
*   valueOf()
*   trim()
*   trimStart()
*   trimEnd()
*   replace()
*   replaceAll()
*   startsWith()
*   endsWith()
*   toString(): Note that the toString() method doesn't work for undefined and null.

Objects
=======

*   JavaScript is an Object Oriented Programming (OOP) language. A programming language can be called object-oriented if it provides four basic capabilities to developers -
*   **Encapsulation** - the capability to store related information, whether data or methods, together in an object.
*   **Aggregation** - the capability to store one object inside another object.
*   **Inheritance** - the capability of a class to rely upon another class (or number of classes) for some of its properties and methods.
*   **Polymorphism** - the capability to write one function or method that works in a variety of different ways.
*   Objects are composed of attributes. If an attribute contains a function, it is considered to be a method of the object, otherwise the attribute is considered a property.

Object Properties
-----------------

*   Object properties can be any of the three primitive data types, or any of the abstract data types, such as another object.
*   Object properties are usually variables that are used internally in the object's methods, but can also be globally visible variables that are used throughout the page.
*   In JavaScript, an object is an unordered collection of key-value pairs. Each key-value pair is called a property.
*   The key of a property can be a string. And the value of a property can be any value, e.g., a string, a number, an array, and even a function.

Object Methods
--------------

*   Methods are the functions that let the object do something or let something be done to it.
*   There is a small difference between a function and a method - at a function is a standalone unit of statements and a method is attached to an object and can be referenced by this keyword.
*   Methods are useful for everything from displaying the contents of the object to the screen to performing complex mathematical operations on a group of local properties and parameters.

how to create an object
-----------------------

*   syntax
```javascript
    let book = new Object();
```
*   JavaScript provides you with many ways to create an object. The most commonly used one is to use the object literal notation.
```javascript
    let empty = {};
``` 
*   To create an object with properties, you use the key:value within the curly braces.
*   The person object has two properties firstName and lastName with the corresponding values 'John' and 'Doe'.
*   When an object has multiple properties, you use a comma (,).
```javascript
    let person = {
        firstName: "John",
        lastName: "Doe",
        }
```

Accessing properties
--------------------

*   To access a property of an object, you use one of two notations: the dot notation and array-like notation.
*   The dot notation( . )
```javascript
    // objectName.propertyName
    console.log(person.firstName);
    console.log(person.lastName);
```
*   Array-like notation(\[\])
```javascript
    // objectName['propertyName']
    console.log(person['firstName']);
    console.log(person['lastName']);
```
*   When a property name contains spaces, you need to place it inside quotes. For example, the following address object has the 'building no' as a property:
*   To access the 'building no' property, you need to use the array-like notation:
*   If you use the dot notation, you'll get an error:
*   Note that it is not a good practice to use spaces in the property names of an object.
```javascript
    let address = {
        'buliding no' : 3960,
        street: 'North 1st stree',
        state: 'CA',
        country: 'USA'
    }
    console.log(address['building no']);
```
Modifying the value of a property
---------------------------------

*   To change the value of a property, you use the assignment operator (=).
*   we changed the value of the firstName property of the person object from 'John' to 'Jane'.
```javascript
    let person = {
        firstName: 'John',
        lastName:'Doe'
    };
    person.firstName ='Jane';
    console.log(person): // {firstName: 'Jane', lastName: 'Doe'}
```
Adding a new property to an object
----------------------------------

*   Unlike objects in other programming languages such as Java and C#, you can add a property to an object after object creation.
*   The following statement adds the age property to the person object and assigns 25 to it:
```javascript
    person.age = 25;
```
Deleting a property of an object
--------------------------------

*   To delete a property of an object, you use the delete operator:
*   If you attempt to reaccess the age property, you'll get an undefined value.
```javascript
    //delete objectName.propertyName;
    delete person.age;
```
Checking if a property exists
-----------------------------

*   To check if a property exists in an object, you use the in operator:
*   The in operator returns true if the propertyName exists in the objectName.
```javascript
    let employee = {
        firstName: 'Peter',
        lastName: 'Doe',
        employeeId:1
    };
    console.log('ssn' in employee); //false
    console.log('emplyeeId' in employee); //true
```
Summary
-------

*   An object is a collection of key-value pairs.
*   Use the dot notation ( . ) or array-like notation (\[ \]) to access a property of an object.
*   The delete operator removes a property from an object.
*   The in operator check if a property exists in an object.

Arrays
======

*   First, an array can hold values of mixed types. For example, you can have an array that stores elements with the types number, string, boolean, and null.
*   Second, the size of an array is dynamic and auto-growing. In other words, you don't need to specify the array size up front.
*   In JavaScript, an array is an ordered list of values. Each value is called an element specified by an index:
*   An array can hold values of mixed types.
*   JavaScript arrays are dynamic, which means that they grow or shrink as needed.

Creating JavaScript arrays
--------------------------

*   JavaScript provides you with two ways to create an array.
*   The first one is to use the Array constructor as follows:
*   let scores = new Array(9,10,8,7,6);
*   The more preferred way to create an array is to use the array literal notation:
*   let arrayName = \[element1, element2, element3, ...\];
*   The array literal form uses the square brackets \[\] to wrap a comma-separated list of elements.

Accessing JavaScript array elements
-----------------------------------

*   JavaScript arrays are zero-based indexed. In other words, the first element of an array starts at index 0, the second element starts at index 1, and so on.
*   To access an element in an array, you specify an index in the square brackets \[\]:

Array properties
----------------

*   To access an element in an array, you specify an index in the square brackets \[\]: arrayName\[index\]
*   To change the value of an element, you assign that value to the element like this:
```javascript
    let mountains = ['Everest', 'Fuji', 'Nanga Parbat'];
    mountains[2] = 'K2';
    console.log(mountains); //['Everest', 'Fuji', 'K2'];
```
*   Getting the array size : Typically, the length property of an array returns the number of elements. The following example shows how to use the length property:
```javascript
    console.log(mountains.length); //3
```
Array Methods
-------------

*   push()
*   unshift()
*   pop()
*   shift()
*   slice()
*   splice()
*   toString()
*   sort()
*   reverse()
*   indexOf()
*   includes()
*   find()
*   findIndex()
*   map()
*   filter()
*   reduce()
*   some()
*   sort()
*   forEach()
*   concat()
*   of()
*   join()
*   Array.isArray()

Array Destructuring
-------------------

*   Prior to ES6, there was no direct way to assign the elements of the returned array to multiple variables.
*   The variables x, y and z will take the values of the first, second, and third elements of the returned array.
*   Note that the square brackets \[\] look like the array syntax but they are not.
```javascript
    let [x,y,z] = [70, 80, 90];
    console.log(x); // 70
    console.log(y); // 80
    console.log(z); // 90
```
Spread Operator
---------------

*   ES6 provides a new operator called spread operator that consists of three dots (...). The spread operator allows you to spread out elements of an iterable object such as an array, map, or set.
```javascript
    const odd = [1, 3, 5];
    const combined = [...odd, 2, 4, 6];
    console.log(combined); // [1, 3, 5, 2, 4, 6];
```
Operator
========

Arithmetic Operator
-------------------
|operator|description|
|--------|-----------|
|+|addition|
|\-|substraction|
|\*|multiplication|
|/|division|
|%|modulus|
|++|increment|
|\--|decrement|

Comparison Operator
-------------------
|operator|description|
|--------|-----------|
|\==|equal|
|!=|not equal|
|\>|greater than|
|<|less than|
|\>=|greater than or equal|
|<=|less than or equal|

logical operator
----------------
|operator|description|
|--------|-----------|
|&&|and|
|\|\||or|
|!|not|

Assignment Operator
-------------------
|operator|description|
|--------|-----------|
|\=|assignment|
|+=|add and assign|
|\-=|substract and assign|
|\*=|multiplication and assign|
|/=|divide and assign|
|%=|modulus and assign|

conditional operator
--------------------
|operator|description|
|--------|-----------|
|? :|conditional|

Control Flow
============

*   The if statement executes block if a condition is true.
```javascript
    if(condition) {
        // statements to execute
    }
```
*   if...else statement to execute a block if a condition is true and another block otherwise.
```javascript
    if(condition) {
        // statements to execute
    } else {
        // statements to execute
    }
```
*   if...else...if statement is to check multiple conditions and execute the corresponding block if a condition is true.
```javascript
    if(condition 1) {
        // statements to execute
    } else if (condition 2) {
        // statements to execute
    } else if (condition 2) {
        // statements to execute
    } else {
        // statements to execute
    }
```
*   you can use a ternary operator instead of the if-else statement.
```javascript
    condition ? expressionIfTrue : expressionIfFalse`
```
*   The switch statement evaluates an expression, compares its result with case values, and executes the statement associated with the matching case value.
```javascript
    switch(expression) {
        case 1:
            // statement here;
            break;
        case 2:
            // statement here;
            break;
        case 3:
            // statement here;
            break;
        default:
            // statement here;
    }
```
*   The JavaScript while statement creates a loop that executes a block as long as a condition evaluates to true.
```javascript
    while(expression) {
        // statement;
    }`
```
*   The do...while loop statement creates a loop that executes a block until a condition evaluates to false.
```javascript
    do {
        // statement;
    } while(expression)
```
*   The for loop statement creates a loop with three optional expressions.
```javascript
    for(initializer; condition; iterator) {
        // statement here;
    }
```
*   The break statement prematurely terminates a loop such as for, do...while, and while loop, a switch, or a label statement.
*   The continue statement terminates the execution of the statement in the current iteration of a loop such as a for, while, and do…while loop and immediately continues to the next iteration.

Function
========

*   To avoid repeating the same code all over places, you can use a function to wrap that code and reuse it.
*   JavaScript provides many built-in functions
*   To declare a function, you use the function keyword, followed by the function name, a list of parameters, and the function body.
```javascript
    function functionName(parameters) {
        // code
    }
```
*   To use a function, you need to call it.
*   Calling a function is also known as invoking a function.
*   To call a function, you use its name followed by arguments enclosing in parentheses.
```javascript
    functionName(arguments);
```
*   The terms parameters and arguments are often used interchangeably. However, they are essentially different.
*   When declaring a function, you specify the parameters. However, when calling a function, you pass the arguments that are corresponding to the parameters.
*   For example, in the say() function, the message is the parameter and the 'Hello' string is an argument that corresponds to the message parameter.
*   To specify a return value for a function, you use the return statement followed by an expression or a value.

anonymous function
------------------

*   An anonymous function is a function without a name.
*   Note that if you don't place the anonymous function inside the (), you'll get a syntax error. The () makes the anonymous function an expression that returns a function object.
```javascript
    (function(){
        // ...                                             
    })
```
*   An anonymous function is not accessible after its initial creation. Therefore, you often need to assign it to a variable.
```javascript
    let show = function() {                                                 
        console.log('anonymous function');                                             
    }                                             
    show();
```
*   The anonymous function has no name between the function keyword and parentheses ().
*   Because we need to call the anonymous function later, we assign the anonymous function to the show variable.
*   Since the whole assignment of the anonymous function to the show variable makes a valid expression, you don't need to wrap the anonymous function inside the parentheses ().

arrow function
--------------

*   ES6 arrow functions provide you with an alternative way to write a shorter syntax compared to the function expression.
```javascript
    let add = (x,y) => x+y;
    console.log(add(3,4)); // 7
```
Document Object Model
=====================

*   The Document Object Model (DOM) is an application programming interface (API) for manipulating HTML documents.
*   The DOM represents an HTML document as a tree of nodes. The DOM provides functions that allow you to add, remove, and modify parts of the document effectively.
*   Note that the DOM is cross-platform and language-independent ways of manipulating HTML and XML documents.

Selecting Elements
------------------

*   select element by Id : `document.getElementById()`
*   select elements by name : `getElementsByName()`
*   select elements by tag name : `getElementsByTagName()`
*   select elements by class name : `getElementsByClassName()`
*   select elements by css selectors : `querySelector()querySelectorAll()`

Travesing Elements
------------------

*   parent element : The `node.parentNode` returns the read-only parent node of a specified node or null if it does not exist. `node.parentNode`
*   sibling element : To get the next sibling of an element, you use the `nextElementSibling` attribute.
*   To get the previous siblings of an element, you use the `previousElementSibling` attribute.
*   To get the first child element of a specified element, you use the `firstChild` property of the element.
*   to get the first child with the Element node only, you can use the `firstElementChild` property:
*   To get the last child element of a node, you use the `lastChild` property:
*   If you want to select only the last child element with the element node type, you use the `lastElementChild` property:
*   To get a live NodeList of child elements of a specified element, you use the `childNodes` property:
*   The `childNodes` property returns all child elements with any node type. To get the child element with only the element node type, you use the children property:

Manipulating Elements
---------------------

*   The `document.createElement()` accepts an HTML tag name and returns a new Node with the Element type.
*   The `appendChild()` method allows you to add a node to the end of the list of child nodes of a specified parent node.
*   To get the text content of a node and its descendants, you use the `textContent` property.
*   The `innerText` takes the CSS style into account and returns only human-readable text.
*   you can also use the `textContent` property to set the text for a node.
*   The `innerHTML` is a property of the Element that allows you to get or set the HTML markup contained within the element.
*   The `element.before()` method allows you to insert one or more nodes before the element.
*   The `element.after()` method allows you to insert one or more nodes after the element.
*   The `parentNode.append()` method inserts a set of Node objects or DOMString objects after the last child of a parent node.
*   The `prepend()` method inserts a set of Node objects or DOMString objects before the first child of a parent node,
*   To replace an HTML element, you use the `node.replaceChild()` method.
*   The `cloneNode()` is a method of the Node interface that allows you to clone an element:
*   To remove a child element of a node, you use the `removeChild()` method.
*   To insert a node before another node as a child node of a parent node, you use the `parentNode.insertBefore()` method.

Events
------

*   mousedown
*   mouseup
*   click
*   dblclick
*   mousemove
*   mouseover
*   mouseout
*   mouseenter
*   mouseleave
*   keydown
*   keyup
*   keypress
*   focus
*   submit
*   blur
*   change
*   etc…

Browser Object Model
====================

The Browser Object Model (BOM) is the core of JavaScript on the web. The BOM provides you with objects that expose the web browser's functionality.

window
------

The global object of JavaScript in the web browser is the window object. It means that all variables and functions declared globally with the var keyword become the properties and methods of the window object.

*   `window.innerWidth`
*   `window.innerHeight`
*   `window.location`
*   `window.location.href`
*   `window.location.href`
*   `window.location.search`
*   `window.open()`
*   `window.resizeTo()`
*   `window.resizeBy()`
*   `window.moveTo(x,y)`
*   `window.close()`
*   `window.alert()`
*   `window.confirm()`
*   `window.prompt()`
*   `window.setTimeout()`
*   `window.setInterval()`

navigator
---------

The JavaScript Navigator provides information about the web browser and its capabilities. You can reference the Navigator object via the read-only window.navigator property.

*   `navigator.appCodeName`
*   `navigator.appName`
*   `navigator.appVersion`
*   `navigator.battery`
*   `navigator.cookieEnabled`
*   `navigator.geolocation`
*   `navigator.userAgent`