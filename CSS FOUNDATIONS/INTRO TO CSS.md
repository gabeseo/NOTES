INTRODUCTION
 - CSS is able to make the structure you made with HTML have some stype

LESSON OVERVIEW
 * Add styles to HTML with CSS
 * Understand how to use the class and ID attributes
 * Add styles to specific elements using the correct selectors

Basic syntax
 - CSS is made up of various rules: a selector and semicolon-separated list of declarations, with each of those declarations being made up of a property-value pair
  - selector {property:value;}
  - div.bold-text {font-weight:700;}
   - A <div> is an empty container


Selectors
 - Selectors refer to the HTML elements to which CSS rules apply (what is being selected)

 Universal Selector
  - The universal selector will select elements of any type, hence the name "universal" and the syntax for it is a simple asterick

   - * {
       color: purple;
      }

 Type Selectors
  - A type selector (or element selector) will select all elements of the given element type, and the syntax is just the name of the element:

   - <!-- index.html -->
     <div>Hello, World!</div>
     <div>Hello again!</div>
     <p>Hi...</p>
     <div>Okay, bye.</div>

     /* styles.css */

     div {
        color:white;
     }
      - Here, all three <div> elements will be selected, while the <p> element wouldn't be

 Class selectors
  - Class selectors will select all elements with the given class, which is just an attribute you place on an HTML element. Here is how you add a class to an HTML tag and select it in CSS:

   <!-- index.html -->

   <div class="alert-text">Please agree to our terms and service.</div>

   /* styles.css */

   .alert-text {
     color: red;
   }

  - Note that the syntax for class selector is: a period immediately followed by the case-sensitive value of the class attribute
  - Another thing you can do with the class attribute is to add multiple classes to a single element as a space-separated list, such as: class="alert-text severe-alert"

 ID selectors
  - ID selectors are similar to class selectors where they can select an element with the given ID.
  Major difference between classes and IDs is that an element can only have one ID and it cannot be repeated on a single page and should nto contain any whitespace:

  <!-- index.html -->

  <div id="title">My Awesome 90's page</div>

  /* styles.css */

  #title {
    background-color: red;
  }
  
  - For IDs, instead of a period, we use a hashtag

 The grouping selector
  - What if we have two groups of elements that share some of their style declarations:

    .read {
    color: white;
    background-color: black;
    /* several unique declarations */
  }

  .unread {
    color: white;
    background-color: black;
    /* several unique declarations */
  }

  - Both our .read and .unread selectors share the color: white; and background color: black; declarations, but otherwise have several of their own unique declaration
   - To cut down on repetition, we can group these two selectors together as a comma-separated list:

  .read,
  .unread {
    color: white;
    background-color: black;
  }  

  .read {
    /* several unique declarations */
  }

  .unread {
    /* several unique declarations */
  }

  - Both of the examples will have the same result, but the second example reduces the repetition of declarations and makes it easier to edit either the color or background-color for both classes at once

 Chaining selectors
  - Another way to use selectors is to chain them as a list without any separation:

  <div>
  <div class="subsection header">Latest Posts</div>
  <p class="subsection preview">This is where a preview for a post might go.</p>
  </div>

  - We have two elements with the subsection class that have some sort of unique styles, but what if we only want to apply a separate rule to the element that also has header as a second class? We could chain both the class selectors together in our CSS like so:

  .subsection.header {
  color: red;
  }

  - What .subsection.header does is it selects any element that has both the subsection and header classes
  - There is no space between the .subsection and .header class selectors
   - This syntax basically works for chaining any combination of selectors except more than one type selector

  - This can be also used to chain a class and an ID like this:
    <div>
    <div class="subsection header">Latest Posts</div>
    <p class="subsection" id="preview">
      This is where a preview for a post might go.
    </p>
    </div>

  - You can take two elements above and combine them like this:
    .subsection.header {
    color: red;
    }

    .subsection#preview {
      color: blue;
    }

  - You can not chain more than one type of selector since an element cannot be two different types at once
   - Chaining two type selectors like div and p would give the selector divp, which would not work because the selector would try to find a literap <divp>, element which does not exist

 Descendant combinator
  - Combinators allow us to combine multiple selectors differently than either grouping or chaining them, as they show a relationship between the selectors
  - There are four different types of combinators in total
  - Descendant combinator is represented in CSS by a single space between selectors
   - A descendant combinator will only cause elements that match the last selector to be selected if they also have an ancestor that matches th eprevious selector

  - Something like .ancestor .child would select an element with the class child if it has an ancestor with the class ancestor
  - Another way to think of it is that child will only be selected if it is nested inside ancestor, regardless of how deep that nesting is
  - For example:

    <!-- index.html -->

    <div class="ancestor">
      <!-- A -->
      <div class="contents">
        <!-- B -->
        <div class="contents"><!-- C --></div>
      </div>
    </div>

    <div class="contents"></div>
    <!-- D -->

    /* styles.css */

    .ancestor .contents {
      /* some declarations */
    }

  - The first two elements (class B and C) would be selected but the last element (D) would not be selected

  - There is no limit to how many combinators you can add to a rule

Properties

 Color and background color
  - The color property sets an element's text color, while background-color sets the background color of an element
  - Both of these properties can accept one of several kind of values such as:
   1. Actual color names (red)
   2. Keywords (transparent)
   3. HEX, RGB, HSL values

 Typography basics and text-align
  - font-family can be a single value or comma-separated list of values that determine what font an element uses
   - Font family name ("Times New Roman")
   - Generic family name (Serif)
  - If a browser cannot find or does not support the first font in a list, it will use the next one
   - font-family:"Times New Roman", serif;
  - font-size changes the size of the font
   - font-size: 22px
  - font-weight affects the boldness of the text
   - font-weight: bold
   - font-weight: 700
    - numeric values will be increments of 100 up to 900
  - text align will align the text horizontally within an element
   - text-align: center

 Image height and width
  - By default, an <img> element's height and width values will be the same as the actual iamge file's height and width
  - You can use the value of "auto" for the height property and adjust the width value if you want to adjust the size of the image without losing its proportions:

   img {
    height: auto;
    width: 500px;
   }

Adding CSS to HTMl
 
 External CSS
  - External CSS is the most common method you will come across, and it involves creating a separate file for the CSS and linking it inside of an HTML's opening and closing <head> tags with a self-closing <link> element:

  <!-- index.html -->

  <head>
    <link rel="stylesheet" href="styles.css">
  </head>

  /* styles.css */

  div {
    color: white;
    background-color: black;
  }

  p {
    color: red;
  }
  
  - First, we add a self-closing <link> element inside of the opening and closing <head> tags of the HTML file
   - The href attribute is the location of the CSS file, either an absolute URL or a URL relative to the location of the HTML file
   - The rel attribute specifies the relationship between the HTML file and the linked file
  - Then, inside of the newly created styles.css file, we have the selector (div and p) followed by a pair of opening and closing curly braces, creating a "declaration block"
  - Finally, we place any declarations inside off the declaration block
   - color: white is one declaration (color being the property and white being the value, and background-color: black is another declaration)
  
  - Some pros to using an External CSS method:
   1. It keeps the HTML and CSS separated, resulting in the HTML file being smaller and making things look cleaner
   2. Only need to edit CSS in one place

 Internal CSS
  - Otherly called as embedded CSS involves adding the CSS within the HTML file itself instead of creating a separate file
  - With this style, you use opening and closing <style> tags, which are then placed inside of the opening and closing <head> tags of your HTML file
   - Since the styles are placed inside of the <head> tags, we no longer need the <link> element the external CSS method requires
  - Example:

    <head>
    <style>
      div {
        color: white;
        background-color: black;
      }

      p {
        color: red;
      }
    </style>
  </head>
  <body>
    ...
  </body>

 Inline CSS
  - Inline CSS makes it possible to add styles directly to HTML elements:

    <body>
    <div style="color: white; background-color: black;">...</div>
    </body>

  - We do not use any selectors here, since we are directing adding the styles to the <div> tags itself
  - We have the style= attribute, with its value within the pair of quotation marks being the declarations
  - This is usefull for adding a unique style for a single element