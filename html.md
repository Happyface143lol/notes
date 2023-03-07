## Default template of an HTML document
```html
<!DOCTYPE html> # It's to tell the browser what version of HTML it should render the document.
<html lang="en"> # lang specifies the language of the text content in that element. It's used
		 # to improve accesibility of the webpage.
    <head> # Where we put important meta-information about webpages, and stuff
	   # requiered for our webpages to render correctly in the browser.
        <meta charset="utf-8"> # It ensures that the webpage will display special
			       # symbols and chars from diff languages correctly.
	<title>[title]</title> # It's used to give the webpages a readable title,
				    # displayed in the webpage's browser tab.
    </head>
    <body>
	# Where all the content displayed will go. 
    </body>
</html>
```

We can use ! in VS code to generate all of the template in one go.

## Text
```html
<p></p> # To write a paragraph of text, even if you put two paragraphs in one of these
	# it'll display as one.
<h1></h1> # These are text displayed larger and bolder than other texts. H1 is the largest,
	  # h6 is the smallest heading.
<strong></strong> # It makes the text bold, it also marks text as important. This
		  # affects tools, that users with visual impairments will rely on 
		  # to use your website.
<b></b> # It also makes the text bold, but it doesn't affect the screen readers.
<em></em> # It makes the text italic. It also places emphasis, which affect things
	  # like screen readers.
<i></i> # It also makes the text italic, but it isn't affected by the screen readers.
<!-- --> # Comments
<div></div> # It's a simple container.
```

## Lists

```html
<ul> # Unordered lists, when order doesn't matter.
    <li></li> # Each item within the list is created using li.
</ul>
<ol> # Ordered lists, where order does matter, appears with a number.
    <li></li>
</ol>
	<ol reversed> # It makes the numbers of the list reversed.
	<ol start="x"> # It makes the numbers start at number x.
	<ol type="a"> # It changes the numering type. 'a' for lowercase letters.
		      # 'A' for uppercase letters. 'i' for lowercase Roman numerals
		      # 'I' for uppercase Roman numerals. '1' for numbers (default)
	<li value="x" # For the list number to change to number x.
<dl> # Description Lists
    <dt><dt> # Description term 
    <dd><dd> # Description element
<dl>
```

## Links and images

```html
<a href="protocol://domain/path">Text Link</a> # Absolute Links, links
	# to other websites.
<a href="./pages/about.html">About</a> # Relative Links, links to another page on
	# the same site.
<a href="[link]" target="_blank"> <!-- Opens the link in a new tab -->

<img src="https://www.animagelinklol.com/image.png"> # Image element, there's
	# no closing tag. Src attribute specifies the image's URL. 
<img alt="text"> # It's used to describe an image, it's put in case it cannot be loaded.
	# It's also used with screen readers to describe what the image is.

<!-- We can turn the image into a link by surround the image tag with
a link tag -->

<figure> <!-- Allows adding caption to the image, we can put several things here -->
    <img src="[link]" alt "[alt]">
    <firgcaption>[caption]</figcaption> <!-- It's used to add the caption to
					describe the image contained within
					the figure element. -->
</figure>

```

## Content areas
These elements makes HTML easier to read and help with Search Engine Optimization
(SEO) and accessibility.

```html
<main> <!-- Identifies the main section of this page -->
   <section> <!-- To separate content from each other -->
   </section>
</main>

<footer> <!-- It will add a footer section to the page -->
</footer>
```

## Form

```html
<form action="[url]"> <!-- Form indicates that it's a form -->
                      <!-- Action tells where the form data should be sent -->

    <input type="[type]" name="[name]"> <!-- Type is a self-Closing element that 
	allows you several ways to collect data -->
	<!-- Name is an attribute that assigns a value to represent the 
	data being submitted -->

    <input type="[type]" placeholder="[placholder]"> <!-- It's a placeholder, 
	and gives a hint about what kind of information to enter into an input -->

    <input type="[type]" required> <!-- It just prevents the user from submitting
	a form when information is missing -->

    <input type="text"> <!-- Form that asks for text -->
    <input type="radio"> [button_name] <!-- Form to select the ones, with circle -->
    <input type="checkbox"> [button_name] <!-- Form that uses checkboxes -->

    <input type="[type]" name="[name]"> [button_name] <!-- So that it selects
	only one button, ALL buttons must have a name attribute with the same value -->
    <input type="[type]" value="[value]"> <!-- To know which button they've selected,
	bcs the form data sends the name and value attributes -->

    <input type="[type]" checked> <!-- So that it is checked by default -->

    <label><input type="[type]">[button_name]</label> <!-- If you click [name], it selects
	the corresponding radio button. It associates the text for an input element
	with the input element itself -->
    <input type="[type]" id="[id]"><label for="[id]">[button_name]</label> 
	<!-- Another way to associate an input element's text with the element
	itself -->

    <fieldset> <!-- To group related inputs and labers together in a web form, they
		all appear on a new line -->
	  <legend>[legend]</legend> <!-- Acts a caption for the content in the fieldset,
				    it provides context of the form -->
	
	<!-- insert input -->

    </fieldset>
</form>
```

## Button
```html
<button>[name of button]</button> <!-- Adds a clickable button -->
<button type="submit">[name of button]</button> <!-- Submits the form, and it's by default -->
```

#### What is html?
It's a language that providesraw data a webpage is built of. It puts the 
information on the webpage. It stands for Hypertext Markup Language.

##### Tags 
Almost all elemenets are just pieces of content wrapped in opening and closing
HTML tags. 

![Tags](images/element_html.png)

Opening tags tell it's the start of an HTML element. `<>`

Closing tags tell where an element ends. `</>`

There are some HTML elements that do not have a closing tag. 

##### Indentation and nesting
When we nest elements within other elements, we create a parent and child 
relationship between them. The nested elements are the children and the 
element they are nested within is the parent.

We use indentation to make the level of nesting clear and readable for 
ourselves and other developers who will work with our HTML in the future. 
It is recommended to indent any child elements by two spaces.

This is important because of CSS and JS.



