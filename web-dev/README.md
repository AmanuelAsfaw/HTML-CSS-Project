# Box Model
Everything displayed by CSS is a box. Understanding how the CSS Box Model works is therefore a core foundation of CSS.
[Box Model](https://web.dev/learn/css/box-model/)
# Selectors
To apply CSS to an element you need to select it. CSS provides you with a number of different ways to do this, and you can explore them in this module.
[Selectors](https://web.dev/learn/css/selectors/)
[MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)
# The cascade
The cascade is the algorithm for solving conflicts where multiple CSS rules apply to an HTML element. It's the reason that the text of the button styled with the following CSS will be blue.

The cascade algorithm is split into 4 distinct stages.

1.Position and order of appearance: the order of which your CSS rules appear

2.Specificity: an algorithm which determines which CSS selector has the strongest match

3.Origin: the order of when CSS appears and where it comes from, whether that is a browser style, CSS from a browser extension, or your authored CSS

4.Importance: some CSS rules are weighted more heavily than others, especially with the !important rule type
[cascade](https://web.dev/learn/css/the-cascade/)

![Origin](https://web-dev.imgix.net/image/VbAJIREinuYvovrBzzvEyZOpw5w1/zPdaZ6G11oYrgJ78EfF7.svg)

#### Position and order of appearance
If you have a ```<link>``` that includes CSS at the top of your HTML page, then another ```<link>``` that includes CSS at the bottom of your page: the bottom ```<link>``` will have the most specificity. The same thing happens with embedded ```<style>``` elements, too. 

An inline style attribute with ```CSS``` declared in it will override all other ```CSS```, regardless of its position, unless a declaration has !important defined.

Being able to specify two values for the same property can be a simple way to create fallbacks for browsers that do not support a particular value. In this next example, font-size is declared twice. If ```clamp()``` is supported in the browser, then the previous font-size declaration will be discarded.

[clamp()](https://developer.mozilla.org/en-US/docs/Web/CSS/clamp)

# Specificity

## Specificity scoring
#### Universal selector - 0 points
#### Element or pseudo-element selector - 1 points
#### Class, pseudo-class, or attribute selector - 10 points
#### ID selector - 100 points
#### Inline style attribute - 1000 points
#### ```!important``` rule - 10,000 points
## Visualizing specificity

![](https://web-dev.imgix.net/image/VbAJIREinuYvovrBzzvEyZOpw5w1/McrFhjqHXMznUzXbRuJ6.svg)

The left group is id selectors. The second group is class, attribute, and pseudo-class selectors. The final group is element and pseudo-element selectors.
### A matching specificity score sees the newest instance win

# Inheritance

### How to explicitly inherit and control inheritance
#### The ```inherit``` keyword
#### The ```initial``` keyword
#### The ```unset``` keyword
The ```unset``` property behaves differently if a property is inheritable or not. If a property is inheritable, the ```unset``` keyword will be the same as ```inherit```. If the property is not inheritable, the ```unset``` keyword is equal to ```initial```.

# Color
### Numeric colors
#### Hex colors
Hexadecimal notation (often shortened to hex) is a shorthand syntax for RGB, which assigns a numeric value to red green and blue, which are the three **primary colors**.

You can also define an alpha value with any numerical colors. An alpha value is a percentage of transparency. In hex code, you add another two digits to the six digit sequence, making an eight digit sequence. For example, to set black in hex code, write ```#000000```. To add a 50% transparency, change it to ```#00000080```.
#### RGB (Red, Green, Blue)

An alpha is set in rgb() in one of two ways. Either add a / after the red, green and blue parameters, or use the rgba() function.

For example, to set a 50% alpha black in modern browsers, write: ```rgb(0 0 0 / 50%)``` or ```rgb(0 0 0 / 0.5)```. For wider support, using the ```rgba()``` function, write: ```rgba(0, 0, 0, 50%)``` or ```rgba(0, 0, 0, 0.5)```.

#### HSL (Hue, Saturation, Lightness)
HSL stands for hue, saturation and lightness. Hue describes the value on the color wheel, from 0 to 360 degrees, starting with red (being both 0 and 360). A hue of 180, or 50% would be in the blue range.

![](https://web-dev.imgix.net/image/VbAJIREinuYvovrBzzvEyZOpw5w1/ob7MTste1Obu9AoLvbKq.svg)

Saturation is how vibrant the selected hue is. A fully desaturated color (with a saturation of 0%) will appear grayscale. And finally, lightness is the parameter which describes the scale from white to black of added light. A lightness of 100% will always give you white.

### Color Keywords [Web.dev](https://web.dev/learn/css/color/)
There are [148 named colors in CSS](https://developer.mozilla.org/docs/Web/CSS/color_value#color_keywords). These are plain English names such as purple, tomato and goldenrod.

# Sizing Units

### Percentages
When using a percentage in CSS you need to know how the percentage is calculated. For example,```width``` is calculated as a percentage of the available width in the parent element.

```
div {
  width: 300px;
  height: 100px;
}

div p {
  width: 50%; 
}
```

In the above example, the width of ```div p``` is ```150px```.

### Dimensions and lengths

#### Absolute lengths

All absolute lengths resolve against the same base, making them predictable wherever they're used in your CSS. For example, if you use ```cm``` to size your element and then print, it should be accurate if you compared it to a ruler.

| Unit   |      Name      |  Equivalent to |
|----------|:-------------:|------:|
| cm |  left-aligned | 1cm = 96px/2.54 |
| mm |    Millimeters   |   1mm = 1/10th of 1cm |
| Q | Quarter-millimeters |    1Q = 1/40th of 1cm |
| in | Inches | 1in = 2.54cm = 96px |
| pc | Picas | 1pc = 1/6th of 1in |
| pt | Points | 1pt = 1/72th of 1in |
| px | Pixels | 1px = 1/96th of 1in |

#### Relative lengths

A relative length is calculated against a base value, much like a percentage. The difference between these and percentages is that you can contextually size elements. This means that CSS has units such as ch that use the text size as a basis, and vw which is based on the width of the viewport (your browser window). Relative lengths are particularly useful on the web due to its responsive nature.