# css-grid
Wes Bos CSS Grid Course
https://cssgrid.io/

## Lesson 03
Learned grid fundamentals, using **grid-template-columns/rows, grid-gap**.

## Lesson 04
Learned how to use the developer tools in Firefox to enable viewing the grid.

## Lesson 05
Learned the difference between grid explicit and implicit tracks. 
**Explicit grid** tracks are tracks that are user defined and can be distinguished by a solid black line.
**Implicit grid** tracks are tracks that are created when the user defines less columns/rows that do not contain the entire content. These tracks ca be distinguished by a small dotted line.

## Lesson 06
Learned about **grid auto** property and it's behavior.

## Lesson 07
Learned about the **fr** type to set for width of columns/rows. Fr can be read as Free Space as it looks at the remaining free space in the grid and divides it amongst the columns/rows. Setting `grid-template-columns: 1fr 2fr` creates two columns, where the second column takes up twice the space of the first.

## Lesson 08
Learned about **grid repeat** function. Can be used in the following manner : `grid-template-columns/rows : repeat(#amountOfTimesToRepeat, #size);`
I.E. `grid-template-columns : repeat(5, 1fr)` creates 5 columns, each one taking the same equal amount of free space.

## Lesson 09
Learned about **spanning** attribute of grid. Use it in the following manner: `grid-column/row : span #amountToSpan`.

## Lesson 10
Learned about sizing of grid elements. The default attributes to use are : **grid-column/row-start** and **grid-column/row-end**. You can use the following attributes for a shortcut : **grid-column/row : #startIndex / #endIndex**. I.E. `grid-column : 1 / 5;` (You can use -1 to span across the whole grid).

## Lesson 11
Grid exercises

## Lesson 12
Learned about **auto-fill** and **auto-fit**. The difference between the two is that auto-fit will shrink down the explicit grid to how many elements are really present. Auto-fill will set the grid to be as wide as it can and will try to fit as many elements as it can. A use case for auto-fill is, if you have a bunch of elements, but you one to always be on the end (far right or far left), using auto-fill and grid-column-end will always place it there. Using auto-fit will just place it at the end of the grid, which may not be the margin of the whole width of the layout.

## Lesson 13
Learned about **minmax(MIN_VALUE, MAX_VALUE)** property for grid-template-columns/rows. Minmax accepts two values which singify the minimum and maximum an element on a track can take. I.E. `grid-template-columns : repeat(auto-fit, minmax(150px, 1fr));`
Also learned about **fit-content(VALUE)** which similarly to minmax, caps the amount of space an element in a track can take. I.E. `grid-template-columns: fit-content(100px) 150px 150px 150px; //Caps the first column to be 100px wide, while the other columns are 150px`.

## Lesson 14
Learned about **grid-template-areas** property. Using grid-template-areas, you define the place in the grid that your content will be in. This is handy, since you don't have to calibrate and fine tune each area in your grid and also when combining it with media queries, all you have to do is just redefine the grid-template-areas property. You do not have to use words to name your areas inside of your grid. You can use emojis.

## Lesson 15
Learned about naming columns/rows to enable easier use when styling start/end of grid items. Instead of using the index of the column/row, you can insert names when declaring the amount of columns/rows. 

I.E.

`grid-template-columns: [site-left] 1fr [content-start] 500px [content-end] 1fr [site-right];`
`grid-template-rows: [content-top] repeat(10, auto) [content-bottom];`

And placing your grid item with the following rules :

`.item3 {
      grid-column: content-start;
      grid-row: content-top / content-bottom;
    }`

## Lesson 16

Learned about **grid-auto-flow**. What this property does, is tell the grid to fill up any space that is left between grid elements. This happens if, for instance, you have an element that is too wide for a grid row, and because of this, it is moved to a new row. What you have left is a space on the top row with no elements in and using this property, the grid starts placing elements from where there is space and not from where the last element ended.

`grid-auto-flow : dense;`