Introduction
 - What does flex: 1; do?

Lesson Overview
 * Learn the 3 properties that are defined by the flex shorthand, and how to use them individually

Flex shorthand
 - The flex declaration is a shorthand for 3 properties that you can set on a flex item:
  1. flex-grow
  2. flex-shrink
  3. flex-basis
 - flex: 1 equates to flex-grow: 1, flex-shrink: 1, flex-basis: 0

Flex-grow
 - flex-grow expects a single number as its value and that number is used as the flex-item's growth factor
 - When we applied flex: 1 to every div inside our container, we were telling every div to grow the same amount
 - If we instead add flex: 2 to just one of the divs, then that div would grow to 2x the size of others

<!-- html -->
<div class="flex-container">
  <div class="one"></div>
  <div class="two"></div>
  <div class="three"></div>
</div>

/* css */
.flex-container {
  display: flex;
}

/* this selector selects all divs inside of .flex-container */
.flex-container div {
  background: peachpuff;
  border: 4px solid brown;
  height: 100px;
  flex: 1 1 0%;
}

/* only div.two is selected here */
.flex-container .two {
  flex: 2 1 0%;
}

Flex-shrink
 - flex-shrink is similar to flex-grow, but it sets the shrink factor of a flex item
 - flex-shrink only ends up being applied if the size of all flex items is larger than their parent container
  - i.e. 3 divs had a width declaration like: width:100px, and .flex-container was smaller than 300px, our divs would have to shrink to fit
 - The default shrink factor is flex-shrink: 1; meaning all items will shrink evenly
 - If you do not want to shrink an item, you specify it to flex-shrink: 0

.flex-container {
  display: flex;
}

/* this selector selects all divs inside of .flex-container */
.flex-container div {
  background: peachpuff;
  border: 4px solid brown;
  height: 100px;
  width: 250px;
  flex: 1 1 auto;
}

.flex-container .two {
  flex-shrink: 0;
}

 - This will make the second flex container never gets smaller than the given width of 250px, even though flex-grow says each element should be equally sized
 - When you specify flex-grow or flex-shrink, flex items do not necessarily respect the given values for width
 - In the above example, even though all 3 devs are given a width of 250px, when their parent is big enough, they will grow to fill it (vice versa for if the parent is too small)

Flex basis
 - flex-basis sets the initial size of a flex item so that any flex-grow or flex-shrink starts from that baseline size
 - Defualt is 0%
  - The reason we had to change it to auto in flex-shrink is because when the basis is set to 0, the items would ignore the item's width, and everything would shrink evenly
  - Using auto tells the item to check for a width declaration (width:250px)
 - flex-basis sets the value of of basis to auto but if you specify flex: 1, it interprets that as flex: 1 1 0%