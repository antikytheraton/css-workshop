# Grid

Grid is a second, after Flexbox, CSS module introduced to solve modern layout
problems in efficient and elegant way. It's the most powerful layout mechanism
available in CSS. With this power comes also the complexity - Grid is also the
most complex module available in CSS.
Support

---

Grid was standardised and implemented in all major browsers at March 2017. The
browsers before that date don't have good support for Grid. Link to more details
in additional resources.
Concepts

---

Like in Flexbox to learn Grid first you need to understand few concepts this
module is introducing.

### Grid container

_Grid container_ is a parent element on which we apply `display: grid;`. It's
the root of the whole grid context. Similar to _Flex container_.

### Grid item

Each child of a _Grid container_ is a _Grid item_. Similar to _Flex item_.

### Grid line

Lines making the grid. They are not the colums and rows, but the lines between
them. They are similar to lines between rows and columns of a table. Those lines
don't have any width, nor are visible, there are pure abstraction. The numbers
start at 1 and finish at number of columns/rows + 1.

### Grid cell

A space (rectangle) between two adjacent row grid lines and between two adjacent
column grid lines. It's similar to a table cell. It's the smallest unit of
a grid, on which items can be placed.

### Grid track

A space between two adjacent row grid lines, or between two adjacent column grid
lines. They are either columns or rows of the grid.

### Grid area

A space surrounded by four grid lines. You can think of it as any rectangle
within the grid, which has all it's sides laying on grid lines.
Defining a grid (part 1)

---

The first thing we need to do when creating a Grid layout is to define a grid.
That is done by first using `display: grid;` property on a grid container, and
then defining rows and columns using one of those properties:

- `grid-template-columns` and `grid-template-rows`
- `grid-template-areas`
- `grid-template`
  They will all be covered in sections about placement where we can demonstrate
  grid examples.
  Implicit placement

---

If we don't manually assign grid items to rows and columns, the items will be
placed on them automatically by grid auto placement algorithm. By default each
item will ocupy only a single grid cell.

### `span` keyword

We can use `grid-column` and `grid-row` properties on a grid item with `span`
keyword to make items occupy more than a single column and/or row.
This will make the item span 3 rows and 2 columns (6 cells - rectangle 3x2):

```css
grid-column: span 2;
grid-row: span 3;
```

## Defining a grid (part 2)

Now that we have explained how implicit placement works, we can show by example
how you can define a grid using automatic placement of the items.

### `grid-template-columns` and `grid-template-rows`

`grid-template-columns` specify the sizes of the columns in the grid, while
`grid-template-rows` the sizes of the rows.

#### Shorthand

`grid-template` can set both in a single delcaration:

```css
grid-template: <grid-template-rows> / <grid-template-columns>;
```

### Different units

We can use many different units to specify the sizes of columns and rows. The
items of course can be mixed.

#### Using fixed sizes

Demo: https://codepen.io/no-cheating/pen/oNbomam?editors=1100
All fixed size units like px, em, rem, pt etc. are valid.

### Using `fr` units

Demo: https://codepen.io/no-cheating/pen/eYJeQMb?editors=1100
Then Grid module introduced new kind of unit: `fr` (fraction). This is
a proportional unit, which lets you specify not an exact size of something, but
how big it will be proportionally to other elements using that unit. And so an
column/row set to `4fr` will be 2 times as big as another column/row in the same
grid which is set to `2fr`. Columns/rows that have it's size in `fr` units will
take all the extra available space and expand distributing extra space between
each other in proportions defined by the values. It is similar to how
`flex-grow` and `flex-shrink` values work in Flexbox.
This is a powerful and very important concept introduced in Grid.

### Using repeat()

We can use `repeat()` to repeat identical column/row declarations multiple times,
to simplify the declaration. For example:

```css
grid-template-columns: repeat(4, 1fr);
```

### Grid line names

Optionally, when declaring a grid we can give custom names to grid lines. The
default ones are 1, 2, 3... number of column/rows + 1, but we can give them
human readable (text) names if we want. Those names then can be used when
specifying where an item will be placed on the grid.

```css
grid-template-rows: [<line1-name>] <line1-size> [<line2-name>] <line2-size> [<line3-name];
```

### Example showing items spanning multiple cells

Demo: https://codepen.io/no-cheating/pen/abdVXrR?editors=1100
It was mentioned earlier. Here is just to show a working example.
Other grid settings

---

### Gaps

Demo: https://codepen.io/no-cheating/pen/OJMOqPX?editors=1100
We can add and control the whitespace between columns and rows using
`column-gap` and `row-gap` properties:

```css
column-gap: <size>;
row: <size>;
```

#### Shorthand

Both can be declared at once using `gap`:

```css
/* To specify different values for column and rows */
gap: <row-gap-size> / <column-gap-size>;
/* To specify one value for both */
gap: <row-and-column-gap-size>;
```

### Alignment

There are few properties that control placement/alignment of grid and it's
items.

#### Items: `align-items` and `justify-items`

Demo: https://codepen.io/no-cheating/pen/mdVqoee?editors=1100
Analogically to similar properties `justify-content` and `align-items` in
Flexbox, those 2 properties control where the grid items are placed within the
grid cells, if they are smaller than the cells. They both accept following
values:

- `start`
- `end`
- `center`
- `stretch`

##### Shorthand `place-items`

There is a shorthand `place-items` for declaring both at once:

```css
place-items: <align-items> / <justify-items>;
```

#### Content: align-content and `justify-content`

Demo: https://codepen.io/no-cheating/pen/mdVqoee?editors=1100
Analogically to `align-content` in Flexbox those 2 properties control placement
of the whole grid within the Grid container, if the size of the grid is smaller
than the container. `align-content` controls column (vertical) placement, while
`justify-content` controls row (horizontal) placement. Both accept the same
values:

- `start`
- `end`
- `center`
- `stretch`
- `space-around`
- `space-between`
- `space-evenly`

##### Shorthand `place-content`

There is a shorthand `place-content` for declaring both at once:

```css
place-content: <align-content-value> / <justify-content-value>;
```

### Controlling implicit tracks

Demo: https://codepen.io/no-cheating/pen/eYJeXqa?editors=1100
`grid-auto-rows` and `grid-auto-columns` allow to control the sizes of rows
and columns that are created implicitly (when there is not enough cells to
accomodate all the items). They accept exactly the same values as
`grid-template-rows` and `gris-template-columns`.

### Controlling auto placement

Demo: https://codepen.io/no-cheating/pen/gOPXyOX?editors=1100
`grid-auto-flow` property controlls how the items will be placed on the grid
when we we don't place them explicitly. The possible values are:

- `row` - They will fill rows, creating extra rows when needed
- `column` - They will fill columns, creating new columns when needed
- `row dense` | `column dense` - The same as `column` and `row` only minimizing
  the number of empty grid cells
  Explicit placement

---

We can also place grid items manually. Either using line numbers or area names.

### Using lines

Demo: https://codepen.io/no-cheating/pen/YzwEMZx?editors=1100
When using line numbers we can specify both the position in column and rows. We
can specify start and end lines separately:

```css
grid-column-start: <line-number>;
grid-column-end: <line-number>;
grid-row-start: <line-number>;
grid-row-end: <line-number>;
```

Or use a shorthand:

```css
grid-column: <line-number> / <line-number>;
grid-row: <line-number> / <line-number>;
```

The numbers can be positive or negative integer. Positive numbers are the line
numbers counted from left to right. Negative ones count from right to left.

#### Omitting one position

We can also specify only start or only end position. The item will then occupy
a single cell, starting or ending where we specify. For example:

```css
grid-column-end: 3;
```

#### `span` keyword

Instead of specifying both start and end positions, we can also specify only one
of them and use `span` keyword on the other one, to specify how many column/rows
the item needs to span.
For example this tells to place the item starting on the 2nd grid line and span
3 columns, which means it'll be placed in grid columns 2, 3 and 4.

```css
grid-column: 2 / span 3;
```

### Using areas

Demo: https://codepen.io/no-cheating/pen/BajmEZO?editors=1100
Flexibility

---

### min-content, max-content

### fr units

### minmax()

Can also use `ch` (characters) units.

### Using all together

## Other concepts

### Overlaping

### Writing mode

## Grid vs Flexbox

Grid isn't meant to replace Flexbox. Grid is meant to complement Flexbox. Each
one offers different possibilities, has different strenghts and the usage of one
or another should be decided for each use case separately.
The main difference is that Flexbox is meant to be used with things laid out
only in one dimension (horizontal or vertical). Grid is meant to be used with
things that are laid out in both dimensions (both horizontal and vertical).
Other way to think about it is that Flexbox is meant to be used in micro
(low-level) layouts (e.g. laying out some buttons on a single line), while Grid
is meant to be used in more macro (high-level) layouts (e.g. laying out main
page areas like header, footer, sidebar, main content).
There are some situations where you can use both. Then you can choose any of
them depending on other criterias.
There are also some things that only one of them can do but not the other. For
example in Grid you can overlap items, while in Flexbox you can't. So if your
layouts need overlapping, Grid is your only choice.
This video explains it very well with a lot of visual examples:
https://www.youtube.com/watch?v=hs3piaN4b5I&list=PLbSquHt1VCf1x_-1ytlVMT0AMwADlWtc1&index=12
Learn both well. Use both.
Additional resources

---

### Layout Land videos on Grid by Jen Simmons

Great material explaining everything about Grid, and more. Best resource I've
seen to learn Grid. Might be especially of interest for graphic designers, as
the author talks a lot in context of graphic design. But I think it's a great
watch for everyone, especially that it's value is not only explaining Grid, but
also showing few things that are unfortunately usually missing from CSS
learning resources:

- How to think in CSS
- Writing semantic HTML before writing any CSS code, when implementing layouts
- Using progressive enhancement/graceful degradation
- Implementing responsive layouts
  https://www.youtube.com/playlist?list=PLbSquHt1VCf1x_-1ytlVMT0AMwADlWtc1

#### Exercises

Jen Simmons also has tons of demos and even exercises for CSS Grid on her
website.
https://labs.jensimmons.com/2017/workshop/

### CSS Tricks Complete Guide to Grid

Great as a reference of all properties with visual explanations.
https://css-tricks.com/snippets/css/complete-guide-grid/

### Grid Garden

A game to learn Grid with. It's good to get familiar with the concepts and the
syntax, but not enough to fully understand the power and uses of Grid:
https://cssgridgarden.com/

### Support table on Can I use

https://caniuse.com/#search=grid
