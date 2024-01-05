Comparisons
 - We know many comparison operators from maths
 - In JS they are written like this:
  - Greater/Less than: a > b, a < b
  - Greater/Less than or equals: a >= b, a <= b
  - Equals: a == b
  - Not equals: a != b

Boolean is the Result
 - All comparison operators return a boolean value
  - true means yes
  - false means no
 - A comparison value can be assigned to a variable, just like any value:
  let result = 5 > 4; //asign the result of the comparison
  alert( result ); //true

String Comparison
 - Strings are compared letter by letter

  alert( 'Z' > 'A'); //true
  alert('Glow' > 'Glee' ); //true
  alert( 'Bee' > 'Be'); //true

 - The algorithm to compare two strings is simple
  1. Compare the first char of both strings
  2. Compare the second char of both strings
  3. Repeat until end of either string
  4. If the same length, they are equal

Comparison of different types
 - When comparing values of different types, JS converts the values to numbers

  alert( '2' > 1); //true
  alert( '01' == 1); //true

 - FOr boolean values, true becomes 1 and false becomes 0

  alert( true == 1); //true
  alert(false == 0); //true

Strict Equality
 - A regular equality check == has a problem. It cannot differentiate 0 from false
 - This happens because operands of different types are converted to numbers by the equality operator ==
 - An empty string, just like false, becomes a zero
 - What do do if we want to differentiate 0 from false?
 A strict equality operator === checks the equality without type conversion
  - In other words, if a and b are of different types, then a === b immediately returns false without an attempt to try them

   alert( 0 === false ); // false, because the types are different

Comparison with null and undefined
 - For a strict equlity check ===:
  - These values are different, because each of them is a different type

   alert( null === undefined ); // false

 - For a non-strict check ==:
  - These two are a 'sweet couple': they equal each other, but not any other value

   alert( null == undefined ); // true

 - For maths and other comparisons: < > <= >=
  - null/undefined are converted to numbers: null becomes 0, while undefined becomes NaN.

Strange result: null vs 0

  alert( null > 0 );  // (1) false
  alert( null == 0 ); // (2) false
  alert( null >= 0 ); // (3) true

An incomparable undefined

  alert( undefined > 0 ); // false (1)
  alert( undefined < 0 ); // false (2)
  alert( undefined == 0 ); // false (3)