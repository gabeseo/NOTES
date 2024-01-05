Lesson Overview 
 * How do you declare a variable?
 * What are three different ways to declare a variable?
 * Which one should you use when?
 * What are the rules for naming variables?
 * What are operators, operands, and operations?
 * What is concatenation and what happens when you add numbers and strings together?
 * What are the different types of operators in JavaScript?
 * What is the difference between == and ===?
 * What are operator precedence values?
 * What are the increment/decrement operators?
 * What is the difference between prefixing and postfixing them?
 * What are assignment operators?
 * What is the Unary Plus Operator?

How to run JavaScript Code
 - Most JS in the foundations Course will be run via the browser
 - The simplest way to get started is to create an HTML file with the JS code inside of it

 <!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Page Title</title>
</head>
<body>
  <script>
    // Your JavaScript goes here!
    console.log("Hello, World!")
  </script>
</body>
</html>

 - If you F12 the page and press console on the top, you should be able to see the output of our console.log statements
 - Another way to include JS in a webpage is through an external script
  - This is similar to linking external CSS docs to your website
   <script src="javascript.js"></script>
 - JS files have the extension .js

Variables
 - Think of variables as "storage containers" for data in your code
 - There are three ways to create a variable in JS:
  1. var
  2. let
  3. const
 - let and const are new ways to declare variables in JS
 - var and let does the same thing but we use let because var sometimes leads to some variables
 - example of how to use let:

  let message;
  message = 'Hello!';

  alert(message); // shows the variable content

 - Can declare multiple variables by:

  let user = 'John', age = 25, message = 'Hello';

 - Can simply mulitvariable usage by:

  let user = 'John';
  let age = 25;
  let message = 'Hello';

  let user = 'John',
    age = 25,
    message = 'Hello';

  let user = 'John'
    , age = 25
    , message = 'Hello';

Constants
 - To declare a constant (unchanging) varaibale, use const instead of let:

  const myBirthday = '18.04.1982';
  myBirthday = '01.01.2001'; // error, can't reassign the constant!

  Uppercase constants
   - There is a widespread practice to use constants as aliases to difficult-to-remember values that are known prior to execution
   - Example:
    
    const COLOR_RED = "#F00";
    const COLOR_GREEN = "#0F0";
    const COLOR_BLUE = "#00F";
    const COLOR_ORANGE = "#FF7F00";

    // ...when we need to pick a color
    let color = COLOR_ORANGE;
    alert(color); // #FF7F00


Numbers/Symbols
 - +	Addition
 - -	Subtraction
 - *	Multiplication
 - ** Exponentiation (ES2016)
 - /	Division
 - %	Modulus (Remainder)
 - ++ Increment
 - -- Decrement

 - Numbers can be written with or without decimals
  x = 3.14
  y = 3
 - Extra large or extra small numbers can be written with scientific notation
  x = 123e5 // 12300000
 - JS numbers are always 64-bit floating poinit
 - Integers are accurate up to 15 digits
  let x = 999999999999999;   // x will be 999999999999999
  let y = 9999999999999999;  // y will be 10000000000000000

 - If you add two numbers, the result will be a number
  let x = 10;
  let y = 20;
  let z = x + y; //30
 - If you add two strings, the result will be a string concatenation
  let x = "10";
  let y = "20";
  let z = x + y; //1020
 - If you add a number and a string, the result will be a string concatenation (vice versa)
  let x = 10;
  let y = "20";
  let z = x + y; //1020
 - JS will try to convert strings to numbers in all numeric operations
  let x = "100";
  let y = "10";
  let z = x / y; //10
 - + is used to concatenate if strings and numbers are used
 - NaN is used to describe the a number is not a legal number
  let x = 100 / "Apple"; //NaN
  - NaN is a number