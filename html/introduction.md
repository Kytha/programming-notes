## Web Fundamentals

Before jumping into HTML and subsequently web development it is important to have a general idea of how all the components and technologies behind the scenes work together to deliver content to your browser.

The most fundamental technology to understand for web development is web browsers. Fortunately you've probably already spent hundreds of hours using a browser. A web browser's fundamental purpose is allow you to visit webpages on the internet. It retrieves information from other parts of the web and displays it on your desktop or mobile device. It does this with the help of a technology called URL.

## Behind URLs

URL stands for Uniform Resource Locator. A url is a reference to a resource on the internet that specifies the resource's location and how to retrieve it.

```
https://google.com
```

- google.com - Name of the resource
- https - Specifies how to retrieve it (hypertext transfer protocol)

When you type in a URL, with the help of your ISP (internet service provider), your browser locates the server that resource is on and asks for the resource. If you're properly authenticated, the server will respond with the resource.

Two important things to note:

1. webpages are just document files
2. Servers are just computers with special server software running

Q: If webpages are documents what type of document are they?
A: HTML documents

## What is HTML

HTML stands for **Hypertext Markup Language**. Hypertext means that this type of document can contain links that allow the reader to jump to other places in the document or to different documents all together. Knowing this, it's easy to see why its used for the world wide web. While modern browsers support other file formats, HTML is by far the most common language used to write webpages.

As the name suggests **HTML is not a programming language** but a markup language. A markup language is a way for computers to control how text is processed and presented. HTML is very simple to learn because it requires the mastery of only 3 concepts; elements, tags, and attributes. In this section, we will explore what HTML elements are and how to create your first HTML document.

## What Are HTML elements?

HTML elements are the building blocks of a webpage. If a webpage is a chemical compound, **HTML elements are the atoms** that compose that compound. At just like elements in chemistry, each element type is different from the next and has a special purpose. Take a look at this sample element;

```html
<title>Facebook</title>
```

Generally speaking, each element will have 2 tags (opening tag and closing tag) and some content. The tag identifies the type of element. In this case the type is a `title` element. Title elements define the title of a webpage. It's opening tag is `<title>` and its closing tag is `</title>`. Tas are surrounded by angular brackets "<>" to distinguish them. All closing tags will be a "/" followed by the name of element. We will explore tags more in the future.

An element's content is whatever is between the opening and closing tags. In this case the content is the string "Facebook".

Just like in chemistry, **elements can be combined to form structures**. So instead of element's content being a string like "Facebook", it could also be **another element**. Take a look at the HTML structure below.

```html
<body>
  <h1>This is a Heading</h1>
  <p>This is a paragraph.</p>
</body>
```

Here we have a header element `<h1>` and a paragraph element `<p>`. However these elements are inside the body element `<body>`. When this happens it is said that the `<body>` element is a **parent element** to `<h1>` and `<p>`. Conversely, `<h1>` and `<p>` are **child elements** to `<body>` and **sister elements** to each other.

Because of this, it is easy an intuitive to think of an HTML document as a **family tree**, with each element being a family member capable of producing children. Just like family trees, HTML documents can become quite complex and containing dozens of "generations" and ancestors.

## Creating an HTML Document

So putting everything learned so far together, let's create a webpage! Before we start writing html code we first need to create a file and give it the extension `html`. Inside this file we will write our html code shown below. **This code is the basic structure for all HTML documents**

```html
<!DOCTYPE html>
<html lang="en">
  <head> </head>
  <body></body>
</html>
```

**Every HTML document will have this basic structure**, so let's analyze it line-by-line.

```html
<!DOCTYPE html>
```

This is a doctype declaration, and all it does is tell whatever software is reading this file (chrome, safari, etc) that this document is an HTML document and should be interpreted as such.

### html element

The `html` element is the root element (which just means the first ancestor) of all other elements in the document. This element will always have the children `head` and `body`.

### Head element

The head element will contain all metadata about the webpage i.e. title, description, favicon. This information will all be loaded before any rendering happens. Think of it like the information on the outside of a letter

### Body element

Next the `body` element contains the rendered contents of the document; the stuff you see when you load the page. It's contents can be anything you want to display. In this case we have a paragraph with the contents "Hello World".

Our document is ready to be viewed! All you need to do is open in with your favorite web browser and you should see the text "Hello World" rendered!

## Further Concepts

Read the tags and attributes articles to continue learning about HTML.
