Introduction
 - Flex is also useful for arranging items that have a specific size

Lesson overview
 * Learn how to align items inside a flex container both vertically and horizontally

Alignment

<div class="container">
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
</div>

 .container {
  height: 140px;
  padding: 16px;
  background: plum;
  border: 4px solid indigo;
  display: flex;
}

.item {
  width: 60px;
  height: 60px;
  border: 4px solid darkslategray;
  background: skyblue;
}

 - For the above code, if we put flex: 1, the three items fill up the the horizontal space the container is emcompassing
 - If we wanted them to stay the same width but distribute them differently inside the container, we can use justify-content: space between to the .container
 - Justify-content aligns items across the main axis
 - To change the placement of items along the cross axis, use align-items
  - align-items: center aligns the items in the container to the center
 - Because justify-content and align-items are based on the main and cross axis of the container, their behavior changes when you change the flex-direction of a flex-container
  - i.e. When you change the flex-direction to column, justify-content aligns veritally and align-items aligns horizontally

Gap
 - Setting gap on a flex container simply adds a specified space between flex items, similar to adding a margin to the items themselves