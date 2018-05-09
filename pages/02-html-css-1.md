# Intro to HTML and CSS

HTML and CSS are the basic building blocks of all web pages. They are used to create the UI (User Interface) that the user interacts with this interaction is often referred to as UX (User eXperience).


## Additional Resources

* [HTML intro (MDN)](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML)
* [List of HTML tags (w3c)](https://www.w3schools.com/TAGs/)
* [Intro to CSS (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS)

## HTML

HTML (Hyper Text Markup Language) is a simple markup language (not a "programming language") used to define the structure of a web page.


### Basic HTML document structure

```
<!DOCTYPE html>
<html>
    <head>
        <title>Title of the document</title>
    </head>

    <body>
        Hello World!
    </body>
</html>
```

All html documents must follow this basic structure.

* Doctype - The Doctype tag should be the first line of any html document it is used to define the type of document.
* `<html>` - all html documents are wrapped in an `<html>` tag
* `<head>` - Information about the document
    * `<title>` - text displayed in title bar of browser
* `<body>` - The contents of the page displayed to the user


### HTML tags

An HTML tag is simply a word wrapped in a less than and greater than symbol. For example `<p>` is a tag that indicates some text should be treated as a paragraph. To close a tag you simply add a forward slash inside of the opening bracket `</p>`.

```
<p>Some paragraph text here!</p>
```

HTML tags are hierarchal and must always be properly nested.

The following example is **VALID**:

```
<p>Some paragraph <strong>text</strong> here!</p>
```

The following example is **INVALID**

```
<p>Some paragraph <strong>text</p> here!</strong>
```

### White space

White space is any non-character space. This can be spaces or new line characters. In HTML these characters are ignored. You can put 1 space between words and any additional whitespace is ignored.

For example

```
This


is 

some text.
```

Would be rendered as: `This is some text.`


### Self-Closing tags

Most HTML tags REQUIRE a closing tag. However, some are self closing. Some common self closing tags include:

* `<img>` - displays an image
* `<br>` - "blank rule" creates a new line
* `<hr>` - "horizontal rule" creates a horizontal divider line

```
Some text here<br>
This text will appear on the next line
```


### Attributes

HTML tags can have attributes that contain extra information about the tag. The following sets the `src` (source) attribute of the `<img>` (image) tag. This tells it where to get the image to display.

```
<img src="path/to/an/image.jpg">
```


### Boolean Attributes

Some attributes do not require a value. They are "boolean" (either they exist or they don't aka true/false). A good example of this is the input tag which creates a form input field. In the following example we set the `type` property to `text` and set a `value` which is the text that will be in the text box. We also have `readonly` as a boolean attribute which means the value cannot be changed by the user.

```
<input type="text" value="Some text" readonly>
```


### Anchor Tags (links)

Anchor Tags aka links can be clicked by a user to navigate from one html file to another. This is the most basic way of building a multi-page website. They are very simple to use. The `href` attribute tells the browser where to "go" when the user clicks the link.

```
<a href="path/to/another-file.html">Clickable Link Text Here</a>
```

### ID Attribute

Any html element can have an ID (identification) attribute. The ID can be used later to reference the element in JavaScript of CSS. One important note about IDs is that they **MUST BE UNIQUE**. If any element on the page has a specific ID no other element can use it.

```
<p id="my-id">something</p>
```


### Class attribute

Any html element can have a class attribute which contains a class (or many) that apply to that element. Class attributes can be used to reference html elements in JavaScript or CSS. Multiple classes are separated by spaces

```
<p class="some-class another-class one-more">something</p>
```


## CSS

CSS (Cascading Style Sheets) is a stylesheet language used to define how html should appear in the browser. This is commonly referred to as "styling".

### Style Attributes

Defining styles is very simple and consists of key/value pairs. For example the css to set text to bold is simply: `font-weight: bold`. There are a TON of css attributes, but they are very easy to look up as you need them and as you do more CSS you'll memorize more and more of them. Don't stress about not knowing them by heart in the beginning.

### Inline styles

The simplest way to apply styles to html is by doing them "inline" this is by simply using the html `style` attribute.

```
<p style="color: red">Some red text</p>
```

Multiple styles can be separated by a semi colon

```
<p style="color: red; font-weight: bold">Some red text</p>
```

Inline styles are commonly considered a "bad practice". This becomes really obvious if you think about a web page that might have 100 links on it that all need to look the same. If you want to change them all you have to change each item individually.

However, inline styles are still worth knowing about / using as they are the often the fastest way to try out styles on an element. Then, you can move them to an external css file.


### Selectors / CSS blocks

If you are not using inline styles you must reference HTML elements using selectors. Selectors come in 3 forms `tag`, `id`, `class`...

A **Tag Selector** references all elements of a specific html tag type. For example you could make all links (a tag) green like this...

```
a {
    color: green;
}
```

An **ID selector** is used to reference an html tag by it's id attribute. To indicate the selector is an ID selector you simply prefix it with a hash symbol (`#`).

```
#my-id {
    color: blue;
}
```

A **class selector** is used to reference any html page that has that class in it's list of classes in the class attribute of the html element. To indicate the selector is a class selctor you prefix it with a period (`.`)

```
.some-class {
    color red;
}
```

### Child Selectors

You can chain selectors together. If they have a space between them it indicates that the selector is supposed to be a child of the preceding selector. 

```
<div class="one">
  <div class="two">
    <div class="three">
        some text
    </div>
  </div>
</div>

<div class="three">
    some other text
</div>
```

Using the above HTML we can reference anything with the class `three` with `.three`, but if we only want to reference the `three` inside of `two` we can do...

```
.two .three {
    // styles here
}
```

### Multiple Selectors

To indicate that an item must have all of the selectors listed simply omit the space between them.

```
<div class="class1 class2 class3">all three</div>
<div class="class1">just 1</div>
<div class="class2">just 2</div>
```

```
.class1.class2.class3 {
    font-weight: bold;
}

.class1 {
    color: red;
}

.class2 {
    background-color: blue;
}
```

In the above example the "all three" would be bold with red text and a blue background. All 3 css definitions would apply to it. "just 1" would be red, but not bold or blue as it does not have class 2 or 3, and "just 2" would have a blue background only.


### Selector specificity

Any HTML element could have multiple css selectors referencing it. The browser chooses which style to apply based on the specificity. The more specific the selector the more likely it'll be the style that is used.

**Example**

```
<div class="menu">
  <a href="p1.html" class="menu-link">Page 1</a>
  <a href="p2.html" class="menu-link">Page 2</a>
  <a href="p3.html" class="menu-link active">Page 3</a>
</div>  

<a href="p4.html" class="menu-link">Page 4</a>
```

```
.menu-link {
    color: red;
    border: 1px solid black;
}

.menu .menu-link {
    color: green;
}

.menu .menu-link.active {
    color: purple;
    font-weight: bold;
}
```

In the above example the first 2 links inside of the div with the menu class would be green because `.menu .menu-link` is more specific than just `.menu-link`. However, all of the links would have a 1 pixel solid black border because they are all still `.menu-link`.

Additionally, the link with the active class would be purple and bold because it has both the `menu-link` and `active` class and `.menu .menu-link.active` is the most specific so the color is overridden.

The final link (page 4) would be red with a black border.


### Style Block

You can put css in your html file wrapped in a `<style>` tag.

```
<style>

.some-class {
    color: blue;
}

</style>
```

### External CSS file

Generally the best practice is to put your css in a separate css file. To do this you simply add a `<link>` tag in your html document to tell it where to find the css file. To work the link tag must have a `rel` attribute set to `stylesheet` so the browser knows what type of external file it is.

```
<link rel="stylesheet" href="path/to/stylesheet.css">
```

### CSS Concepts

* formatting
    * font-size
    * font-weight
* color
* background
* box model
    * margin
    * padding
    * border
* display
* position
* width / height
