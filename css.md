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

### Properties

```css
/* Color and background-color */
p {
    color: [color]; /* Set an element's text color. */
    background: [color]; /* Set the background color of an element. */
    /* We can use HEX, RGB, and HSL values. */
}
```

```css
/* Typography Basics and Text-Align */
p {
    font-family: [font], [font]; /* Determine what font an element uses */
    font-family: sans-serif; /* Generic family names */
    font-family: "DejaVu Sans"; /* Font family name, we use quotes due to whitespace */
    /* between words. If a browser can't find or support the first font, it'll use */
    /* the next one, and so on until it finds a supported and valid font. Usually, with */
    /* start with the font we want to use, and end with a generic font family. */

    font-size: [number]px; /* Sets the size of the font */
    font-weight: [number between 1-1000 OR a keyword]; /* Affects the boldness of the text */
    text-align: [center/left/right] /* Align the text horizontally within an element */
}
```

```css
/* Image Height and Width */
img {
  height: auto; /* With auto, image will be the same proportions */
  width: 500px;
}

/* It's best to include both of these properties, as stating a height and width,
reserves a space for the image on the page. A blank space will be there
until the image loads. */
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


##### What is CSS? 
It's a popular style sheet language that adds style to the plain elements of 
HTML, it gives the information color, font, and makes it look cool.