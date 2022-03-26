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

[MDN Reading Source](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)

The Flexible Box Module, usually referred to as flexbox, was designed as a one-dimensional layout model, and as a method that could offer space distribution between items in an interface and powerful alignment capabilities. This article gives an outline of the main features of flexbox, which we will be exploring in more detail in the rest of these guides.

When we describe flexbox as being one dimensional we are describing the fact that flexbox deals with layout in one dimension at a time — either as a row or as a column. This can be contrasted with the two-dimensional model of CSS Grid Layout, which controls columns and rows together.

#### The two axes of flexbox

When working with flexbox you need to think in terms of two axes — the main axis and the cross axis. The main axis is defined by the ```flex-direction``` property, and the cross axis runs perpendicular to it. Everything we do with flexbox refers back to these axes, so it is worth understanding how they work from the outset.

The main axis is defined by flex-direction, which has four possible values:
```row``` ```row-reverse``` ```column``` ```column-reverse```

#### The flex container

An area of a document laid out using flexbox is called a flex container. To create a flex container, we set the value of the area's container's ```display``` property to ```flex``` or ```inline-flex```. As soon as we do this the direct children of that container become flex items. 

#### Multi-line flex containers with flex-wrap

While flexbox is a one dimensional model, it is possible to cause our flex items to wrap onto multiple lines. In doing so, you should consider each line as a new flex container. Any space distribution will happen across that line, without reference to the lines either side.

To cause wrapping behavior add the property ```flex-wrap``` with a value of ```wrap```. Now, should your items be too large to all display in one line, they will wrap onto another line. The live sample below contains items that have been given a width, the total width of the items being too wide for the flex container. 

#### The flex-flow shorthand

You can combine the two properties ```flex-direction``` and ```flex-wrap``` into the ```flex-flow``` shorthand. The first value specified is ```flex-direction``` and the second value is ```flex-wrap```.

##### align-items
The ```align-items```property will align the items on the cross axis.
values are ```stretch``` ```flex-start``` ```flex-end``` ```center```

##### justify-content
The justify-content property is used to align the items on the main axis, the direction in which flex-direction has set the flow.
values are ```flex-start``` ```flex-end``` ```center``` ```space-around``` ```space-between``` ```space-evenly```


### Grid

**CSS Grid Layout** excels at dividing a page into major regions or defining the relationship in terms of size, position, and layer, between parts of a control built from HTML primitives.

## Flow layout
