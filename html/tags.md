## Tags

As described before, `tags` are how elements are identified. Relating back to chemistry, it could be said that "Fe" is the "tag" for iron, an atom with 26 protons. In chemistry there are 118 different elements. In HTML there are 142 and each representing a different component of a website. That's a lot of elements but in day-to-day use you'd probably only use around 30 different ones. You've already been introduced to some of the most basic tags, like `html`, `body`, and `head`. Here is a list of the most common tags used:

- html - It is the root of the html document which is used to specify that the document is html.
- head - Head tag is used to contain all the head element in the html file. It contains the title, style, meta, … etc tag.
- meta -
- body - It is used to define the body of html document where all rendered content goes. It contains image, tables, lists, … etc.
- h1 - It is used to define the largest heading of html document.
- h2 - It is used to define the 2nd largest heading of html document.
- h3 - It is used to define the 3rd largest heading of html document.
- h4 - It is used to define the 4th largest heading of html document.
- h5 - It is used to define the 5th largest heading of html document.
- h6 - It is used to define the 6th largest heading of html document.
- p - It is used to define paragraph content in html document.
- span - It is used mark up a part of a text, or a part of a document
- em - It is used to renders as emphasized text
- b - It is used to specify bold content in html document
- small - It is used to set the small font size of the content
- u - It is used to set the content underline
- br - It is used to define a line break
- a - It is used to link one page to another page
- ol - It is used to list the content in a particular order
- li - It is used to list the content
- ul - It is used to list the content without order
- img - It is used to add image element in html document
- div - It is used to define a division of a webpage
- table - Table tag is used to create a table in html document
- tr - It is used to define row of html table
- td - It defines the standard cell in html document
- th - It defines the header cell in a table. By default it set the content with bold and center property
- form - It is used to create html form for user
- input - It is used to take the input from the user
- button - It is used to define a clickable button
- option - It is used to select an option from a drop-down list.

## Tag Syntax

Tags are always surrounded by angular brackets `<>` and generally speaking, elements will have two tags; an opening tag and closing tag. You can always distinguish between the two because closing tags begin with a backslash followed by the tag name, i.e. `<\head>`. Everything between the opening and closing tag is defined as the elements content.

```html
<body>
  <p>Everything between the two tags is the elements content</p>
</body>
```

Sometimes certain elements, like the `img` element cannot contain any children; these are called `leaf elements`. In these cases a shorthand can be used to describe the element. Take a look at the snippet below

```html
<img src="image.png"></img>
```

You can see that this format is quite redundant. We define an opening and closing tag but the element has no children. Because of these HTML has a nice shorthand to make this cleaner.

```html
<img src="image.png" />
```

Instead of defining a closing tag, we just end our first tag with a backslash. This tells the browser this element has no children and is a leaf element.
