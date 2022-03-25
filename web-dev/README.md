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