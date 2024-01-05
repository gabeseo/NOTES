Lesson Overview
 * How to define and invoke different kinds of functions
 * How to use the return value
 * What function scope is

Functions - Reusable blocks of code
 - Functions allow you to store a piece of code that does a singel task inside a defined block, and then call that code whenever you need it

Where do I find functions
 - Anything that features a pair of parentheses (), you are using a function

Built-in browser functions
 - Can use to manipulate a text-string

  const myText = "I am a string";
  const newString = myText.replace("string", "sausage");
  console.log(newString);
  // the replace() string function takes a source string, and a target string and replaces the source string, with the target string, and returns the newly formed string

 - Can use to manipulate an array

  const myArray = ["I", "love", "chocolate", "frogs"];
  const madeAString = myArray.join(" ");
  console.log(madeAString);
  // the join() function takes an array, joins all the array items together into a single string, and returns this new string

 - Can use to generate a random number

  const myNumber = Math.random();

Functions versus methods
 - Functions that are part of objects are called methods
 - There are built-in functions and built-in methods available to use
 - Custom functions are functions defined in the code, not the browser
  - Anytime there is a custom name with a parentheses straight after it

Invoking functions
 - To use a function after it has been defined, you ahve to run (invoke) it by including the name of the function in the code somewhere else, bollowed by parenthesis
  
  function myFunction() {
    alert("hello");
  }

  myFunction();
  // calls the function once

Function Parameters
 - Some function require parameters (values that need to be included inside the function parenthesis) to be specified when you are invoking them
 - i.e. The browser's built-in Math.random() function does not require any parameters. When it is called, it always returns a random number between 0 and 1
  
  const myNumber = Math.random();
 
 - i.e. The browser's built-in replace() function needs two parameter - the substring to find the main string, and the substring to replace the string with

  const myText = "I am a string";
  const newString = myText.replace("string", "sausage");

Optional parameters
 - Parameter are optional as you do not have to specify them because the fuction will adopt some kind if default behavior
 - The join() function's parameters("") from earlier is an example

Default parameters
 - You can specify default values of parameters in a function, you use the = sign after the name of the parameter

Anonymous functions and arrow function
 - Anonymous functions have no name and is often seen when a function expects to receive another function as a parameter

  (function () {
    alert("hello");
  });

Arrow functions
 - Another alternative form instead of anon functions are arrow functions called an arrow function
 - Instead of function(event), you write (event) =>

  textBox.addEventListener("keydown", (event) => {
  console.log(`You pressed "${event.key}".`);
  });

 - If the function takes only one parameter, you can omit the parentheses around the parameter (can take out the () around event in the above ex)
 - If your function contains only one line that is a return statement, you can omit the braces and the return keyword and implicityly return the expression

  const originals = [1, 2, 3];
  const doubled = originals.map(item => item * 2);
  console.log(doubled); // [2, 4, 6]

Function scope and conflicts
 - When you create a function, the varibales and other things defined inside the function are inside their own separate scope, meaning that they are locked away in their own separate compartments
 - The top level outside all your functions is called the global scope (Values in the global scope are accessible everywhere in the code)