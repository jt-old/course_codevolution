# CSS Flexbox Crash Course Notes

[CSS Flexbox Crash Course](https://www.youtube.com/watch?v=z62f2k38s64&list=PLC3y8-rFHvwhuX4qGvFx-wPy_MEi6Jdp7&index=3)

Timestamps
00:00 Introduction
00:28 Before we begin
02:01 What is Flebox?
04:00 Terminology
06:16 Flex container properties
08:01 Setup
10:06 display
12:13 flex-direction
15:01 flex-wrap
19:37 flex-flow
21:23 gap properties
23:22 justify-content
28:13 align-items
32:28 align-content
36:36 Flex item properties
37:46 order
40:12 flex-grow
44:16 flex-shrink
47:58 flex-basis
50:37 flex
52:05 align-self

## What is Flexbox

The CSS Flexible Box Module or simply known as Flexbox is a one-dimensional layout model

It allows you to design felixble nad efficient layouts, align and distribute space among items in a container

Flexbox helps you arrange elements in a webpage with ease.

Flexbox provides a lot of flexibility to arrange items, adjust spacing, adjsut alignment, and adjust the order of items.

Before flexbox, there were four layout modes.

1. Block, for sections in a webpage
2. Inline, for text
3. Table, for two-dimensional table data
4. Positioned, for explicit position of an element

## Terminology

When you talk a out flex box, you mainly have two entities, a parent container, which we refer to as flex-container and the immediately children, which we refer to as flex-elements.

## Flex Axes

You deal with two axes with flexbox:

1. Main Axis

   - Runs left to right by default
     - The startpoint of the main axis is termed Main Start
     - The endpoint of the main axis is termed Main End
     - The length from main start to main end is called the Main Size.
     - Flex items flow from main start to main end and take up the main size as the length

1. Cross Axis
   - Runs top to bottom by default
     - The startpoint of the main axis is termed Cross Start
     - The endpoint of the main axis is termed Cross End
     - The length from main start to main end is called the Cross Size.

You can change the direction of the main and cross axes by changing how the items are laid out in the container.

## Flex Container Properties

There are ten total flex container properties

1. Display - this is what defines a flex container and is mandatory in order to work with flexbox.
2. flex-direction - it defines the direction in which the flex items are placed within the container
3. flex-wrap - used to control the wrapping of items within the container
4. flex-flow - shorthand for the combination of flex-direction and flex-wrap
5. column-gap - sets the gap between columns
6. row-gap - sets the gap between rows
7. gap - shorthand for setting gap between column and rows
8. justify-content - defines the alignment of the items along the main axis
9. align-items - defines how flex-items are laid out along the cross axis
10. align-content - similar to justify-content, but this will align along the cross axis and not the main axis. This works ony when there are multiple flex rows within the container.

---

### display

Display creates either a block level or and inline container. The possible values are 'display: flex' or 'display: inline-flex'

On the container class, we set the display: flex;

As with all properties with CSS, some initial values are defined. When creating a flex container, all of the contained flex items behave in a certain way.

First, they will display in a row.

Second, items start from the beginning of the left axis, the left most axis, but do not stretch to the end. However, they can shrink to a certain extent

Third, items will stretch to fill the cross axis, from the top to the bottom.

Also, from the border, the container itself has 100% width, so it does behave similar to a block level element. If you do not want a block level flex container, you can set the flex proeprty to inline-flex and create an inline flex container.

After setting the property to inline-flex, the border wraps around the container instead of filling the full width to accomodate its children.

### flex-direction

Flex Direction establsihes the main axis, which in turn decides how the flex items are placed within the container.

By default, the main access flows from left to right, which is the reason why the initial items are placed from left to right in the browser.

By changing the direction of the flex property, we can change the order of the flex items displayed

There are four possible values for flex-direction:

1. flex-direction: row; - This is the default value. Items flow from left to right
2. flex-direction: row-reverse; - Sets the row items in a row, reversed.
3. flex-direction: column; - Sets the main access from top to bottom. The items will be stacked on top of each other.
4. flex-direction: column-reverse - stacks items in a column in the reverse order.

### flex-wrap

There are three possible valus for flex-wrap

1. flex-wrap: nowrap; - This is the default value.
2. flex-wrap: wrap; - The values of the container will wrap/unwrap as you decrease/increase the viewport size. Wrapping takes place only when needed.
3. flex-wrap: wrap-reverse; - Instead of items falling into the row below, they climb from the end up into the row above.

Vertical wrapping of items is also possible. For that, we need to change flex-direction to column and add a height to the flex container.

### flex-flow

Flex flow is a short hand for both flex-direction and flex-wrap. The first value is the flex-direction and the second direction is the flex-wrap.

ie. flex-flow: 'flex-direction''flex-wrap';

By default, the flex-flow is set to row and nowrap, which are the default values of each of the indvidual properties.

You can type any possible combination of the direction and wrap values and the container will adjust.

### column-gap

Sets the gap between columns.

Values can be a non-negative value or a percentage.

ex. column-gap: 20px;

gives a gap of 20px to the columns.

### row-gap

Sets the gap between rows.

Values can be a non-negative value or a percentage.

ex. row-gap: 20px;

gives a gap of 20px to the rows.

### gap

Gap is shorthad for row-gap and column-gap. The first value is row-gap and the second value is column-gap.

ie. gap: 'row-gap''column-gap'

Values can be a non-negative value or a percentage.

You can type any possible combination of the row and column gap values and the container will adjust.

## Aligment-Based Properties

### justify-content

Defines the content along the main axis. Used to align items and distribute any extra spacing in the parent container.

Possible Values:

1. justify-content: flex-start; - By default, justify-content is set to the value flex-start, which places the flex items at the beginning of the main axis, which is also knonw as 'main start'.
2. justify-content: flex-end; - Causes the flex items to be placed at the end of the main axis, which is also known as 'main end'
3. justify-content: center; - Causes the flex items to be placed at the cneter of the main axis.
4. justify-content: space-between; - evenly distributes the extra space within the container between the flex items.
5. justify-content: space-around; - evenly distributes the extra space within the container between the flex items and gives a space that is half of the space that's between the items to the start and end.
6. justify-content: space-evenly; - even distributes the extra space within the container between the flex items and gives equal space to the start and end.

### align-items

Align Items defines the default behavior for how flex items are laid out across the cross axis of the container. It works just like justify-content, but in the perpendicular position.

To visualize the changes, you need a height on the container.

Possible Values:

1. align-items: stretch; - By default, the value of align-items is stretch. This means that items stretch the entire length of the cross axis.
2. align-items: flex-start; - All items will be pushed to the cross start, which is the starting point of the cross axis.
3. align-itens: flex-end; - All items will be pushed to the botto of the container, which is the cross end, the ending point of the cross axis.
4. align-items: center; - Places the items at the center of the cross axis.
5. align-items: baseline; - The baseline upon which content sits.

### align-content

The align content propety aligns lines of content along the cross axis, similar to how justify-content justifies content along the main axis.

A very important condition is that multiple lines or rows must exist within the container, otherwise the property doesn't have any effect.

First, make sure to have a height on the container and also enable wrapping of items.

Possible Values:

1. align-content: stretch; - By default, the value of align-content is stretch.
2. align-content: flex-start; - This pulls the rows to the beginning of the cross axis.
3. align-content: flex-end; - Pushes the content to the end of the cross axis.
4. align-content: center; - Center aligns the content
5. align-content: space-between: - Distributes vertical space between rows
6. align-content: space-around: - distributes the space around the lines. The center portion has twice the amount of space as the top and bottom edges.

## Flex Item Properties

1. order - controls the order in which the items appear in the flex container
2. flex-grow - defines the ability for a flex item to grow if necessary
3. flex-shrink - defines the ability for a flex item to shrink if necessary
4. flex-basis - specififes the initial main size of a flex item
5. flex - shorthand for flex-grow, flex-shrink and flex-basis
6. align-align

### order

Order is an integer value used to determine the order in which items appear.

By default, the order of all flex items is 0. You can change the order in which items appear on screen by using 'order: number', ie. 'order: 1', 'order: 2', etc.

If you specify the same order number for two or more items, the items will appear in the order in which they appear in the source code.

### flex-grow

Flex-grow specificies what amount of space inside a container the item should take up if necessary. It is always relative to the other children within the flex container.

By default, all flex iems have a value of 0 and only take up the amount of space required to fit the content.

ex. 'flex-grow: 0;', 'flex-grow: 1;'. 'flex-grow: 3;' etc.

If you want all of te items to grow to take up the extra space evenly, you simply add flex-grow: 1 for all items.

### flex-shrink

Flex shrink defines the ability for a flex item t shrink if necessary.

Unlike flex-grow, the default value for flex-shrink is 1 on every item.

### flex-basis

Specificies the inital size of a flex item before the extra space in the container is distributed. This is used in place of the width property in flex layouts.

It can accept values such as: pixels, percentages, values, rem, or even keywords like auto.

By default, flex-basis has a value of auto.

flex-grow and flex-shrink apply on top of flex-basis.

For example, if you set flex-grow: 1 on item 1, the extra space is added on top of the 200 px.

Flex-box doesn't try to decrease its growth just because it is larger than the other items to begin with.

### flex

Flex is shorthand for flex-grow, flex-shrink, and flex-basis.

Although you can designate grow, shrink and basis individually, Flex is the recommended method.

By default, flex has a value of 'flex: 0 1 auto;', meaning the items will no grow to fit the container, the items will shrink if necessary, and that the width of the items depends on the content.

The flex property can be specified using one, two or three of the values.

ie.
.item{
flex-grow: 2;
flex-shrink: 5;
flex-basis: 200;
}

You can shorthand the above by using:

.item {
flex: 2 5 200px;
}

Other examples:

flex: 2;
flex: 10em;
flex: 30px;
flex: 1 30px;
flex: 2 2;
flex: 2 2 10%;
etc...

### align-self

Used to control the alignment of individual items.

The default value for align-self is auto.

Align-self is computed off of the align-items property of the parent container. align-self overides the align-items value fo the flex container.

The values are pretty much the same as the values for align-items.

align-self: flex-start; - the item will be pushed to the beginning of the cross axis
align-self: flex-end; - the item will be pushed to the end of the cross axis
align-self: center; - the item will be centered within the cross axis.
align-self: stretch; - The item will be stretch across the cross axis.
