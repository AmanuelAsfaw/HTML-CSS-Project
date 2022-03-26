# Layout

## Understanding the display property

The ```display``` property does two things. The first thing it does is determine if the box it is applied to acts as inline or block.

```inline``` elements behave like words in a sentence. They sit next to each other in the inline direction.

You can't set an explicit width and height on inline elements. Any block level margin and padding will be ignored by the surrounding elements.

```block``` elements don't sit alongside each other. They create a new line for themselves. Unless changed by other CSS code, a block element will expand to the size of the inline dimension, therefore spanning the full width in a horizontal writing mode. The margin on all sides of a block element will be respected.

Setting the ```display``` property to ```display: flex``` makes the box a block-level box, and also converts its children to flex items. This enables the flex properties that control alignment, ordering and flow.

## Flexbox and Grid 

are two main layout mechanisms that create layout rules for multiple elements.

### Flexbox

Flexbox is a layout mechanism for one-dimensional layouts. Layout across a single axis, either horizontally or vertically. By default, flexbox will align the element's children next to each other, in the inline direction, and stretch them in the block direction, so they're all the same height.
