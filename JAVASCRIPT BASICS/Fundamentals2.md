Lesson Overview
 * Name the eight data types in JavaScript.
 * Understand the difference between single, double, and backtick quotes.
 * Embed a variable/expression in a string.
 * Understand what a method is.
 * Name the three logical operators.
 * Understand what the comparison operators are.
 * Understand what conditionals are.
 * Understand what nesting is.
 * Understand what truthy and falsy values are.

Data Types
 - There are eight basic data types in JS

 Number
  - A number type represents both integer and floating point numbers
  - There are many operations for numbers (previous lesson)
  - There are special numeric values that are in the data type
   1. Infinity
    alert(1/0); // Infinity
   2. -Infinity
   3. NaN
    alert("not a number" / 2); //NaN, such division is erroneous
    alert( NaN + 1 ); // NaN
    alert( 3 * NaN ); // NaN
    alert( "not a number" / 2 - 1 ); // NaN

 BigInt
  - In JS, the numbertype cannot safely represent integer values larger than (2e53-1) or smaller than -(2e53-1)
   console.log(9007199254740991 + 1); // 9007199254740992
   console.log(9007199254740991 + 2); // 9007199254740992
  - All other digits that does not get fixed into the 64-bit storage get approximated
  - A BigInt value is created by appending n to the end of an integer
   // the "n" at the end means it's a BigInt
   const bigInt = 1234567890123456789012345678901234567890n;

 String
  - A string in JS is surrounded by quotes
  - Three type of quotes that can be used: " ' `
  - Single and ouble quotes are just simple quotes and there are no differences between them
  - Backticks are "extended functionality" quotes that allow us to embed variables and expressions into a string by wrapping them in ${...}
   
   let firstname = "John";
   let lastname = "Doe";

   // embed a variable
   alert( `Hello, ${firstname}!` ); // Hello, John!

   // embed two variables
   alert( 'Hello, ${firstname} ${lastname} )

   // embed an expression
   alert( `the result is ${1 + 2}` ); // the result is 3

 Boolean
  - Boolean types only has two values: true and false
  - They are used to store yes/no values

 Null Value
  - The null value only containss null
  - null is not a reference to a non-existing object like on some other languages
  - Literally means nothing (unknown, empty, value unknown)

 Undefined Value
  - Means the value is not assigned
  - If a variable is declared but not assigned, the value is undefined

 Objects and Symbols
  - All other types are called primitive because their values can contain only a single string but objects are used to store collections of data and more complex entities
  - The symbol type is used to create unique identifiers for object

 The typeof operator
  - The typeof operator returns the type of operand
   - Useful when we want to process values of different types differently or just want to do a quick jectk

   typeof undefined // "undefined"

   typeof 0 // "number"

   typeof 10n // "bigint"

   typeof true // "boolean"

   typeof "foo" // "string"

   typeof Symbol("id") // "symbol"

   typeof Math // "object"  (1)

   typeof null // "object"  (2)

   typeof alert // "function"  (3)
  - Math is a built-in object that providees mathematical operations
  - The typeof alert is a function because alert is a function