## Default template of an HTML document
```html
<!DOCTYPE html> # It's to tell the browser what version of HTML it should render the document.
<html lang="en"> # lang specifies the language of the text content in that element. It's used
		 # to improve accesibility of the webpage.
    <head> # Where we put important meta-information about webpages, and stuff
	   # requiered for our webpages to render correctly in the browser.
        <meta charset="utf-8"> # It ensures that the webpage will display special
			       # symbols and chars from diff languages correctly.
	<title>Insert Title</title> # It's used to give the webpages a readable title,
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
<img src="https://www.animagelinklol.com/image.png"> # Image element, there's
	# no closing tag. 
<img alt="text"> # It's used to describe an image, it's put in case it cannot be loaded.
	# It's also used with screen readers to describe what the image is.
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



