Logical Operators
 - There are four logical operators in JS: || (OR), &&(And), !(NOT), ??(Nullish Coalescing)

 OR ||
  - OR is meant to manipulate boolean values only
  - If any of it arguments are true, it returns true, otherwise it returns false

   alert( true || true );   // true
   alert( false || true );  // true
   alert( true || false );  // true
   alert( false || false ); // false

   if (1 || 0) { // works just like if( true || false )
   alert( 'truthy!' );
   }
  
  - Most of the time, OR || is used in an if statement to test if any of the given conditions is true

   let hour = 12;
   let isWeekend = true;

   if (hour < 10 || hour > 18 || isWeekend) {
     alert( 'The office is closed.' ); // it is the weekend
   }

  OR "||" finds the first truthy value
   - Given multiple OR values:
    result = value1 || value 2 || value 3;
   - The OR operator does the following:
    1. Evaluates operands from left to right
    2. For each operand, converts it into boolean. If it returns true, it stops and returns the original value of that operand
    3. If all operands have to be evaluated, returns the last operand
   - In other words, a chain of OR returns the first truthy value or the last one if no truthy value is found

    alert( 1 || 0 ); // 1 (1 is truthy)

    alert( null || 1 ); // 1 (1 is the first truthy value)
    alert( null || 0 || 1 ); // 1 (the first truthy value)

    alert( undefined || null || 0 ); // 0 (all falsy, returns the last value)

    Getting the first truthy value from a list of variables or expressions
     - For example, we have firstName, lastName, and nickNae variables, all optional
     - We use the OR to choose the one that has the data and show it

      let firstName = "";
      let lastName = "";
      let nickName = "SuperCoder";

      alert( firstName || lastName || nickName || "Anonymous"); // SuperCoder
    
    Short-circuit evaluation
     - Another feature of OR operator is the so-called short-circuit evaluation
     - Means that || processes its arguments until the first truthy value is reached, and then the value is returned immediately, without even touching the other argument
     - This is important if the operand isn't a value, but an expression with a side effect, such as a variable assignment or a function call
     
      true || alert("not printed");
      false || alert("printed");

       - In the first line, the OR operator stop the evaluation immediately upon seeing true, so the alert isn't run
       - This makes only the second line print

 AND &&
  - AND returns true if both operands are truthy and false otherwise

   alert( true && true );   // true
   alert( false && true );  // false
   alert( true && false );  // false
   alert( false && false ); // false
  
  - An example with if:

   let hour = 12;
   let minute = 30;

   if (hour == 12 && minute == 30) {
     alert( 'The time is 12:30' );
   }
  
  - Just like OR, any value is allowed as an operand of AND:
   if (1 && 0) { // evaluated as true && false
     alert( "won't work, because the result is falsy" );
   }
  
  And && finds the first falsy value
   - The AND && operator does the following
    1. Evaluates operands from left to right
    2. For each operand, converts it into a boolean. If the result is false, stops and returns the original value of that operand
    3. If all operands have been evaluated, returns the last operand
  - In other words, AND returns the first falsy value or the last value if none was found

   // if the first operand is truthy,
   // AND returns the second operand:
   alert( 1 && 0 ); // 0
   alert( 1 && 5 ); // 5

   // if the first operand is falsy,
   // AND returns it. The second operand is ignored
   alert( null && 5 ); // null
   alert( 0 && "no matter what" ); // 0
  
  - Can pass several values in a row:

   alert( 1 && 2 && null && 3 ); // null
  
  - When all values are truthy, the last value is returned:

   alert( 1 && 2 && 3 ); // 3, the last one

  - The precedence of && is higher than ||
   a && b || c && d is the same as (a && b) || (a && b)

 NOT !
 - The operator accepts a single argument and does the following:
  1. Converts the operand to boolean type
  2. Reverses the inverse value
 - For example:

  alert( !true ); // false
  alert( !0 ); // true

 - A double NOT !! is sometimes used for converting a value to boolean type:

  alert( !!"non-empty string" ); // true
  alert( !!null ); // false

   - The first NOT converts the value to boolean and returns the invers, and the second NOT inverses it again
    - We have a plain value-to-boolean conversion
   - A built-in Boolean function:

  alert( Boolean("non-empty string") ); // true
  alert( Boolean(null) ); // false

   - The precedence of NOT ! is the highest of all logical operators, so it executes first before && or ||