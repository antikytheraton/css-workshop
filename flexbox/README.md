# Flexbox

To make an element use Flexbox layout `display: flex` needs to be set on that
element.
That element becomes a Flex parent. All its children are Flex children. It's
both children and parent layouts which get affected by Flexbox properties.
Controlling the parent

---

2 main settings of a Flex parent are direction and wrapping.

### Direction

Demo: https://codepen.io/no-cheating/pen/poggmeW?editors=1100
The direction in which the children are laid out is set by `flex-direction`
property. It has 4 possible values: `row`, `column`, `row-reverse` and
`column-reverse`.
That defines which axis is the main one and which is the cross one. For `row`
Y axis is the main one and X is the cross one. For `column` X is the main one
and Y the cross one. That's important terminology to understand well further
properties like `justify-content` and `align-items`.

### Wrapping

Demo: https://codepen.io/no-cheating/pen/LYGGoWa?editors=1100
You control if the children will wrap (span multiple) or not (will occupy only
a single line) by `flex-wrap` property. That property accepts 2 values:
`wrap` and `nowrap`.

### Combining direction and wrapping

`flex-direction` and `flex-wrap` can be combined into one shorthand property
`flex-flow`, e.g. `flex-flow: column-reverse nowrap`.

### Controlling main axis

Demo: https://codepen.io/no-cheating/pen/bGEEyRB?editors=1100
You can control how children are laid out on main axis (which one is the main
axis is dictated by the value of `flex-direction`). The property that controls
this is `justify-content`, with values:

- `flex-start` (default)
- `flex-end`
- `center`
- `space-between`
- `space-around`
- `space-evenly`

### Controlling cross axis

Demo: https://codepen.io/no-cheating/pen/rNxxgdZ?editors=1100
To control cross axis layout `align-items` property is used. It has values:

- `stretch` (default)
- `flex-start`
- `flex-end`
- `center`
- `baseline`

### Layout of whole content

Demo: https://codepen.io/no-cheating/pen/xxZZNMN?editors=1100
When content spans multiple lines, you can also control how the whole content
lays out in relation to the cross axis of the parent. `align-content` is the
property for that. It has values:

- `stretch` (default)
- `flex-start`
- `flex-end`
- `center`
- `space-between`
- `space-around`
- `space-evenly`
  Controlling the children

---

### Order

Demo: https://codepen.io/no-cheating/pen/dyGGEBo?editors=1100
Unlike in CSS layout methods before, in Flexbox visual order of the children can
be different than the order in the markup. It is controlled by `order` property,
applied on each child. It accepts numerical values, natural numbers, both
negative and positive. The default value is `0`.

### Size

Demo: https://codepen.io/no-cheating/pen/mdVVZqM?editors=1100
That's the most complicated part of Flexbox module - controlling the size of
children. 3 properties applied on the child all play role in that:

- `flex-basis`
- `flex-grow`
- `flex-shrink`
  `flex-basis` is the starting size for the child, before Flexbox applies any size
  manipulations. It's equivalent and equal to `width` when `flex-direction` is
  `row`, and to `height` when `flex-direction` is `column`. It takes exactly the
  same values as `width` and `height`.
  `flex-grow` describes ability of that particular child to grow, when there is
  some extra space to be distributed. It accepts positive integers and `0` as
  values. Those values describe the ratio in which that child will grow in
  relation to other children (a child with `flex-grow: 6` will grow twice as much
  as a child with `flex-grow: 3`). `0` means the child will never grow. The
  default value is `0`.
  `flex-shrink` describes ability of that particular child to shrink, when there
  is not enough space to accomodate all children. It accepts positive integers and
  `0` as values. Those values describe the ratio in which that child will shrink
  in relation to other children (a child with `flex-shrink: 2` will shrink twice
  as much as a child with `flex-shrink: 1`). `0` means the child will never shrink.
  The default value is `1`.
  There is a shorthand property `flex`, which assigns all 3 values at once. The
  interesting part is that you don't have to specify all 3 numbers, but can
  specify 1, 2 or 3 numbers. If you choose to specify only 1 or 2 numbers it's
  understanding is quite complicated, and I recommend to read the [reference on
  MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/flex) before using those
  forms. It's usage is totally optional though - you can always specify
  `flex-basis`, `flex-grow` and `flex-shrink` separately.

### Self aligning

Demo: https://codepen.io/no-cheating/pen/OJMMeJg?editors=1100
The value of `align-items` on Flex **parent** specifies the alignment of the
children on cross axis. The value specified on the parent can be overwritten for
specific children using `align-self` property applied on the **child**. It
accepts excactly the same values as `align-items`.
Some use cases

---

Demo: https://codepen.io/no-cheating/pen/OJMNmpy?editors=1100
The most useful use case is centering things. Before Flexbox centering in CSS,
especially vertical, used to be hard, sometimes very hard. With Flexbox it
became easy as it always should have been.
Other thing, which is not a use case per sethat much, but is something that wasn't
mentioned before and it's often useful, is that when a Flex child has some of
it's main axis margins specified to `auto`, that child will eat the available
white space and work similar to floating.
Standard layout

---

Standard layout exercise, this time using Flexbox for a solution.
Result image: https://i.ibb.co/TLW0LK8/standard-layout-result.png
Exercise: https://codepen.io/no-cheating/pen/QWyNvxg?editors=1100
Result: https://codepen.io/no-cheating/pen/mdVPmLJ?editors=1100
Additional resources

---

- Learn Flexbox while playing:
  https://flexboxfroggy.com/
- The best guide and reference to Flexbox:
  https://css-tricks.com/snippets/css/a-guide-to-flexbox/
