## What is HTML

HTML stands for **Hypertext Markup Language**. Hypertext means that this type of document can contain links that allow the reader to jump to other places in the document or to different documents all together. Knowing this, it's easy to see why its used for the world wide web. While modern browsers support other file formats, HTML is by far the most common language used to write webpages.

As the name suggests **HTML is not a programming language** but a markup language. A markup language is a way for computers to control how text is processed and presented. HTML is very simple to learn because it requires the mastery of only 3 concepts; elements, tags, and attributes.

## What Are HTML elements?

HTML elements are the building blocks for a webpage. If a webpage is a chemical compound, **HTML elements are the atoms** that compose that compound. At just like elements in chemistry, each element type is different from the next and has a special purpose. Take a look at this sample element;

```html
<title>Facebook</title>
```

Generally speaking, each element will have 2 tags (opening tag and closing tag) and some content. The tag identifies the type of element. In this case the type is a `title` element. Title elements define the title of a webpage. It's opening tag is `<title>` and its closing tag is `</title>`. Tas are surrounded by angular brackets "<>" to distinguish them. All closing tags will be a "/" followed by the name of element.

An element's content is whatever is between the opening and closing tags. In this case the content is the string "Facebook".

Just like in chemistry, **elements can be combined to form structures**. Just like an element's content can be a string like "Facebook", it could also be **another element**. Take a look at the HTML structure below.

```html
<body>
  <h1>This is a Heading</h1>
  <p>This is a paragraph.</p>
</body>
```

Here we have a header element `<h1>` and a paragraph element `<p>`. However these elements are inside the body element `<body>`. When this happens it is said that the `<body>` element is a **parent element** to `<h1>` and `<p>`. Conversely, `<h1>` and `<p>` are **child elements** to `<body>` and **sister elements** to ech other.

Because of this, it is easy an intuitive to think of an HTML document as a **family tree**, with each element being a family member capable of producing children. Just like family trees, HTML documents can become quite complex; with dozens of "generations" and ancestors.

## More on Tags

As described before, `tags` are how elements are identified. Again relating back to chemistry, it could be said that "Fe" is the "tag" for iron, an atom with 26 protons. In chemistry there are 118 different elements. In HTML there are 142 and each representing a different component of a website. That's a lot of elements but in day-to-day use you'd probably only use around 30 different ones. Here is a list of the most common tags:

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

## Creating an HTML Document

So putting everything learned so far together, let's create a webpage! Before we start writing html code we first need to create a file and give it the extension `html`. Inside this file we will write our html code shown below.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>A simple HTML document</title>
  </head>
  <body>
    <p>Hello World!</p>
    <p></p>
  </body>
</html>
```

Every HTML document starts with the same line

```html
<!DOCTYPE html>
```

This is a doctype declaration, and all it does is tell whatever software is reading this file (chrome, safari, etc) that is document is an HTML document.

Next, we define our root element `html`, which always has the children `head` and `body`.

The head element will contain all metadata about the webpage i.e. title, description, favicon. This information will all be loaded before any rendering happens.

Next the `body` element contains the rendered contents of the document; the stuff you see when you load the page. It's contents can be anything you want to display. In this case we have a paragraph with the contents "Hello World".

Our document is ready to be viewed! All you need to do is open in with your favorite web browser and you should see the text "Hello World" rendered!

## HTML Attributes
