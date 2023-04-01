### What is CSS? 
It's a popular style sheet language that adds style to the plain elements of 
HTML, it gives the information color, font, and makes it look cool.

### Adding CSS to HTML
###### External CSS
Involves creating a separate file for the CSS and linking it inside of an HTML's
opening and closing `<head>` with a self-closing `<link>` element.
```html
<head>
    <link rel="[rel]" href="[css file name]"> 
    <!-- href attibute refers to the location of the CSS file, either an absolute
    URL or a URL relative to the location of the HTMl file. rel specifies the
    relationship between HTML file and the linked file -->
</head>
```
This keeps HTML and CSS separated, which results in the HTML file being smaller 
and making things look cleaner.

We only need to edit the CSS in one place, which is especially handy for 
websites with many pages that all share similar styles.

###### Internal CSS
Involves adding the CSS withing the HTML file itself. We will place them
inside `<style></style>`, which are placed inside `<head></head>`. 

This is useful to add unique stles to a single page of website, and depending
on how many rules and declarations there are it, can cause the HTML file to get
very big.

###### Inline CSS
Involves adding styles directly to HTML elements. This isn't recommended, as
it can make the HTML file really messy, when we start adding a lot of 
declarations, and if we want many elements to have the same style, we would 
need to copy and paste the same style to each individual element. Any inline 
CSS will override the other two methods.

```html
<body>
    <div style="color: white; background-color: black;">...</div>
</body>
```

### Basic Syntax

![Basic_syntax_css](images/basic_syntax_css.jpg)

##### Selectors
Refers to the HTML elements which CSS rules apply. They're what actually being
selected for each rule. 

###### Universal Selector
This will select elements of any type, and the syntax is a simple asterisk.

```css
* {
    color: purple;
}
```

###### Type Selectors
This will select all the elements of the given element type.

```css
div {
    color: white;
}
```

###### Class Selectors
This will select all the elements with the given class, which is an attribute
you place on an HTML element.

```html
<div class="[class]"> Hello! </div>
```

```css
.[class] {
    color: red;
}
```

To select all the [element] elements in an element, like article, we write:
```css
.[class] [element]{
    color: red;
}
```

###### ID Selectors
They select an element with a give ID, which is an another attribute you 
place on an HTML element.

```html
<div id="[id]">Hi!</div>
```

```css
#[id] {
    background-color: red;
}
```
The difference between classes and IDs is that an element can only have one
ID, it cannot be repeated on a single page, and it shouldn't contain any
whitespace.

###### Grouping Selectors
When two groups of elements share some of their style declarations.

```css
.[class1],
.[class2] {
    color: white;
    background-color: black;
}

.[class1] {
    /* unique declarations */
}

.[class2] {
    /* unique declarations */
}
```

###### Chaining Selectors
It selects any element that has both [class1] AND [class2]. There isn't any space and
it works for chaining any combination of selectors, except for type selectors.

```html
<div>
    <div class="[class1] [class2]">Latest Posts</div>
    <p class="[class1] [class3]">Preview</p>
</div>
```

```css
.[class1].[class2] {
    color: red;
}
```

It can also be used to chain a class and an ID.

```html
<div>
    <div class="[class1] [class2]">Latest Posts</div>
    <p class="[class1]" id="[id]">Preview</p>
</div>
```

```css
.[class1]#[id] {
    color: blue;
}
```

###### Descendant Combinator
It allows us to combine multiple selectors differently than either grouping or
chaining them.  A descendant combinator will only cause elements that match 
the last selector to be selected if they also have an ancestor that matches 
the previous selector.

`.ancestor .child` will only select an element if the class `child` is nested
inside of `ancestor`, no matter how deep. 

```html
<div class="ancestor">
    <div class="contents">
    </div>
</div>
```

```css
.ancestor .contents {
    /* some declarations */
}
```

### The Box Model

##### Parts of the box

* Content box: It's the area where the content is displayed.

* Padding: It's the space between the border of a box and the content of the box.

* Border: It's the space between the margin and the padding. The size of it is added
	to the `width` and `height`. Each border can have a style, width and color we can
	manipulate.

* Margin: It's the space between the borders of a box and the borders of the 
	adjacent boxes. It's not counted to the actual size of the box. It can have positive
	or negative values. We can use negative values to overlap other things. If two vertically
	adjacent elements have a margin set on them and their margins touch, only
	the larger margin remains, this is called margin collapsing.

```css
/* Box */
margin-[left/right/top/bottom]: [number/auto]px; /* Margin on the [left/right/top/bottom].
	To center it, have margin left and right in auto. */
padding-[left/right/top/bottom]: [number]px; /* Adds some space between 
	the content and sides */
padding: [number]px; /* Adds space between the content and sides in all directions */
border: [number]px [style] [color]; /* Creates a border with the line size of [number],
	, using the [color] and the [type]. */
	/* [style]: double, solid, dotted */

box-sizing: border-box; /* Allows us to include the padding and border in an
	element's total width and height. */

/* To save time, you can also do */

margin: [top] [right] [bottom] [left]; /* If there's any missing, it's assumed that 
	it's based on the ones defined. If only one missing, it's margin is [top]
	[left-and-right] [bottom] */

margin: [number] auto; /* The value of auto tells the browser to define the margin for you.
	In most cases, it'll be equivalent to 0, or whatever space is available. However,
	it's quite handy for HORIZONTAL centering. */

```

Display specifies how an element would be treated, and the layout of its children.

```css
display: [option];
```
If the [option] is:

* `block`: the box will break into a new line, the width and height are respected
the padding, margin and border will cause other elements to be pushed away 
from the box, and if the width is not specified, the box will extend in the
inline direction to fill the space available in its container. 

* `inline`: the box will not break, width and height do not apply
everything about the box (padding, size, etc.) VERTICALLY will apply but 
will not cause other inline boxes to move away from the box, but everything 
about the box HORIZONTALLY will apply AND will cause other inline boxes 
to move away from the box.

* `flex`: the element will use the outer display type block but the inner 
display type to flex, and any direct children will become flex items.

* `inline-block`: it doesn't break into a new line but it'll respect the 
width and height. Everything about the box, will cause the other elements to 
be pushed away.

##### Normal Flow

The elements that are laid out by default are using the box model. By default,
a block level element's content fills the available inline space of the 
parent element containing it and the element grows along the block dimension 
to accommodate its content.

The size of inline elements is just the size of their content. You can't set width
and height, apart from images. We need to use `display: inline-block` or 
`display: block`, so that we can control the size.

The normal layout flow (mentioned in the layout introduction article) is the 
system by which elements are placed inside the browser's viewport. By 
default, block-level elements are laid out in the block flow direction, 
which is based on the parent's writing mode. Each element will appear on a 
new line below the last one, with each one separated by whatever margin 
that's been specified.

Inline elements all sit on the same line along with any adjacent text content,
as long as there is space to do so. If not, it'll move down to a new line.

### Flexbox
It . These items will grow and shrink
(flex, basically) based on simple rules you can define. The elements will try to fill
the available area will each have equal width.

* Flex container: is any element that has `display: flex`. 
* Flex item: is any element that is inside of a flex container. 

![Basic_syntax_css](images/basic_syntax_css.jpg)
![flex_container_item] (images/flex_container_item.jpg)

### Properties

```css
/* Color */
p {
    color: [color]; /* Set an element's text color. */
    background-color: [color]; /* Set the background color of an element. */
    /* We can use HEX, RGB, and HSL values.
	RGB --> rgb([0-255 red],[0-255 green],[0-255 blue]); (In RGB, when
	the primary colors are combined, it creates pure white)

	RGBA --> rgb([0-255 red],[0-255 green],[0-255 blue], [0-100% / 0-1 alpha value]); 
	(In RGB, when the primary colors are combined, it creates pure white)

        HEX --> #[00-FF red][00-FF green][00-FF blue][00-FF alpha channel]; 
        (0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F)
 
        HSL --> hsl([0-360 HUE], [0-100 saturation]%, [0-100 lightness]%);
        (0 HUE is red, 120 HUE is green, 240 HUE is blue)

	HSLA --> hsl([0-360 HUE], [0-100 saturation]%, [0-100 lightness]%, 
	[0-100% / 0-1 alpha value]);
    */

    border-color: [color]; /* Sets the edges of the element to that color. */

    opacity: [0-1 / 0 - 100%]; /* Controls how opaque or transparent an element is */

    box-shadow: [[number] offsetX] [[number] offsetY] [[number] blurRadius] 
    [[number] spreadRadius] [color];
}

/* Color: Gradient*/
div{
   background: [gradient]; /* Because the gradient function creates an image 
	element, and the background element accepts an image as a value */

   /* [Gradient] 
	linear-gradient([0-360 gradientDirection]deg, [color1],[color2], ...);
	    [Gradientdirection] is a number that indicates the direction of the line.
	    [Color1] and [color2] are color arguments, which are the colors used 
	    in the transition. They can be hex, rgb, hsl or keywords.	
	    
	linear-gradient(..., [color1] [color-stop][px/%],[color2], ...);
	    [color-stop] is a length unit that continues a color in the 
	    linear-gradient.
   */
}
```


```css
/* Size */
p {
    width: [number][px/%]; /* Sets the width to the pixels or the % of the parent */
    max-width: [number][px/%]; /* To prevent the contents from growing too wide */
    height: [number]px; /* Sets the height to the [number]px */
}
```

```css
/* Text */
p {
    font-family: [font], [font]; /* Determine what font an element uses */
    font-family: sans-serif; /* Generic family names */
    font-family: "DejaVu Sans"; /* Font family name, we use quotes due to whitespace */
    /* between words. If a browser can't find or support the first font, it'll use */
    /* the next one, and so on until it finds a supported and valid font. Usually, with */
    /* start with the font we want to use, and end with a generic font family. */

    font-size: [number]px; /* Sets the size of the font */
    font-weight: [number between 1-1000 OR a keyword]; /* Affects the boldness of the text */
    text-align: [center/left/right]; /* Align the text horizontally within an element */
    font-style: [normal/italic/oblique]; /* Sets whether a font should be from the [] */ 
}
```

```css
/* Image */
img {
    height: auto; /* With auto, image will be the same proportions */
    width: 500px;
}

p {
    background-image: url([link]); /* Adds a background image to the parent */
}

/* It's best to include both of these properties, as stating a height and width,
reserves a space for the image on the page. A blank space will be there
until the image loads. */
```

```css
/* Links */
a:visited{ /* Pseudo-selector */
    [property]: [property value]; /* [property] happens when it has been visited */
}
a:hover{ 
    [property]: [property value]; /* [property] happens when the cursor hovers over it */
}
```

### Cascade
The cascade is what determines which rules actually get applied to the HTML. 

###### Importance
1. Transition: Rules that apply to an active transition take the utmost importance
2. `!important`: When we add !important to the end of our declaration, it jumps to this level of the Cascade. 
3. Animation: Rules that apply to an active animation jump up a level in the Cascade
4. Normal: This level is where the bulk of rules live

###### Origin
1. Website: This is the only level that you have control over, as a web developer.
2. User
3. Browser: Each browser has its own set of styles, which is why things like <button>s have default styles.

The hierarchy here is actually reversed for `!important` rules, meaning that an 
`!important` browser default rule wins over an !important website rule.

###### Specificity
A CSS declaration that is more specific will take precedence over less 
specific ones.

*Inline* have the hightest specificity compared to selectors. 

Each selector has its own specificity level that contributes to how 
specific a declaration is.

1. ID selectors (most specific selector)
2. Class selectors
3. Type selectors

Specificity will only be taken into account when an element has multiple, 
conflicting declarations targeting it, sort of like a tie-breaker.

When no declaration has a selector with a higher specificity, a larger 
amount of a single selector will beat a smaller amount of that same selector.

`*`, `+`, `~`, `>` doesn't add specificity. `*` has no specificity value.

###### Inheritance
Inheritance refers to certain CSS properties that, when applied to an 
element, are inherited by that element’s descendants. Typography bases properties
are usually inherited, white most other properties aren’t.

The exception to this is when directly targeting an element, as this always 
beats inheritance

###### Order
Whichever rule was the last defined is the winner.