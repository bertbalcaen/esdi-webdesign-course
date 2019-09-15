# HTML elements, tags and attributes

![elements, tags and attributes](./img/element-tag-attribute.png)

# Elements and tags

- HTML elements are the building blocks of HTML pages.
- An element usually has a start and end tag, an opening and closing tag.
- For example: `<p>` and `</p>`.
- A start tag starts with `<` and ends with `>`.  
- An end tag starts with `<` and ends with `/>`.
- Tags have names, for example the name of the `<p>' tag is `p`.
- Not all tags have closing tags. For example: `<br>`, a break, or a new line. Another example: `<img>`.

All HTML tags: https://www.w3schools.com/tags/ref_byfunc.asp 

## Hierarchical relations between elements

Elements can contain other elements. For example:

```html
<p>This is some text, and this is in <b>bold</b>.</p> 
```

The nesting can go deeper:

```html
<p>This is some text, and this is in <b><i>bold and in italics</i></b>.</p> 
```

We can also reformat this to show the hierarchy more clearly:

```html
<p>
    This is some text, and this is in 
        <b>
            <i>
                bold and in italics
            </i>
        </b>
    .
</p> 
```

Now it's more clear that there are 3 levels in piece of HTML, with a hierarchy between them. This will be important later when we talk about CSS.

There are rules about which sub-elements an element can have. For example, a `<p>` can contain `<b>` and `<i>` elements, but not a `<table>` element.

Elements must also be properly nested. This is wrong for example:

```html
<b><i>bold and in italics</b></i>
```
# Whitespace in HTML documents

- Whitespace = spaces, tabs, line break (new line).
- Browser ignore almost all whitespace.

For example:

```
<p>Hello world!</p>
```

Renders exactly the same as 

```
<p>


Hello                       world!
                </p>
```

Use whitespace to make the hierarchy clear between the elements. It makes the code more readable, and there is less chance of mistakes. 

For example:

```html
<table><tr><td>Item 1</td><td>€5</td><td>3</td></tr><tr><td>Item 2</td><td>€7</td><td>11</td></tr></table>
```

This is correct HTML but it's not very readable. It can be rewritten as:

```html
<table>
    <tr>
        <td>Item 1</td>
        <td>€5</td>
        <td>3</td>
    </tr>
    <tr>
        <td>Item 2</td>
        <td>€7</td>
        <td>11</td>
    </tr>
</table>
```

This is much more readable. The result in the browser will be exactly the same.

This piece of HTML has 3 levels. Each level is indented with a specific number of tabs. It's easy to see where an element is inside the structure by looking at the number of tabs in front of each element.

- level 0: `<table>`, 0 tabs
- level 1: `<tr>` inside `<table>`, 1 tab
- level 2: `<td>` inside `<tr>`, 2 tabs

Using indentation (tabs or spaces) is absolutely not required, but it helps a lot.

# Attributes

- Some elements have attributes.
- Attributes are used to give extra info to an element.
- For example: `<img src="logo.png">`. The `<img>` element requires a `src` (source) attribute to let the browser know which image to load.
- Attribute always have the form `name="value"`. You can also use single quotes, but double quotes is more common.
- Attributes always appear at the start tag, never at the end tag.
- Some attributes are required, while others are optional. For example: the `src` attribute is required for an `<img>` tag. The `width` attribute for an `<img>` is optional.
- An element can have multiple attribute, seperated by a space. The order is never important. For example: `<img src="logo.png" width="100" height="200">`.

# Organizing files

Typical directory structure of a website:

- index.html -> the home page
- another_page.html
- img/ -> directory with images used on the site
- css/ -> directory with stylesheets
- js/ -> directory with JavaScript files

# Rules for filenames

- HTML documents typically use the extension `.htm` or `.html`. The last one is more common.

The following rules apply to HTML documents, and other files, like images, CSS, JS, ...:

- It's best to avoid spaces in filenames. Use a dash `-` or an underscore `_` instead. Reason: spaces are not allowed in URL's.
- Use lowercase for filenames. Reason: the server your site is on might be case-sensitive, meaning: `Index.html` and `index.html` are two different documents. Avoid confusion by using lowercase everywhere.

# Basic structure of an HTML document

The is a minimal HTML page:

```html
<!DOCTYPE html>     
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>This is the title</title>
    </head>
    <body>
        <h1>Hello world!</h1>
    </body>
</html>
```

## Doctype

- Necessary, but no need to worry about the details.
- Must be on the first line.
- Mostly needed for historical reasons.

## `<html>`

- The `<html>` element is the container for the whole page.
- An HTML document contains HTML elements.
- There is a hierarchical relationship between the elements.
- The `<html>` element is at the top of hierarchy.
- It has two child elements: `<head>` and `<body>`.
- These are required. In other parts of the document you are free to include other elements, but inside `<html>` we need to use `<head>` and `<body>`.
- Always set the `lang` attribute of the `<html>` element so search engines and other software know what language your document is in. 

## `<head>`

- The `<head>` element contains meta information, meaning info about the document itself.
- Most important: the `<title>` of the document.
- The title appears in the title bar of the browser window, and is used when you save a bookmark, or save the page. 
- It's also very important for search engines. The title is used in the search results. Also, search engine will use the text of the `<title>` to rank search results. It's very important for SEO to give good titles to pages, and to make them unique.
- Other things that can appear in the `<head>` element: the character set used, references to stylesheets, reference to the favicon, ...

## `<body>`

- The `<body>` element contains the actual content: text, images, ...

## How to check if your HTML is correct?

- You can 'validate' your document = checking if the HTML is correct.
- Go to https://validator.w3.org.
- Click on the tab 'Validate by Direct Input'.
- Copy and paste the HTML and click 'Check'.
- Read the results and fix any errors.

## Exercise: fix a badly made HTML page

- You will fix a badly made HTML document. There are many errors: invalid nesting, missing elements, ...
- [Download the exercise](exercises/fix_incorrect_html/index.html) (Right-click and select 'Save link as')
- Check if your document is valid on https://validator.w3.org.

# Commonly used HTML elements

## Inline vs block-level

Block-level elements:

- examples: `<p>`, `<h1>`, `<table>`, ...
- begin on a new line 
- take up the full width of their parent element

Inline elements:

- examples: `<b>`, `<i>`, `<img>`, ...
- can be part of a line of text 
- do no start a new line

## Headings

- `<h1>`, `<h2>`, `<h3>`, `<h4>`, `<h5>`, `<h6>`
- `<h1>` = most important title
- `<h2>` = subtitle
- Use headings to indicate the logical levels in your text.

## Paragraphs and breaks

- `<p>This is a paragraph.<p>`
-  Use a break `<br>` to create a new line in a paragraph.
- Paragraph are block level elements.

## Lists

- Very common. Also used for navigation items.
- Can be ordered (with a numbering) and unordered (no numbering).
- Lists are block level elements.

Unordered:

```html
<ol>
    <li>cookies</li>
    <li>milk</li>
    <li>bread</li>
</ol>
```

Ordered:

```html
<ul>
    <li>cookies</li>
    <li>milk</li>
    <li>bread</li>
</ul>
```

## Images

- ```<img src="path_to_image" alt="alternative text for image">```
- The `src` attribute is required.
- Use relative paths for loading images within your website and absolute paths to link to an image on another website.
- `alt` attribute: a textual description of the image
- You can omit the description within the `alt` attribute if the image you are using is decorative and has no 'real meaning', for example a drop shadow, a separator, ...
- Images are inline level elements.

## Links
- `<a href="path_to_link">content that is looks like a  link</a>`
- The `href` attribute is required.
- Use relative paths for linking files within your website and absolute path to link  to external resources and websites.
- `<a href="path_to_link" target="_blank">` 
- Use the attribute `target="_blank"` when linking to an external website to keep your website and let the link open in a new tab or page.
- Links are inline level elements, so you can place a link within paragraphs, headers, lists, or structural elements.

Example of a simple link:

```html
Read more <a href="about_us.html">about us</a>.
```

Link to an external page that opens in a new window or tab:

```html
Our school <a href="https://esdi.es" target="_blank">ESDI</a>.
```

Linking an image:

```html
<a href="index.html">
    <img src="logo.png">
</a>
```

Email links:

- `<a href="mailto:bert@rekall.be">send me a mail</a>`
- Clicking on the link will open a mail client (Outlook, Thunderbird, Apple Mail, ...)

## Comments

- `<!-- some comment  -->`
- Used for your own organisation. 
- Used to temporarily hide your markup in the browser (in debug mode).

## Entities

- Some characters have a special meaning.
- For example `<` is the start of the tag.
- We cannot use these characters directly because we would confuse the browser. We need to use 'entities'.

Common entities:

- `&gt;` for `>`
- `&lt;` for `<`
- `&amp;` for `&`

## Text formatting

- `<b>`, `<strong>`
- `<i>`, `<em>`
- `<hr>`

## Structual elements

- `<header>`, `<footer>`
- `<nav>`

# Exercise: turn some content into a website

- You will make a mini-website with 2 pages: a homepage and an about page.
- Create a new, empty folder for this. Create the necessary files and directories.
- Each page should have a navigation on top, with links to the homepage, the about page, and a link to the ESDI site. The logo should also be on top of every page, and it should link to the homepage. You download the logo here: exercises/content_to_website/This is our logo.jpeg](exercises/content_to_website/This is our logo.jpeg) (right-click > save link as)
- Each page should also have a footer, which mentions 'Made by your name here' and your email address. Your email address should be a link. 
- The about page needs to have the text in [exercises/content_to_website/about.txt](exercises/content_to_website/about.txt) (right-click > save link as). Use the appropriate HTML elements to make the structure of the text clear.
- 

# Homework

- Quiz: https://www.w3schools.com/quiztest/quiztest.asp?qtest=HTML