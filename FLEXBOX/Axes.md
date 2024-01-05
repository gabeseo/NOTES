Introduction
 - See how the orientation of items within a flex container can be controlled using the flex-direction property

Lesson overview
 * You'll learn about the 2 axes of a flex container
 * You'll learn how to change those axes to arrange your content in columns instead of rows
 - Confusing thing about flexbox is that it can work either horizontally or vertically, and some rules change a bit depending on which direction you are working with
 - The default direction for a flex container is horizontal (or row) but you can change the direction to vertical (or column)

 .flex-container{
    flex-direction:column;
 }

Axes
 - No matter which direction you are using, you need to think of your flex-conteiners as having 2 axes: main axis and cross axis
  - It is the direction of these axes that changes when the flex-direction is changed
 - In most circumstances, flex-drection row puts the main axis horizontal, and column muts the main axis vertical
 - flex-direction: column does not work as intended if we use the shorthand flex: 1
  - The divs collapse, even though they have a height defined
  - This is because the flex shorthand expands flex-basis to 0, meaning that all flex-grow and flex-shrink starts their calc from 0 
  - Empty divs by default have 0 height
 - This example is fixed by specifying flex: 1 1 auto, telling the flex items to default to ehir given height
  - We could have given a height to the parent .flex-container, or use flex-grow instead
 - When the direction is changed from rows to columns, flex-basis refers to to the width as height