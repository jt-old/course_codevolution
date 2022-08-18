# CSS Grid Crash Course Notes

## What is CSS Grid

The CSS Grid Layout Module, simply known as CSS Grid or just Grid, is a two-dimensional grid-based layout system that is composed of 12 cells.

With rows and columns, Grid makes it easier ot design web apge layouts, align, and distribute space among items in a rid.

Flexbox is great for 1D layouts.

Grid is great for 2D layouts.

## Terminology

When you talk about CSS Grid, you are mainly talking about the parent container, which we call the Grid Container and the children elements, which we refer to as Grid Items.

A Grid Line is the horizontal or vertical dividing line in a grid. If the line is vertical, it is a column grid line. If the line is horizontal, it is a row grid line.

A Grid Cell is the smallest unit that you can have on a grid. It is the space between four intersecting grid lines.

A Grid Track is the space between two adjacent grid lines. It is denoted by the green space in the image.

The Grid Area is the total space surrounded by four grid lines. It may be composed of any number of grid cells. It is denoted by the purple space in the image.

## Grid Container Properties

There are 18 total grid container properties.

The 18 Grid Container Properties Are:

1. display
2. grid-template-columns
3. grid-template-rows
4. grid-template
5. column-gap
6. row-gap
7. gap
8. justify-items
9. align-items
10. place-items
11. justify-content
12. align-content
13. place-content
14. grid-auto-columns
15. grid-auto-rows
16. grid-auto-flow
17. grid-template-areas
18. grid

### display

Used to create either a block level or an inline level grid container.

Possible Values:

1. display: grid
2. displau: inline-grid

To create a grid container, we use a display property and set it to 'grid'. ie 'display: grid'

By default, display: grid creates a block level element. If you do not want a block level element, you can create an inline element by using 'display: inline-grid'

### grid-template-columns

Specifies the number of columns in the grid layout.

The valuyes are a space-separated list where each value specifies the size of the respective column.

ie using. 'grid-template-columns: 100px 200px 300px;'

creates three columns. Columnn 1 is 100 px, column 2 is 200px, and column 3 is 300px;

If you want equal sized columns, simply set the desired size repeatedly.

ie. 'grid-template-columns: 200px 200px 200px;'

#### repeat function

A better way to set a repeated size for multiple columns is the set the value to repeat and then declare the amount of times to be repeated and the size...

ie. 'grid-template-columns: repeat(3, 200px);'

It is also possible to set the width of the column as a fraction of the available space in the container by using 'fr'

ie. 'grid-template-columns: 1fr 2fr 1fr;'

In the example above, columns 1 and 3 would be given 25% of the space each and column 2 would be given 50% of the space.

#### minmax function

Another function that is useful with grid is the minmax function.

You can specify any amount of columns and apply a minmax

ie. 'grid-template-columns: repeat(3, minmax(200px, 1fr));'

The column should be at least 200px, but can grow to take up the free space if available. At 200px, the items would stop shrinking and start to overflow.

### grid-template-rows

Specifies the number of rows in a grid.

The values are basically the same as grid-template-rows, except now you can designate the height of the rows instead of the width (column size)

ie. grid-template-rows: 100px 150px 200px; - three rows with their corresponding heights.

ie. grid-template-rows: repeat(3, 100px) 200px; - three rows with a height of 100px and one row with a height of 200px. In this example, the fourth row ends up being blank space at the bottom that is occupied by the grid container.

#### repeat() and minmax()

Like grid-template-columns, you can also specify a repeat function and a minmax function for rows

### grid-template

A shorthand for defining Rows and Columns.

It is specified by 'grid-template: grid-template rows / grid-template-columns'

ie.
'grid-template-columns: repeat(3, minmax(200px, 1fr));'
'grid-template-rows: repeat(3, 1fr);'

Becomes

'grid-template: repeat(3, 1fr) / repeat(3, minmax(200px, 1fr));'

### column-gap

Sets the gap between the columns in the grid.

Values can be any non-negative value or a percentage

ie. 'column-gap: 20px;

### row-gap

Sets the gap between the rows in the grid.

Values can be any non-negative value or a percentage

ie. 'row-gap: 20px;

### gap

Shorthand for specifying the column-gap and the row-gap.

Values can be any non-negative value or a percentage

ie. 'gap: 20px 20px;'

### justify-items

Aligns items within a container along the row axis. Applies to all items within a container

Possible Values:

1. stretch - items will fill the cell
2. start - justifies items to the start of the cell
3. end - justifies items to the end of the cell
4. center - justifies items along the horizontal center

The default value of justify-items is 'stretch'

### align-items

Aligns items within a container along the vertical axis. Applies to all items within a container

Has a default value of 'stretch'

Possible Values:

1. stretch - items will fill the cell
2. start - justifies items to the start(top) of the cell
3. end - justifies items to the end(bottom) of the cell
4. center - justifies items along the vertical center

### place-items

Shorthand for specifying align-items and justify-items. Applies to all items within a container

Values can be any non-negative value or a percentage and any possible combination of align and justify.

The first value is for align-items and the second value is for justify-items

ie. 'place-items: start end;' - item will be placed at the start(top) of the cell and to the end(right) of the cell.

place-items can take a single value, in which case the value will be applied to both align-items and justify-items.

ie. 'place-items: center' will place items both horizontally and vertically within the cell.

### justify-content

Justifies content along the row axis (horizontal) with respect to the container

By default, justify-content is set to start.

Possible Values:

1. justify-content: start; - places items at the horizontal start
2. justify-content: end; - places items at the horizontal end
3. justify-content: center; - centers items horizontally
4. justify-content: stretch; - stretches content along the row axis
5. justify-content: space-between; - extra space is evenly split in between grid columns, excluding the start and end
6. justify-content: space-around; - extra space is evenly distributed between grid columns, and distribures half of the value to the start and end
7. justify-content: space-evenly; - extra space is evenly and equally distributed between the grid columns, including the start and end.

### align-content

Justifies content along the column axis (vertically) with respect to the container

By default, align-content is set to start.

Possible Values:

1. align-content: start; - places items at the vertical start (top)
2. align-content: end; - places items at the vertical end (bottom)
3. align-content: center; - centers items vertically
4. align-content: stretch; - stretches content along the column axis
5. align-content: space-between; - space is evenly distributed between the rows
6. align-content: space-around; - adds space at the start and the end that is equal to half of the space of the rows.
7. align-content: space-evenly; - adds equal space at the start, end, and between the rows of the container

### place-content

Shorthand for align-content and justify-content.

The first value is for align-content and the second value is for justify-content.

Values can be any possible combination of values for align and justify

ie. 'place-content: start end;' - places content at the start(top) of the container and to the end(right) of the container.

place-content can take a single value, in which case the value will be applied to both align-content and justify-content.

ie. 'place-content: center' will place the content both horizontally and vertically within the container.

### grid-auto-columns

Sets the default width for columns within the grid

Values can be pixels, percentages, minmax, and auto(default), etc.

### grid-auto-rows

Sets the default height for rows within the grid

Values can be pixels, percentages, minmax, and auto(default), etc.

### grid-auto-flow

Controls how auto-placed items get inserted into the grid.

The default value is 'row'

Potential Values:

1. grid-auto-flow: row;
2. grid-auto-flow: column;
3. grid-auto-flow: dense;
4. grid-auto-flow: row dense;
5. grid-auto-flow: column dense

### grid-template-areas

Used to specifies areas within the grid layout

### grid

Shorthand for grid-template-rows, grid-template-columns, grid-template-areas, grid-auto-rows, grid-auto-columns, and grid-auto-flow

## Grid Item Properties

1. grid-column-start
2. grid-column end
3. grid-column
4. grid-row-start
5. grid-row-end
6. grid-row
7. justify-self
8. align-self
9. place-self

### grid-column-start

Controls on which grid column the content starts.

ie.
grid-column-start: 1; - content begins on grid line 1

### grid-column-end

Controls on which grid column the content ends

ie.
grid-column-end: 3; - content ends on grid line 3

You can also specify a span instead, meaning the column must span however many columns you specify.

ie.
grid-column-end: span 2; - content spans 2 columns.

This is the same as telling it to end on grid line 3.

### grid-column

Shorthand for grid-column-start and grid-column-end

ie.
grid-column: 1 / span 2; - content will begin on column 1 and span 2 columns

### grid-row-start

Controls on which grid row the content starts

ie.
grid-row-start: 1;

### grid-row-end

Controls on which grid row the content ends

ie.
grid-row-end: 3;

You can also specify a span instead, meaning the row must span however many rows you specify.

ie.
grid-row-end: span 2; - content spans 2 rows.

### grid-row

Shorthand for grid-row-start and grid-row-end

grid-row: 1 / span 2; - content will begin on row 1 and span 2 rows.

### justify-self

Deals with the horizontal alignment of a single item along the row axis

By default, the value is 'stretch'

Possible Values:

1. justify-self: start;
2. justify-self: end;
3. justify-self: center;
4. justify-self: stretch;

### align-self

Deals with the vertical alignment of a single item along the column axis

By default, the value is 'stretch'

Possible Values:

1. justify-self: start;
2. justify-self: end;
3. justify-self: center;
4. justify-self: stretch;

### place-self

Shorthand for align-self and justify-self

By default, the values are 'place-self: stretch stretch'

ie.
place-self: start end; - the item will be placed at the column start(top) and the row end(right)

place-self can take a single value, in which case the value will be applied to both align-self and justify-self.

ie.

place-self: center; - will center the item along the column and row axis.
