Lesson Overview
 * What the cascade does
 * Specificity and combining CSS selectors
 * How inheritance affects certain properties

The cascade of CSS
 - CSS does what we tell it to do except the default styles provided by the browser
  - The default styles vary from browser to browser, and they are why some elements create a large "gap" between themselves and other elements, or why buttoms look the way they do, despite us not writing any CSS rules to style them that way
 - The cascade is what determines which rules actually get applied to our HTML

 Specificity
  - A CSS declaration that is more specific will take precedence over less specific ones
   - i.e. inline styles have the highest specificity compared to selectors
  - We are going to talk about:
   1. ID selectors (most specific selector)
   2. Class selectors
   3. Type selectors
  - Specificity will only take place when an element has multiple declarations atrgeting it
   - ID selector will beat any class selector, a class selector will beat any type selector, and a type selector will beat any less specific selectors
  - Example:

  <!-- index.html -->

  <div class="main">
    <div class="list subsection">Red text</div>
  </div>

  /* rule 1 */
  .subsection {
    color: blue;
  }

  /* rule 2 */
  .main .list {
  color: red;
  }

  - Rule 2 is more specific, so the color: red declaration takes precedence
  - Example 2:

  <!-- index.html -->

  <div class="main">
    <div class="list" id="subsection">Blue text</div>
  </div>
  
  /* rule 1 */
  #subsection {
    color: blue;
  }

  /* rule 2 */
  .main .list {
    color: red;
  }

  - Even though rule 2 has more class selectors than ID selectors, rule 1 is more specific because ID beats class
  - Example 3:

  <!-- index.html -->

<div class="main">
  <div class="list" id="subsection">Red text on yellow background</div>
  </div>
  /* rule 1 */
  #subsection {
    background-color: yellow;
    color: blue;
  }

  /* rule 2 */
  .main #subsection {
   color: red;
  }
  - Neither rule is using a more specific selector than the other but rule 2 has more selectors in use, so rule 2 has higher specificity

  - Symbols (+, *, ~, >, empty space) do not add any specificity

 Inheritance
  - Inheritance refers to certain CSS properties that, when applied to an element, are imherited by that element's descendants, even if we do not explicitly write a rule
  - Typography-based properties (color, font-size, font-family, etc.) are usually inherited, while most other properties are not
  - Exception is when directly targeting an element, as this always beats inheritance:
   <!-- index.html -->

   <div id="parent">
     <div class="child"></div>
   </div>
   /* styles.css */

   #parent {
     color: red;
   }

   .child {
     color: blue;
   }

   - Despite the parent element having a higher specificity with an ID, the child element would have the color: blue style applied since that declaration directly targets it, while color: red from the parent is only inherited

 Rule Order
  - The final factor (tie of ties)!!
  - Whichever rule was LAST defined is the winner
  - Example:

   /* styles.css */

   .alert {
     color: red;
   }

   .warning {
     color: yellow;
   }
  - It is yellow because it was the last one defined