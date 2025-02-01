# Fundamental of PHP Development

## What is PHP?
* PHP is a server side scripting language.
* Develop Static websites or Dynamic websites or Web applications.
* PHP stands for Hypertext Pre-processor, that earlier stood for Personal Home Pages.
* PHP scripts can only be interpreted on a server that has PHP installed.
* The client computers accessing the PHP scripts require a web browser only.
* A PHP file contains PHP tags and ends with the extension `.php`.

## PHP Syntax
```php
<?php
echo 'Hello World';
?>
```
A PHP file can also contain tags such as HTML and client-side scripts such as JavaScript. HTML is an added advantage when learning PHP Language. You can even learn PHP without knowing HTML but it’s recommended you at least know the basics of HTML. Database management systems DBMS for database powered applications. Diagram shown below illustrates the basic architecture of a PHP web application and how the server handles the requests.

## Why use PHP?
* PHP is open source and free.
* Short learning curve compared to other languages such as JSP, ASP etc.
* Large community document
* Most web hosting servers support PHP
* latest technology trends to update.
* PHP has in built support for working hand in hand with MySQL;
* You can also use PHP with <mark>Postgres</mark>, <mark>Oracle</mark>, <mark>MS SQL Server</mark>, <mark>ODBC etc.</mark>
* PHP is cross platform: you can deploy your application on a number of different operating systems such as windows, Linux, Mac OS etc.
  
## PHP File Extensions
File extension and Tags In order for the server to identify our PHP files and scripts, we must save the file with the `.php` extension. Older PHP file extensions include <mark>.phtml</mark>, <mark>.php3</mark>, <mark>.php4</mark>, <mark>.php5</mark>, <mark>.phps</mark>. PHP was designed to work with HTML, and as such, it can be embedded into the HTML code.
```php  
<?php
echo 'Hello World';
// output: Hello World
?>
```
### Summary
* PHP stands for Hypertext pre-processor
* PHP is a server side scripting language. This means that it is executed on the server. The client applications do not need to have PHP installed.
* PHP files are saved with the “.php” file extension, and the PHP development code is enclosed in tags.
* PHP is open source and cross platform

## What is Variable?
A variable is a name given to a memory location that stores data at runtime. The scope of a variable determines its visibility. A global variable is accessible to all the scripts in an application. A local variable is only accessible to the script that it was defined in.  
<ins>Rules of Variable</ins>
* All variable names must start with the dollar sign.  
`$name`
* Variable names are case sensitive. This means `$num` is different from `$NUM`    
`$num != $NUM`
* All variables names must start with a letter follow other characters    
`✅ $num1` `❌ $1num`
* Variable names must not contain any spaces,  
`❌ $first name` is not a legal variable name.  
You can instead use an underscore in place of the space `✅ $first_name`.
* You can't use characters such as the dollar or minus sign to separate variable names.  
`✅ $my_var;` `❌ $my-var;` `❌ $my var;`

```php
$my_var = 1;
echo $my_var; //Output: 1

$my_var = 3.14;
echo $my_var; // Output: 3.14

$my_var ="Hypertext Pre Processor";
echo $my_var; // Output: Hypertext Pre Processor
```

## Use of Variables
Variables are used for storing values such as numeric values, characters, character strings, or memory addresses so that they can be used in any part of the program.

## PHP Data Types
A Data type is the classification of data into a category according to its attributes;
* Alphanumeric characters are classified as strings
* Whole numbers are classified integers
* Numbers with decimal points are classified as floating points.
* True or false values are classified as Boolean.
* PHP is a loosely typed - Integer – whole numbers e.g. -3, 0, 69. The maximum value of an integer is platform-dependent. On a 32 bit machine, it’s usually around 2 billion. 64 bit machines usually have larger values. The constant `PHP_INT_MAX` is used to determine the maximum value.

### Scalar type

```php
$num_1 = -100;
echo $num_1; // 1
echo gettype($num_1); // integer

$num_3 = 1.234;
echo $num_3; // 1.234
echo gettype($num_3); // double

$str = "hello, PHP";
echo $str; // hello, PHP
echo gettype($str); // string

$isCompleted = true;
echo $isCompleted; // 1
echo gettype($isCompleted); // boolean

$isCompleted = false;
echo $isCompleted; // ''
echo gettype($isCompleted);// boolean
```
### Compound type
```php
// Array
$arr = ['apple', 'orange', 'mango'];
print_r($arr);
// Array
// (
//     [0] => one
//     [1] => two
//     [2] => three
// )

//  Object
class Car {
    public $brand;
    function __construct($brand) {
        $this->brand = $brand;
    }
}
$myCar = new Car("Toyota");
print_r($myCar);
// Car Object
// (
//     [brand] => Toyota
// )
```

### Special type 
```php
// Null
$email = null;
var_dump($email); // NULL

// Resource
```

## PHP Operators

### Arithmetic operators
| Operator | Name           | Description                         | Example                 | Output           |
|----------|----------------|-------------------------------------|-------------------------|------------------|
| +        | Addition       | Summation of x and y                | 1 + 1;                  | 2                |
| -        | Subtraction    | Difference between x and y          | 1 – 1;                  | 0                |
| *        | Multiplication | Multiplies x and y                  | 3 * 7;                  | 21               |
| /        | Division       | Quotient of x and y                 | 45 / 5;                 | 9                |
| %        | PHP Modulus    | Gives remainder of dividing x and y | 10 % 3                  | 1                |
| -n       | Negation       | Turns n into a negative number      | -(-5)                   | 5                |
| x.y      | Concatenation  | Puts together x and y               | “PHP”.”ROCKS”;<br>10.3; | PHP ROCKS<br>103 |

### Assignment Operators
| Operator | Name           | Description                       | Example                               | Output       |
|----------|----------------|-----------------------------------|---------------------------------------|--------------|
| x = ?    | Assignment     | Assigns the value of x to ?       | `$x = 5;`                             | 5            |
| x += ?   | Addition       | Increments the value of x by ?    | `$x = 2;`<br>`$x += 1;`               | 3            |
| x -= ?   | Substraction   | Subtracts ? from the value of x   | `$x = 3;`<br>`$x -= 2;`               | 1            |
| x *= ?   | Multiplication | Multiplies the value of x ? times | `$x = 0;`<br>`$x *= 9;`               | 0            |
| x /= ?   | Division       | Quotient of x and ?               | `$x = 6;`<br>`$x /= 3;`               | 2            |
| x %= ?   | Modulus        | The remainder of dividing x by ?  | `$x = 3;`<br>`$x %= 2;`               | 1            |
| x .= ?   | Concatenate    | Puts together items               | `$x = “Pretty”;`<br>`$x .= “ Cool!”;` | Pretty Cool! |

### Comparison operators
| Operator          | Name                  | Description                                                           | Example    | Output                                           |
|-------------------|-----------------------|-----------------------------------------------------------------------|------------|--------------------------------------------------|
| x == y            | Equal                 | Compares x and y then returns true if they are equal                  | 1 == ‘1’;  | True or 1                                        |
| x === y           | Identical             | Compares both values and data types                                   | 1 === ‘1’; | False or 0. Since 1 is integer and “1” is string |
| x != y,<br>x <> y | PHP Not equal         | Compares values of x and y returns true if the values are not equal   | 2 != 1;    | True or 1                                        |
| x > y             | Greater than          | Compares x and y then returns true if x is greater than y             | 3 > 1;     | True or 1                                        |
| x < y             | Less than             | Compares x and y then returns true if x is less than y                | 2 < 1;     | False or 0;                                      |
| x >= y            | Greater than or equal | Compares x and y then returns true if x is greater than or equal to y | 3 > 1;     | True or 1                                        |
| x <= y            | Less than or equal    | Compares x and y then returns true if x is less than or equal to y    | 2 < 1;     | False or 0;                                      |

### Logical operators
| Operator             | Name             | Description                                       | Example                    | Output                  |
|----------------------|------------------|---------------------------------------------------|----------------------------|-------------------------|
| x and y <br>x && y   | And              | Returns true if both x and y are true             | 1 and 4;<br>true && false; | true or 1<br>false or 0 |
| x or y <br> x \|\| y | Or               | Returns true if either x or y is true             | 6 or 9;<br>0 \|\| 0;       | true or 1<br>false or 0 |
| x xor y              | Exclusive or,Xor | Returns true if only x is true or only y is true  | 1 xor 1;<br>1 xor 0;       | false or 0<br>true or 1 |
| ! x                  | Not              | Returns true if x is false and false if x is true | !0;                        | true or 1               |

## Variable Type Casting
Type casting is converting a variable or value into a desired data type. This is very useful when performing arithmetic computations that require variables to be of the same data type. Type casting in PHP is done by the interpreter.

```php
$a = 1;
$b = 1.5;
$c = $a + $b;
$c = $a + (int) $b;
echo $c; // Output: 2
```
There are two types of casting
* Implicit Casting (Automatic)
```php
$x = 2;
$y = 4;
var_dump($x / $y); // 2/4 = 0.5 (Float)
var_dump($y / $x); // 4/2 = 2 (Int)
```
* Explicit Casting (Manual) - Casting to an integer. Both (int) and (integer) casts are valid.
```php
$x = 5.35;
$y = (int) $x; // cast $x to integer
var_dump($y);

$x = '25';
$y = (integer) $x; // cast $x to int
var_dump($y);

$string = '10 Animals';
$numberOfAnimals = (int) $string;
echo $numberOfAnimals;
```

`var_dump` function is used to determine the data type.

```php
$a = 1;
var_dump($a); // Output: int(1)

$b = 1.5;
var_dump($b); // Output: float(1.5)

$c = "I Love PHP";
var_dump($c); // Output: string(10) "I Love PHP"

$d = true;
var_dump($d); // Output: bool(true)
```
### Summary
* PHP is a loosely typed language.
* Variables are memory locations used to store data
* The value of constants cannot be changed at runtime
* Type casting is used to convert a value or variable into a desired data type
* Arithmetic operators are used to manipulate numeric data
* Assignment operators are used to assign data to variables
* Comparison operators are used to compare variables or values
* Logical operators are used to compare conditions or values

# PHP Constant
**Define constant** – A constant is a variable whose value cannot be changed at runtime. To define a constant, you use the `define()` function. The `define()` function takes the constant’s name as the first argument and the constant value as the second argument.
```php
define('WIDTH','1140px');
echo WIDTH;
```
constant names are uppercase. Unlike a variable, the constant name doesn’t start with the dollar sign(`$`). a constant can hold a simple value like a number, a string, a boolean value. From PHP 7.0, a constant can hold an array.
```php
define( 'ORIGIN', [0, 0] );
```
The following example uses the const keyword to define the SALES_TAX constant:
```php
const SALES_TAX = 0.085;
$gross_price = 100;
$net_price = $gross_price * (1 + SALES_TAX);
echo $net_price; // 108.5
```
## define vs const
`define()` is a function while the const is a language construct. `define()` function defines a constant at run-time, whereas the const keyword defines a constant at compile time. use the `define()` function to define a constant conditionally
```php
if(condition)
{
    define('WIDTH', '1140px');
}
```
❌ cannot use the `const` keyword to define a constant this way.
```php
if(condition)
{
    const WIDTH = '1140px';
}
```
### Summary
* A constant is a name that holds a simple value that cannot be changed during the execution of the script. From PHP 7, a constant can hold an array.
* A constant can be accessed from anywhere in the script.
* Use the `define()` function or `const` keyword to define a constant.
* Use the `define()` function if you want to define a constant conditionally or using an expression.

## PHP Control Structure

### Conditional Statements
Conditional Statements allow you to branch the path of execution in a script based on whether a single, or multiple conditions, evaluate to true or false.  
```php
// if Statement

$x=1;
if ($x == 1)
print '$x is equal to 1';

$age = 50;
if ($age > 30)
{
    echo "Your age is greater than 30!";
}

$x=1;
if ($x == 1) {
    print 'x is equal to 1';
    $x++;
    print 'now x is equal to 2';
}
```
```php
// else Statement  

$x=1;
if ($x == 2) {
    print 'x is equal to 2';
} else {
    print 'x is equal to 1';
}

$age = 50;
if ($age < 30){
    echo "Your age is less than 30!";
} else{
    echo "Your age is greater than or equal to 30!";
}

$year = 2014; // Leap years are divisible by 400 or by 4 but not 100
if(($year % 400 == 0) || (($year % 100 != 0) && ($year % 4 == 0))){
    echo "$year is a leap year.";
} else{
    echo "$year is not a leap year.";
}
```

```php
// elseif Statement

$x=1;
if ($x == 2) {
    print 'x is equal to 2';
}
elseif ($x == 1) {
    print 'x is equal to 1';
}
else {
    print 'x does not equal 2 or 1';
}
```

`Switches` are a good alternative to If/Else if/Else Statements in situations where you want to check multiple values against a single variable or condition.
```php
// Switches

$var = "yes";
switch ($var) {
case "maybe":
    print 'var is equal to yes';
    break;
case "no":
    print 'var is equal to no';
    break;
default:
    print 'none of the other two cases were true, so this sentence will be printed out instead.';
}

// Similar to the `break` Statement is the `exit` Statement. `exit` is particularly useful in situations where you run into what would be considered a "fatal error" (for example, if the user had entered a password that was incorrect) or any other time you needed to end the execution of a script before it naturally terminated. Unlike `break`, `exit` may be used anywhere in your scripts, inside or outside of control structures.  

$var = "yes";
switch ($var) {
case "yes":
    print '$var is equal to yes';
    exit;
case "no":
    print '$var is equal to no';
    break;
}
print "this will not be printed, because the script will have terminate before this line is reached";
```

### The Ternary Operator ( ? : )

```php
$x = 1;
($x==1) ? (print '$x is equal to 1') : (print '$x is not equal to 1');
```
## Control Loops
Loops in PHP are useful when you want to execute a piece of code repeatedly until a condition evaluates to false.  
Code is executed repeatedly as long as a condition evaluates to true, and as soon as the condition evaluates to false, the script continues executing the code after the loop.
```php
// while
$x=1;
while ($x <=10){
    print "$x<br>";
    $x++;
}

// do…while
$x = 11;
do {
    print $x . "<br>";
    $x++;
} while ($x <= 10);

// for
for ($x = 1; $x <= 10; $x++) {
    print $x . "<br>";
}

// foreach
foreach($array as $value)
{
    // Statements to be executed
}
```
### Summary
* The `for…` loop is used to execute a block of a specified number of times
* The `foreach…` loop is used to loop through arrays
* `while…` loop is used to execute a block of code as long as the set condition is made to be false
* The `do… while` loop is used to execute the block of code at least once then the rest of the execution is dependent on the evaluation of the set condition



## PHP Function
**Types of Functions**
* User Defined Functions in PHP
* Built-in Functions in PHP
* Advantages of PHP Function
* Creating and Calling Function
* PHP Function Arguments
* Passing Arguments By Reference
* PHP Is a Loosely Typed Language
* PHP Functions - Returning Value
* Setting Default Values for Passing Arguments
* Dynamic Function Calls  
### Advantages of PHP Function
* Reusability of Code: Unlike other programming languages, PHP Functions are specified only once
and can be called multiple times.
* Less Code: It saves a lot of code because the logic doesn't have to be written several times. You can
write the logic only once and reuse it by using functions.
* Simple to Comprehend: The programming logic is separated using PHP Functions. Since every logic is
divided into functions, it is easier to understand the application's flow.

## User Defined Functions in PHP
* In PHP, functions can be written on their own in addition to the built-in PHP functions.
* A function is a set of statements that can be used repeatedly in a program.
* When a page loads, a feature will not run automatically.
* A call to a function will cause it to be executed.  
The basic syntax of creating a custom function can be give with:
```php
function functionName(){
    // Code to be executed
}
```
*No Argument Function* :
```php
function call() {
    echo "PHP Function";
}
call(); // calling function
?>
```
```php
function whatIsToday()
{
    echo "Today is " . date('l');
}
// Calling function
whatIsToday();
?>
```
**Functions with Parameters** :
```php
function customFont($font, $size = 1.5) {
    echo "<p style=\"font-family: $font; font-size: {$size}em;\">Hello, world!</p>";
}
// Calling function
customFont("Arial", 2);
customFont("Times", 3);
customFont("Courier");
?>
```
**Returning Values from a Function**
```php
function getSum($num1, $num2) {
    $total = $num1 + $num2;
    return $total;
}
echo getSum(5, 10); // Outputs: 15
```
```php
function divideNumbers($dividend, $divisor) {
    $quotient = $dividend / $divisor;
    $array = array($dividend, $divisor, $quotient);
    return $array;
}
list($dividend, $divisor, $quotient) = divideNumbers(10, 2);
echo $dividend; // Outputs: 10
echo $divisor; // Outputs: 2
echo $quotient; // Outputs: 5
```
## PHP Function from Javascript
```php
<?php
function myphpfunction($x, $y)
{
$z = $x + $y;
return 'The sum is: ' . $z;
}
?>
<html>
    <head>
        <title>Untitled Document</title>
        <script type="text/javascript">
            alert("<?php echo myphpfunction(4, 90) ?>");
        </script>
    </head>
    <body></body>
</html>
```
## JavaScript Function from PHP
```html
<html>
    <head>
        <script type="text/javascript">
            function jsFunction() {
                alert('Execute Javascript Function Through PHP');
            }
        </script>
    </head>
    <body>
        <?php echo '<script type="text/javascript">jsFunction();</script>'; ?>
    </body>
</html>
```
```html
<html>
    <head>
        <meta charset="utf-8">
        <title>JavaScript Alert Box by PHP</title>
    </head>
    <body>
        <?php
        function createConfirmationmbox() {
            echo '<script type="text/javascript"> ';
            echo ' function openulr(newurl) {';
            echo ' if (confirm("Are you sure you want to open new URL")) {';
            echo ' document.location = newurl;';
            echo ' }';
            echo '}';
            echo '</script>';
        }
        createConfirmationmbox();
        ?>
        <strong>
            <a href="javascript:openulr('phploop.php');">Open new URL</a>
        </strong>
    </body>
</html>
```
## Passing Arguments to a Function by Reference
```php
<?php
function selfMultiply(&$number) {
    $number *= $number;
    return $number;
}
$mynum = 5;
echo $mynum; // Outputs: 5
selfMultiply($mynum);
echo $mynum; // Outputs: 25
```
## Understanding the Variable Scope
```php
<?php
function test() {
    $greet = "Hello World!";
    echo $greet;
}
test(); // Outputs: Hello World!
echo $greet; // Generate undefined variable error
```
```php
$greet = "Hello World!";
// Defining function
function test() {
    echo $greet;
}
test(); // Generate undefined variable error
echo $greet; // Outputs: Hello World!
```
**The global Keyword**
```php
$greet = "Hello World!";
// Defining function
function test() {
    global $greet;
    echo $greet;
}
test(); // Outpus: Hello World!
echo $greet; // Outpus: Hello World!
// Assign a new value to variable
$greet = "Goodbye";
test(); // Outputs: Goodbye
echo $greet; // Outputs: Goodbye
```
**Recursive Function**
```php
function display($number) {
    if ($number <= 5) {
        echo $number . "<br/>";
        display($number + 1);
    }
}
display(1);
```
 
### Built-in Functions in PHP 
PHP has over 1000 built-in functions that can be called directly from within a script to perform a specific task
in PHP Functions.  

### PHP String Functions
String functions are built-in language constructs and functions that are designed to manipulate and display
strings. These functions include trimming whitespace, properly escaping strings for security, splitting strings, and many more.  
`explode()`
The `explode` function splits a string by a given delimiter and returns an array with all the substrings between
the delimiters.  
*Limit is unspecified* :
```php
$str = "Toyota,BMW,Honda,Mercedes,Bugatti,Lamborghini,Acura,Porsche";

$exploded = explode(",", $str);
print_r($exploded);
// Array ( [0] => Toyota [1] => BMW [2] => Honda [3] => Mercedes [4] => Bugatti [5] => Lamborghini [6] => Acura [7] => Porsche ) 

$exploded = explode(",", $str, 5);
print_r($exploded);
// Array ( [0] => Toyota [1] => BMW [2] => Honda [3] => Mercedes [4] => Bugatti,Lamborghini,Acura,Porsche ) 
```
`implode() `
The `implode` function does the exact opposite of the explode function. It converts an array into a string, with each array element separated by a delimiter.
```php
$column_heading = ['first_name', 'age', 'phone number', 'address'];
$sample_header = implode('; ', $column_heading);
echo $sample_header;
// first_name; age; phone number; address

$trial = array('This', 'is', 'PHP', 'simplified');
echo implode("|", $trial); // This|is|PHP|simplified
echo implode("*", $trial); // This*is*PHP*simplified
echo implode("+", $trial); // This+is+PHP+simplified
echo implode("_", $trial); // This_is_PHP_simplified
```
`str_split()`
The `str_split` function takes a string to turn into an array, and splits the string into an array, with each of the characters being a separate character.
*No length specified* :
```php
$to_split = "Hello, World!";
print_r(str_split($to_split)); 
//Array ( [0] => H [1] => e [2] => l [3] => l [4] => o [5] => , [6] => [7] => W [8] => o [9] => r [10] => l [11] => d [12] => ! ) 
```
```php
$string = "hello world how are you";
print_r(str_split($string, 10));
// Array ( [0] => hello worl [1] => d how are [2] => you ) 
```
`trim()`
The `trim()` function removes whitespace characters from the beginning and end of a string on default settings, but can also remove other characters if specified
```php
$string = "Hello PHP! ";
echo trim($string);
```
`rtrim()` & `ltrim()`
These are the same as trim, except they only do it from one end. rtrim trims from the end, and ltrim trims from the beginning.
```php
$string1 = "Welcome     ";
$string2 = " website";
echo rtrim($string1) . " to the " . ltrim($string2);
// Welcome to the website
```
`addslashes()` 
This function takes one input string and returns a string with all of the quotation marks escaped by a slash.
```php
$string = "I am about to land at O'Hare airport in Chicago, Illinois";
echo addslashes($string);
// I am about to land at O\'Hare airport in Chicago, Illinois
```
`stripslashes()`
```php
$string = "I am about to land at O\'Hare airport in Chicago, Illinois";
echo stripslashes($string);
// I am about to land at O'Hare airport in Chicago, Illinois
```
`strip_tags()`  
`strip_tags()` is another security feature, to prevent people from entering HTML tags into forms. This is useful because otherwise, people could enter new forms, and submit them, as well as Javascript, and Iframes containing malicious code.
```php
$text = '<p>Test paragraph.</p><!-- Comment --> <a href="#fragment">Other text</a>';

echo strip_tags($text);
// Test paragraph. Other text

echo strip_tags($text, '<p>');
// Test paragraph.
// Other text
```
`substr()`
`substr()` takes a string and a location to start in that string, and returns the substring starting at the location specified going to the end of the string  
*no length specified* :
```php
$string = "hello, world!";
echo $string; // hello, world!

$substring = substr($string, 4);
echo $substring; // o, world!

$string = "hello, world!";
$substring = substr($string, 4, 4);
echo $substring; // o, w
```
`strpos()`
`strpos()` finds the location of a substring in a string.  
*Optional parameter offset not specified*:
```php
$haystack = "Welcome PHP";
$location = strpos($haystack, "c");
echo "The character c is found at character $location in $haystack";
// The character c is found at character 3 in Welcome PHP
```
`stripos()`
`stripos()` does the same thing as strpos, except that it is case-insensitive. The syntax and parameters are exactly the same as strops.
```php
$haystack = "hello, world!";
echo $haystack; // hello, world!"
$location = stripos($haystack, "L");
echo "The character L is found at character $location in $haystack";
// The character L is found at character 2 in hello, world!
```
`strstr()` 
`strstr()` takes a string to look in, a string to look for, and returns all of the characters before or after the string you want to look for  
```php
$haystack = "foo@bar.com";
$domain = strstr($haystack, "@");
echo $domain; // @bar.com
```
`stristr()` (case insensitive strstr)
`stristr()` takes a string to look in, a string to look for, and returns all of the characters before or after the string you want to look for
```php
$haystack = "FoO@bAr.cOm";
$needle = "@Ba";
$substring = stristr($haystack, $needle);
echo $substring; // @bAr.cOm
```
`str_replace()`  
`str_replace()` replaces certain substrings in a string with other substrings.  
```php
$string = "hello. My name is bob. This is my friend bob.";
$find = "bob";
$replace = "joe";
$result = str_replace($find, $replace, $string);
echo $string . "<br>" . $result;
// hello. My name is bob. This is my friend bob.
// hello. My name is joe. This is my friend joe.
```
```php
// *Search value is an array* :
$string = "hello. My name is bob. This is my friend bob.";
$find = array("bob", "friend");
$replace = "joe";
$result = str_replace($find, $replace, $string);
echo $string . "<br>" . $result;
// hello. My name is bob. This is my friend bob.
// hello. My name is joe. This is my joe joe.
```
`str_ireplace()`
`str_ireplace()` is a case-insensitive version of str_replace
```php
$string = "Hi! My name is Bob.";
$find = "bob";
$replace = "Joe";
$result = str_ireplace($find, $replace, $string);
echo "$string <br> $result";
// Hi! My name is Bob.
// Hi! My name is Joe.
```

## PHP Array
Array is a data structure which allows you to store multiple elements in a single variable.
```php
// Initialization an Array
$array = array();
$array = [];

$array_fruits = array('Apple', 'Orange', 'Watermelon', 'Mango');
$colors = ['red', 'green', 'blue', 'violet'];
```

### Types of Arrays in PHP
There are three kinds of arrays that you can make. These are listed below.
```php
// Define an indexed array
$colors = array("Red", "Green", "Blue"); 
// Output: Array ( [0] => Red [1] => Green [2] => Blue ) 
```
```php
// create an array already initialized with values
$array = [];
$array[] = 'One';
$array[] = 'Two';
$array[] = 'Three';
print_r($array); 
// Output: Array ( [0] => One [1] => Two [2] => Three )
```

#### Numeric arrays – Arrays with a numeric index
The filled or indexed array is an array where all key values are numeric and always start from zero. You can define this array as below.
```php
// Numeric array
$fruit = array("apple", "banana", "mango");

// get the first element of the $fruit array
echo $fruit[0]; // apple

// get the second element of the $fruit array
echo $fruit[1]; // banana

// get the third element of the $fruit array
echo $fruit[2]; // mango

```

#### Associative arrays – Arrays with named keys
The keys are well defined with respect to the data that index holds as shown in the below example.
```php
$ages = array("Zaid" => 26, "Ali" => 30, "John" => 28, "Cris" => 28, "Clark" => 28);
print_r($ages);
```
```php
$persons = array("Mary" => "Female", "John" => "Male", "Mirriam" => "Female");
print_r($persons);
echo "Mary is a " . $persons["Mary"];
```
```php
$person_weight = array(
    "Rajnish" => 58,
    "Sanjeev" => 55,
    "Ravi" => 60,
    "Yash" => 60,
    "Suraj" => 48
);
// Use for-each loop and display the key of associative array
foreach ($person_weight as $key => $value) {
    echo "Key: " . $key . "<br>";
}
```

#### Multidimensional arrays – Arrays containing one or more arrays  
In a multidimensional array, there are one or more arrays between the array. So, you can say the sub-array of the first array.
```php
$movies = array(
    "comedy" => array("Pink Panther", "John English", "See no evil hear no evil"),
    "action" => array("Die Hard", "Expendables"),
    "epic" => array("The Lord of the rings"),
    "Romance" => array("Romeo and Juliet")
);
print_r($movies);
```
```php
$a[0][0] = "value0";
$a[0][1] = "value1";
$a[0][2] = "value2";
$a[1][0] = "value3";
$a[1][1] = "value4";
$a[1][2] = "value5";
$a[2][0] = "value6";
$a[2][1] = "value7";
$a[2][2] = "value8";

for ($b = 0; $b < count($a); $b++) {
    for ($c = 0; $c < count($a[$b]); $c++) {
        echo $a[$b][$c], "<br> ";
    }
}
// output:
// value0
// value1
// value2
// value3
// value4
// value5
// value6
// value7
// value8
```
```php
$name = array(
    array("ajay", "kumar", 10),
    array("vijay", "kumar", 20),
    array("dhanjay", "kumar", 30)
);
for ($e = 0; $e < count($name); $e++) {
    echo "--------------------------<br>";
    for ($f = 0; $f < count($name[$e]); $f++) {
        echo $name[$e][$f], "<br>";
    }
}
// Output
// --------------------------
// ajay
// kumar
// 10
// --------------------------
// vijay
// kumar
// 20
// --------------------------
// dhanjay
// kumar
// 30
```
```php
$d = array(
"sunday" => array("cost", "first", 10),
"monday" => array("cost1", "second", 20),
"tuesday" => array("cost2", "third", 30)
);
foreach ($d as $e) {
    foreach ($e as $f) {
        echo $f, " ";
    }
    echo "<br>";
}
```
```php
$users = ['john', 'dave', 'tim'];

// for loop
for ($i = 0; $i < count($users); $i++)
echo $users[$i] . "<br>";

// foreach loop
foreach ($users as $user)
echo $user . "<br>";
```

## PHP Array Function
`count()`
The length of an array can be counted using the in-built function `count()`.
```php
$my_array1 = array("apple", "banana", "mango", "peach");
echo "Length of the array is: " . count($my_array1);
// Length of the array is: 4
```
`array_keys()`
The `array_keys()` function is used to get all the keys or a subset of the keys of an array.
```php
$array1 = array("Orange" => 100, "Apple" => 200, "Banana" => 300, "Cherry" => 400);
print_r(array_keys($array1));
// Array ( [0] => Orange [1] => Apple [2] => Banana [3] => Cherry ) 
```
`array_values() `
Return all the values of an array
```php
$array = array("size" => "XL", "color" => "gold");
print_r(array_values($array));
// Array ( [0] => XL [1] => gold ) 
```
`array_push()`
Push one or more elements onto the end of array
```php
$arr = ['apple', 'orange', 'mango'];
array_push($arr, 'strawberry');
print_r($arr);
// Array ( [0] => apple [1] => orange [2] => mango [3] => strawberry ) 
```
`array_unshift()` 
Prepend one or more elements to the beginning of an array
```php
$arr = ['apple', 'orange', 'mango'];
array_unshift($arr, 'watermelon');
print_r($arr);
// Array ( [0] => watermelon [1] => apple [2] => orange [3] => mango ) 
```
`array_pop()`
Pop the element off the end of array
```php
$arr = ['apple', 'orange', 'mango'];
array_pop($arr);
print_r($arr);
// Array ( [0] => apple [1] => orange ) 
```
`array_shift()`
Shift an element off the beginning of array
```php
$arr = ['apple', 'orange', 'mango'];
array_shift($arr);
print_r($arr);
// Array ( [0] => orange [1] => mango ) 
```
`array_map()`
Applies the callback to the elements of the given arrays
```php
$fruits = ['apple', 'orange', 'mango'];
$arrmap = array_map(function($f) {
    return strtoupper($f);
}, $fruits);
print_r($arrmap);
// Array ( [0] => APPLE [1] => ORANGE [2] => MANGO ) 
```
`list()`  
list — Assign variables as if they were an array
```php
$fruits = ['apple', 'orange', 'mango'];
list($f1, $f2, $f3) = $fruits;
echo $f1; // apple
echo $f2; // orange
echo $f3; // mango
```
`array_walk()`
The `array_walk` is an array function provided by PHP which applies the given function to each element in the array, hence the name `array_walk`.
```php
$users = ['john', 'dave', 'tim'];
function print_item($item, $key)
{
    echo "Hi, I am $item. <br>";
}
array_walk($users, 'print_item');
// Hi, I am john.
// Hi, I am dave.
// Hi, I am tim. 
```
### Summary
* Arrays in PHP are one of the most powerful and flexible mechanisms for storing and manipulating
lists of data.
* Arrays will be used often in the course of developing web applications using PHP.


**filter_var ()**  
`filter_var()` is a PHP function used to filters a variable with the help of a specified filter. we can use `filter_var()` function to validate and sanitize a data such as email id, IP address etc.
1. Sanitize and Validate an Email Address
```php
$email = "test@test.com";
// Remove all illegal characters from email
$email = filter_var($email, FILTER_SANITIZE_EMAIL);
// Validate e-mail
if (filter_var($email, FILTER_VALIDATE_EMAIL)) {
    echo ("$email is a valid email address");
} else {
    echo ("$email is not a valid email address");
}
```
2. Sanitize a String
```php
// Variable to check
$string = "<p><strong>This is a Stechies !</strong></p>";
// Remove all illegal characters from string
$string = filter_var($string, FILTER_SANITIZE_STRING);
echo $string;
```
3. Validate an Integer Number
```php
// Variable to check
$intnum = 1000022;
if (filter_var($intnum, FILTER_VALIDATE_INT)) {
    echo ("$intnum is a valid integer number");
} else {
    echo ("$intnum is not a valid integer number");
}
```
4. Validate a float Number
```php
// Variable to check
$intnum = 11.11;
if (filter_var($intnum, FILTER_VALIDATE_FLOAT)) {
    echo ("$intnum is a valid float number");
} else {
    echo ("$intnum is not a valid float number");
}
```
5. Validate an IP Address
```php
// Variable to check
$ipadd = '192.168.1.1';
if (filter_var($ipadd, FILTER_VALIDATE_IP)) {
    echo ("$ipadd is a valid IP address");
} else {
    echo ("$ipadd is not a valid IP address");
}
```
6. Sanitize and Validate a URL
```php
// Variable to check
$url = "https://www.stechies.com/";
// Remove all illegal characters from url
$url = filter_var($url, FILTER_SANITIZE_URL);
// Validate url
if (!filter_var($url, FILTER_VALIDATE_URL) == false) {
    echo ("$url is a valid URL");
} else {
    echo ("$url is not a valid URL");
}
```
## Summary
* Function in PHP is a section of code in a program that is written to perform a specific task.
* Take data as a parameter, run a block of statements, perform operations, and then return the
result.
* Creating calling the function, functions with parameters, passing default values as arguments.

# Working with Form
**A Simple HTML Form**
```php
<!-- Form.php -->
<html>
    <body>
        <form action="pet.php" method="post">
            Pet breed: <input type="text" name="breed"><br>
            Color: <input type="text" name="color"><br>
            <input type="submit">
        </form>
    </body>
</html>
```
**GET and POST Methods**
```php
<html>
    <body>
        Your pet breed is: <?php echo $_POST["breed"]; ?> <br>
        Color is: <?php echo $_POST["color"]; ?>
    </body>
</html>
```

# Working with Files and Directories with PHP
## File open modes
When opening a file, there are several different modes you can use. The most common ones are r and w for read and write. There are several more available though that will control whether you create a new file, open an existing file, and whether you start writing at the beginning or the end. These modes are used with `fopen()` in the rest of the examples.  
**Write to a file**  
When writing files you have two primary options that we will look at:    
Writing bytes as needed with `fwrite()`  
Writing the entire file contents at once with `file_put_contents()`  
**WRITE BYTES**
```php
$file = fopen('hello.txt', "w") or die("Unable to open file!");
fwrite($file, "Hello, world!");
fclose($file);
```
**WRITE ENTIRE FILE AT ONCE**
```php
file_put_contents('hello.txt', "I am Healthy!");
```
**Read from a file**  
When reading a file you have the same two primary options that we will look at:  
Reading bytes as needed with `fread()`  
Reading the entire file in to a variable with `file_get_contents()`  
**READ BYTES**
```php
$filename = 'hello.txt';
$number_of_bytes_to_read = filesize($filename);
$file = fopen($filename, 'r');
$contents = fread($file, $number_of_bytes_to_read);
echo $contents;
```
**READ ENTIRE FILE AT ONCE**
```php
$contents = file_get_contents('hello.txt');
echo $contents;
```
**READ ALL LINES OF A TEXT FILE**
```php
$lines = file('hello.txt');
print_r($lines);
```
**GET FILESIZE**
```php
echo filesize('hello.txt'); 
```
**FILE EXISTS**
The function, as you can see from the definition above, returns a boolean:
* If the file (or directory) exists, it will return true
* Otherwise, it will return false  
The `file_exists()` function is supported by PHP 4, PHP 5, PHP 7, and PHP 8  
Use the `getcwd()` Function to Get the Current Directory Name in PHP  
Use the `dirname(__FILES__)` Function to Get the Current Directory Name in PHP  
Use the `basename()` function to get the current directory name in PHP
```php
echo basename(dirname(__FILE__)) . "<br>";
echo basename(getcwd()) . "<br>";
```
```php
// Define the path to your file
$path_to_file = (dirname(__FILE__)) ."\hello.txt";
if (file_exists($path_to_file)) {
    echo "Hooray, the file exists!";
} else {
    echo "Whoops, no such file exists!";
}
// echo basename(dirname(__FILE__))."<br>";
// echo basename(getcwd())."<br>";
```
**CHECK IF FILE IS A DIRECTORY**  
To check if a directory entry is a file or a directory, you can use `is_dir()` function.
```php
$file = "hello.txt";
mkdir("documents"); // make directory folder
if (is_dir($file)) {
    echo ("$file is a directory");
} else {
    echo ("$file is not a directory");
}

echo "<br>";

if (is_dir("documents")) {
    echo ("Documents is a directory");
} else {
    echo ("Documents is not a directory");
}
```
**How to change directory of the running PHP script**  
```php
// current directory
echo getcwd() . "<br>";
// change directory
chdir('Documents');
// current directory
echo getcwd() . "<br>";
```
If the directory you specified doesn’t exist, then the function will produce a warning as shown below:

## Work With JSON In PHP
**What is JSON?**
* JSON stands for JavaScript Object Notation.
* This is a way to store and exchange data.
* JSON is text based, so it can easily sent from the user to the server and the server back to the user.
* It’s a useful format because it allows different programming languages to communicate with each
other.
**JSON Functions**  
PHP contains built-in functions that can be used to handle JSON.
* `json_encode()`: used to encode an array into a JSON object
* `json_decode()`: used to turn a JSON object into an array.  
These functions are the opposite of each other.
```php
$age = array("Peter" => 35, "Ben" => 37, "Joe" => 43);
echo json_encode($age);
```
```php
$jsonobj = '{"John":23,"Jack":"25", "Joe":31}';
$obj = json_decode($jsonobj);
echo $obj->John . "<br>";
echo $obj->Jack . "<br>";
echo $obj->Joe . "<br>";
```
**Looping Through A JSON**
```php
$jsonobj = '{"John":23,"Jack":"25", "Joe":31}';
$obj = json_decode($jsonobj);
foreach ($obj as $key => $value) {
    echo $key . " => " . $value . "<br>";
}
```
**To get the current directory**
`__DIR__`: This constant is used to get the current directory of the file. This is equivalent to the dirname(`__FILE__`).
```php
echo "The current directory of this file is '" . `__DIR__` . "'.<br>";
```
**To get the current filename with full file path**
```php
echo "The current file with path is '" . `__FILE__` . "'.<br>";
```
**To get the current line number**  
`__LINE__`: This is used to return the current line number of the file.  
```php
echo "The line number of this code is '" . `__LINE__` . "'.<br>";  
```
**Delete a Directory**
* Use the rmdir() Function to Delete an Empty Directory in PHP
* Use Recursion to Delete Non-Empty Directory in PHP  
**Empty Directory**
```php
$path = "testing";
if (is_dir($path)) {
    rmdir($path);
    echo "the directory is deleted";
}
```

# Object-Oriented Programming in PHP
The PHP Object-Oriented Programming concepts are:
* Class
* Objects
* Inheritance
* Interface
* Abstraction

## Class & Object
Class is a programmer-defined data type, which includes local methods and local variables. Class is also a collection of objects. Object has properties and behavior.  
You can define a **class** like this:  
```php
<?php

class ClassName
{
    //
}

```

### Creating Objects in PHP
When class is created, we can create any number of objects in that class. The object is created with the help of the new keyword.  
The process of creating a new object is also called **instantiation**.  
You can create a **new object** like this:
```php
<?php

class People
{
    //
}
$person = new People();
```

### Add properties to class
add properties to class :
```php
<?php

class People
{
    public name;
    public age;
}
```

### Accessing properties in class
```php
<?php

$object->property;

```

### Adding methods to class
```php
<?php

class People
{
    public function walk()
    {

    }
}

```

### Calling methods of a class
When the object is created, we can access the variables and method function of the class with the help of operator `->`.  
```php
// classs with properties and method
class Car
{
    public function color()
    {
        return "This car is white";
    }
}

// instantiate a Class
$nissan = new Car;
echo $nissan->color();
```

### $this
`$this` သည် ယခုလက်ရှိ class ကိုရည်ညွှန်းခြင်းဖြစ်ပါသည်။

## Magic Methods
Magic methods are special methods which override PHP's default's action when certain actions are performed on an object. All methods names starting with `__` are reserved by PHP.

### Constructor
PHP constructor function is called when the object is created.  
The magic method `__construct()` is known as a constructor that is automatically called whenever a new object is created.  
keep in mind that the construct function starts with two underscores (`__`).
```php
// classes with constructor method
class Car
{
    public $brand;
    public function __construct($brand)
    {
        $this->brand = $brand;
    }
    public function color()
    {
        return "$this->brand is white color";
    }
}
$kia = new Car("KIA");
$kia->color();
```
### Destructor

`__destruct()` method is executed automatically when the object is destroyed.  
keep in mind that the destructor function starts with two underscores (`__`).

```php
<?php

class House
{
    public $name;
    public $color;
    public function __construct($name, $color)
    {
        $this->name = $name;
        $this->color = $color;
    }
    public function about() {
        return "The color of the {$this->name} is {$this->color}";
    }
    public function __destruct()
    {
        echo "<br>This is all the information of the House Class";
    }
}
$blackHouse = new House("John's House", "black");
print_r($blackHouse->about());
```

## Access Modifiers
PHP supports various keywords to make any variable to access any variable and the identifiers.  
Assign these keywords to the class, function or identifiers.  
* Public
* Private
* Protected
* Abstract
* Final  

| Access Modifier | Class Level | Function Level | Variable Level |
|:----------------|:------------|:---------------|:---------------|
| public          | NA          | YES            | YES            |
| private         | NA          | YES            | YES            |
| protected       | NA          | YES            | YES            |
| abstract        | YES         | YES            | NA             |
| final           | YES         | YES            | NA             |
| static          | NA          | YES            | YES            |

### Public access modifier
The public is the default modifier in PHP. If we do not use any modifier with the functions of the identifiers by default, it is considered as a public access modifier.
### Private access modifier
This modifier us the private keyword to process with it. We cannot use the private modifier with the class.  
We can use this with the class variables and class methods only.
When we declare and use the private, it cannot be accessed using the class’s object. It can only be used within the class.
### Protected access modifier
Like public and private, protected itself doesn’t support at the class level.  
Like a private modifier, protected also restricts the class variables’ access or the function from outside of the
class.  
It can be used within the same class and from the subclass.  

```php
// access control -> public, protected, private
class Car
{
    public $brand;
    protected $model;
    private $carno;
    public function __construct($brand, $model, $carno)
    {
        $this->brand = $brand;
        $this->model = $model;
        $this->carno = $carno;
    }
    public function drive()
    {
        return "$this->brand $this->model ($this->carno) can drive very fast";
    }
}
$subaru = new Car("Japan", "Samba", "1234");
echo $subaru->brand;
echo $subaru->model; // cannot access protected property // same with method
echo $subaru->carno; // cannot access private property // same with method
echo $subaru->drive();
```

## Class Inheritance
Inheritance allows a class to reuse the code from another class without duplicating it.  
In inheritance, you have a parent class with properties and methods, and a child class can use the code from the parent class.  
For example, when extending a class, the subclass inherits all of the public and protected methods, properties and constants from the parent class. Unless a class overrides those methods, they will retain their original functionality.  

```php
// inherit a class
class Car
{
    public $name;
    public function __construct($name)
    {
        $this->name = $name;
    }
    public function name()
    {
        return "The car brand is $this->name <br>";
    }
}

class Toyota extends Car
{
    public $model;
    public function __construct($name, $model)
    {
        parent::__construct($name);
        $this->model = $model;
    }
    public function model()
    {
        return "$this->model is one of Toyota <br>";
    }
}
$probox = new Toyota("Toyota", "Probox");
echo $probox->name();
echo $probox->model();
```

### abstract classes

**abstract classes** are something going with inheritance.  
Abstract classes have abstract methods in it which they need their children (child classes) to override when inheriting.  
**Declaring Abstract Methods**  
* If a class is abstract, you cannot create an object of that class.
* Abstract methods only define the method’s signature, without the body.
* If a class has at least one abstract method, then the class too must be abstract.
* When you define a child class of an abstract class, you must write the body of all the abstract methods of the parent class.  
a class is an `abstract` class, you need to use the `abstract` keyword like this:
```php
abstract class Electronic
{
    public $pwrConsumption;
}
```
Cannot create objects of this class, but you must create a child class first.  

**Add abstract methods to the class**
An abstract method is a class method that only defines the method’s signature, without the body.
```php
abstract class Electronic
{
    public $pwrConsumption;
    abstract public function turnOn();
    abstract public function turnOff();
}
```

A class that contains at least one abstract method, must be an abstract class.

```php
<?php
class MyClass
{
    abstract public function myMethod();
}
// Fatal error: Class MyClass contains 1 abstract method and must therefore be declared abstract or implement the remaining methods (MyClass::myMethod)
```

It is an error because there is no abstract keyword before the class:  
The role of abstract methods is to set a requirement for children classes.

```php
abstract class MyClass
{
    abstract public function myMethod();
}

class ConcreteClass extends MyClass
{
    public function myMethod()
    {
    echo "Hello";
    }
}
```

**Final classes**
Inheritance allows for enormous flexibility within a class hierarchy. You can create subclasses to extend the functionality of a base class, but PHP OOP gives the possibility to create classes that cannot be extended. Such a class is called final class.  
A final class is declared by adding the final keyword before the class word.
```php
final class Base
{
    //code here
}

// define a child class derivated from Base
class BaseChild extends Base
{
    //code here
}
// Output: Fatal error: Class BaseChild may not inherit from final class (Base) in ...
```

**Final methods**
A normal method (public or protected) can be overridden in the child class. If you want a method to remain fixed and unchanging, prefix the definition with the final keyword.  
A final method cannot be overridden.  

```php
// base class
class Base
{
    // final method
    final public function testMethod()
    {
        echo 'This is a final method';
    }
}

// define a child class derivated from Base
class BaseChild extends Base
{
    // override the testMethod()
    public function testMethod()
    {
    echo 'Another text';
    }
}
// Output: Fatal error: Cannot override final method Base::testMethod() in ...
```

**Static Class**  
A static method is a method that is not invoked on any object. when you are creating a static method, inside of it there is no mention of the keyword `$this`. The keyword `$this` is used only for non-static methods. Since there is no object with static methods, there is no use of the keyword `$this`.
```php
// static => direct use from class
class Car
{
    static $make = "Subaru";
    static function drive()
    {
        return static::$make . " can drive very fast. <br>";
    }
}
echo Car::$make;
echo Car::drive();
$samba = new Car;
echo $samba->drive();
echo $samba->make; // undefinded property
?>
```

# Error & Exception Handling
There are four types of PHP error handling best practices and they are as follows:
1. Warning Error
2. Notice Error
3. Parse Error
4. Fatal Error

1. Warning Error* : The main reason for warning errors is to include a missing file or passing an incorrect number of parameters in a function. A warning error is a type of error that does not stop the execution of the script.
```php
echo "Warning Error!!";
include("function.php");
```

2. Notice Error* : Notice error and warning error both are similar which means it does not stop the execution of the code. It occurs when you try to access an undefined variable, then it generates a notice error.
```php
$a = 10;
echo "Notice Error !!";
echo $b;
echo "Below notice error";
```

3. Parse Error* : A Parse error is a type of error that you need to know about when dealing with PHP error handling best practices and is caused by misused or missing symbols in a syntax. A parse error is also known as a Syntax
error. Some common reasons for parse errors are:
   * Unclosed quotes/braces
   * Missing or Extra parentheses/semicolon
   * Misspellings
```php
echo "A";
echo "B"
echo "C";
 ```

4. Fatal Error* : A fatal error is another type of error that is caused due to the use of an undefined function or class. It is the type of error where the PHP compiler understands the PHP code but it recognizes an undeclared function. This means that function is called without the definition of the function.
```php
function message()
{
    echo "Hello team";
}
sms();
echo "Fatal Error !!";
```

## Ways to Handle PHP Errors
Procedural error handling in PHP can be handled in the following ways:
1. Using die() method
2. Custom Error Handling

*1. Using die() function*
```php
$file = fopen("profile.txt", "r");
```
To prevent the user from getting the error message, check whether the file exists or not before accessing it.
```php
if (!file_exists("profile.txt")) {
    die("File not found");
} else {
    $file = fopen("profile.txt", "r");
    print "Open file successfully";
}
```

*2. Custom Error handling*
Create a function that can be called when an error has occurred in PHP.
```php
Function syntax
error_function(error_level,error_message,error_file,error_line,error_context);
```
function must be able to handle a minimum of two parameters (error level and error message).  
**Parameter & Description**  
*$error_level*: Required parameter and it must be an integer. There are predefined error levels.
*$error_message*: Required parameter and it is the message which the user wants to print.
*$error_file*: Optional parameter and used to specify the file in which error has occurred.
*$error_line*: Optional parameter and used to specify the line number in which error has occurred.
*$error_context*: Optional parameter and used to specify an array containing every variable and their value when an error has occurred.
```php
function myerror($error_no, $error_msg)
{
    echo "Error: [$error_no] $error_msg ";
    echo "<br>";
    echo "Now Script will end";
    die();
}
set_error_handler("myerror"); // Setting set_error_handler
$a = 50;
$b = 0;
echo ($a / $b); // This will generate error
```
**Exceptions Handling**
Exception handling is a powerful way which can handle runtime errors.
"An unexpected result of a program is an exception, which can be handled by the program itself." Exceptions can be thrown and caught in PHP.  
***Benefits of Exception Handling***
* Exception handling can control run-time errors that occur in the program.
* It can avoid abnormal termination of the program and also shows the behavior of the program to users.
* It can separate the error handling code and normal code by using try-catch block.  
**Try**  
The try block contains the code that may have an exception or where an exception can occur.  
**Catch**  
The catch block contains the code that executes when a particular exception is thrown. It is always used with a try block, not alone. When an exception occurs, PHP finds the matching catch block.  
**Throw**  
It is a keyword that is used to throw an exception. It also helps to list all the exceptions that a function throws but does not handle itself. Remember that each throw must have at least one "catch".  
**Finally**  
The final block contains a code, which is used for clean-up activity in PHP. It executes the essential code of
the program.
```php
try {
    $firstValue = 10;
    $secondValue = 0;
    if ($secondValue == 0) throw new Exception("Divide by Zero exception occurred");
    $result = $firstValue / $secondValue;
    printf("Result is : ", $result);
} 
catch (Exception $e) {
    printf("Exception: %s", $e->getMessage());
}
```
```php
session_start();
$_SESSION["tagName"] = "PHP";
```

**Accessing Session Variable**  
The data is stored in a session variable, then it is in the global scope and can be accessed from any PHP file.
```php
session_start();
$tag = $_SESSION["tagName"];
echo "Welcome to $tag world!";
```

# Database with MySQL
**what is MySQL**  
* open source relational database management system
* uses the SQL(Structured Query Language)
* A leading database for web applications
* Used for small apps to large enterprise apps
* Used with multiple languages (PHP, Node, Python, C#, etc…)
* Cross platform
* Based on relational model of data
* virtually all RDBMS use SQL to manage them
* uses ‘tables’ with ‘columns’ and ‘rows’
* tables can relate to each other by keys  
MySQL is the world’s most popular open source database. According to DB-Engines, MySQL ranks as the second-most-popular database, behind Oracle Database. MySQL powers many of the most accessed applications, including Facebook, Twitter, Netflix, Uber, Airbnb, Shopify, and Booking.com.  
Since MySQL is open source, it includes numerous features developed in close cooperation with users over more than 25 years. So it’s very likely that your favorite application or programming language is supported by MySQL Database.  
**Common Data Types**
* numeric (int.tinyint.bigint.float)
* string (varchar.text.char)
* dates (date.datetime.timestamp)
* others (binary.json)  
**Management Tools**  
1. Terminal
2. Desktop Tools – MySQL workbench, CloudBeaver, etc…
3. Web Based Tools – phpMyAdmin, etc…  
**Create A Database**
you can create a database via command or tools:   
in terminal: `create database test;`  
you can connect database via `mysqli_connect()` method:
```php
// mysqli_connect('hostname', 'username', 'password', 'databasename');
mysqli_connect('localhost', 'root','', 'students')
```
**if you want to select data from table:**
```php
SELECT id, name, email FROM users
// or you can select all column via
SELECT * FROM users
```
**add new data to table:**
```php
INSERT INTO users (id, name, email) VALUES ('1', 'Andy', 'andy@gmail.com')
```
**update the existing data in table:**
```php
UPDATE users SET name='Cindy', email='cindy@gmail.com' WHERE id='1'
```
**delete the existing data in table:**
```php
DELETE FROM users WHERE id='1'
```
# MySQL with PDO
PHP PDO is a database access layer that provides a uniform interface for working with multiple databases.
PDO allows you to work with any database that has a PDO driver available. PDO relies on database-specific drivers,   
e.g., `PDO_MYSQL` for MySQL, `PDO_PGSQL` for PostgreSQL, `PDO_OCI` for Oracle database, etc., to
function properly.  
PDO uses a data source name (DSN) that contains the following information:
* The database server host
* The database name
* The user
* The password
* and other parameters such as character sets, etc.  

PDO uses this information to make a connection to the database server. To connect to the MySQL database server, you use the following data source name format:
```php
"mysql:host=host_name;dbname=db_name;charset=UTF8"
```
for example:
```php
$dsn = "mysql:host=localhost;dbname=bookdb;charset=UTF8";
```
Connecting to MySQL
```php
$dsn = "mysql:host=localhost;dbname=blog";
$db = new PDO($dsn, 'root', '', [
    PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION,
    PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_OBJ
]);
```
**Select all data from table:**
```php
$result = $db->prepare("SELECT * FROM users");
$result->execute();
$users = $result->fetchAll();
print_R($users);
```
**Insert new data to table:**
```php
$query ="INSERT INTO users (name, email, phone, address) VALUES (:name, :email, :phone, :address)";
$result = $db->prepare($query);
$result->execute([
    'name' => 'Jenny',
    'email' => 'jenny@gmail.com',
    'phone' => '09123456',
    'address' => 'No.1, Bagan Street, Yangon',
]);
```


# Superglobals

Superglobals — Built-in variables that are always available in all scopes
Several predefined variables in PHP are "superglobals", which means they are available in all scopes throughout a script. There is no need to do global $variable; to access them within functions or methods. 

## $GLOBALS
References all variables available in global scope
An associative array containing references to all variables which are currently defined in the global scope of the script.

## $_SERVER
Server and execution environment information. $_SERVER is an array containing information such as headers, paths, and script locations. The entries in this array are created by the web server.

## $_GET
(PHP 4 >= 4.1.0, PHP 5, PHP 7, PHP 8)
HTTP GET variables.
An associative array of variables passed to the current script via the URL parameters (aka. query string). Note that the array is not only populated for GET requests, but rather for all requests with a query string.  

## $_POST
(PHP 4 >= 4.1.0, PHP 5, PHP 7, PHP 8)
$_POST — HTTP POST variables

Description ¶

An associative array of variables passed to the current script via the HTTP POST method when using application/x-www-form-urlencoded or multipart/form-data as the HTTP Content-Type in the request.

## $_FILES
(PHP 4 >= 4.1.0, PHP 5, PHP 7, PHP 8)
$_FILES — HTTP File Upload variables

Description ¶

An associative array of items uploaded to the current script via the HTTP POST method. The structure of this array is outlined in the POST method uploads section.

## $_COOKIE
(PHP 4 >= 4.1.0, PHP 5, PHP 7, PHP 8)
$_COOKIE — HTTP Cookies

Description ¶

An associative array of variables passed to the current script via HTTP Cookies.

## $_SESSION
(PHP 4 >= 4.1.0, PHP 5, PHP 7, PHP 8)
$_SESSION — Session variables

Description ¶

An associative array containing session variables available to the current script. See the Session functions documentation for more information on how this is used.

## $_REQUEST
(PHP 4 >= 4.1.0, PHP 5, PHP 7, PHP 8)
$_REQUEST — HTTP Request variables

Description ¶

An associative array that by default contains the contents of $_GET, $_POST and $_COOKIE.

## $_ENV
(PHP 4 >= 4.1.0, PHP 5, PHP 7, PHP 8)
$_ENV — Environment variables

Description ¶

An associative array of variables passed to the current script via the environment method.

These variables are imported into PHP's global namespace from the environment under which the PHP parser is running. Many are provided by the shell under which PHP is running and different systems are likely running different kinds of shells, a definitive list is impossible. Please see your shell's documentation for a list of defined environment variables.

Other environment variables include the CGI variables, placed there regardless of whether PHP is running as a server module or CGI processor.


