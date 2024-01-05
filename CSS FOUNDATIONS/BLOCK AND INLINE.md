Introduction
 - We can modify the box calculation by changing the display property
 - Css has two box types: block and inline
 - The display property controls how HTML elements appear on the webpage

Lesson overview
 * You'll learn about "Normal Flow"
 * Learn the difference between block and inline elements
 * Learn which elements default to block and which elements default to inline
 * Lean what divs and spans are

Block vs inline
 - Most of the elements that we learned thus far are block elements (default style is display:block)
 - Inline elements do not start on a new line
  - They appear in line with whatever elements they are placed beside (i.e. <a> tag)
  - Padding and margin behave differently on inline elements
 
 The middle ground inline-block
  - Inline-block behave like inline elements, but with block-style padding and margin
  - Display: inline-block is a useful tool

Divs and spans
 - Having elements like <div> and <span> is useful even though they do not mean anything
  - We need eleements that serve no other purpose than to be "hook" elements
  - We can group related elements under one parent element to correctly position them on the page
  - We can give an id or a class to target them for styling with CSS
 - Div is a block-level element by default so it also allows us to divide the page into different blocks and apply styling to those blocks
 - Span is an inline-level element by deafulat so it is used to group text content and inline HTML elements for styling