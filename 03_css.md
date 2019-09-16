# HTML recap

- Quiz: https://www.w3schools.com/quiztest/quiztest.asp?qtest=HTML

# CSS

- Never use HTML for presentation, formatting or design - that's what CSS is for
- CSS = Cascading stylesheets
- CSS = rules defined by you that tell the browser how to display the elements in your HTML page

# CSS files

- Usually, CSS rules are placed in separate files ('stylesheets').
- These files have the extension `.css`.
- You need tell an HTML document which stylesheet to use by making a reference to the CSS file in the `<head>` of the document: `<link rel="stylesheet" href="css/styles.css">` 

For example:

```html
<!DOCTYPE html>     
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>This is the title</title>
        <link rel="stylesheet" href="css/styles.css"> 
    </head>
    <body>
        <h1>Hello world</h1>
    </body>
</html>
```

- You can have multiple stylesheets connected to the same HTML document.
- You can make certain stylesheets apply on to screens, or to print. 

# Rules

A rule consists of:

- a selector
- a declaration, which one or more settings between curly braces

In general:

```css
selector {
    property: value;
    property: value;
}
``` 

- The selector determines to what part of the HTML document the rule will apply.
- The declaration is list of one ore more properties with values.
- The properties and values are separated with a colon (:).
- Each property and value pair has to end with a semicolon (;).

For example:

```css
p {
    color: blue;
}
``` 

- The selector is `p`.
- The declaration is everything between `{` and `}`.
- The is one property/value pair: `color: blue;`. The property is `color`, and the value is `blue`.

# Browser default stylesheet

- Even if you don't add any rules at all to a page, the browser will still apply some CSS rules.
- Reason: the browser has a default stylesheet.
- It sets reasonable defaults: text is in black, links are underlined an in blue, an `<h1>` will be larger than a `<p>', ...
- You can override these with your own CSS.  

# Selectors

- Selectors: used to precisely define to what HTML the rules will apply.
- There are many different types of selectors. 
- In many cases, multiple rules can apply on an element. In that case, the most specific rule wins.
- 

## Tag selectors

- Easiest to understand.
- Example: `p`, `h1`, ... 
- These apply a rule to all elements with a specific tag name.
- Useful for defining the overall appearance of links, headers, paragraphs, ... 

For example:

```css
p {
    color: blue;
}
``` 

This will make all paragraphs blue.

## Inheritance

If you apply a rule to an element, all the children of that element will also inherit that rule.

For example if you apply this CSS:

```css
body {
    color: blue;
}
``` 

To this HTML:

```html
...
<body>
   <p>Hello</p> 
</body>
...
``` 

Then the paragraph will also be blue. Remember: HTML is like a tree structure, with hierarchical relations between elements (an element can contain other elements). The CSS you apply to a 'higher' element will also apply to the 'lower' elements.

## Grouping selectors

You can group selectors by using comma's. For example:

```css
p, h1, h2 {
    color: blue;
}
``` 

This will apply the rules in the declaration to all elements of the group. You can combine this with other rules. For example:

```css
p, h1, h2 {
    color: blue;
}

h1 {
    background-color: red;
}

h2 {
    background-color: yellow;
}
``` 

## Selecting elements inside other elements

Use a space to indicate that you want to select elements appearing inside other elements. For examplen this will only affect links in paragraphs. The rule will not be applied to other links.

```css
p a {
    color: green;
}
``` 

## The `class` attribute

- Tag selectors are useful, but in many cases you want to be more specific. For example, you want apply a rule only to some paragraphs, not to all.
- In this case you can use the `class` attribute. This attribute can be added to any HTML element. You can then reference it in your CSS.

For example, suppose you want to change the look of the first paragraph in this HTML:

```html
<p class="intro">
    This is the first paragraph.
</p>
<p>
    Another one.
</p>
<p>
    And another one.
</p>
``` 

Note that we added an attribute `class="intro"` to the first paragraph. 

You are free to choose the name of the class, but there are some rules:

- The name can only contain letters and digits.
- Spaces are not allowed. Well they are allowed, but then you give multiple classes to the same element. For example: `class="intro promotional-text"` gives the element 2 classes: intro, and promotional-text.
- Use a dash `-` or and `_` to create word breaks inside a class name.
- Most people only use underscore.
- It's best to use structural, semantic names that have nothing to do with the visual properties of an element, for example: better `intro` rather than `big-text`, or `blue-text`. If you decide to change the color of the text later on, the name `blue-text` might become confusing. 

Once you added a `class` attribute, you can target it in the CSS by adding a period `.` in front of the name:

```css
.intro {
    color: green;
}
``` 

You can re-use the `class`, and not only with paragraphs. For example: `<h1 class="intro">` would also work. 

Tag names and class names can be combined, for example:

```css
p.intro {
    color: green;
}
``` 

This means: apply the rule to `<p>` elements that have the class intro, but not to other elements, like headings.

## The `id` attribute

- Similar to the `class` attribute, but the value of an `id` attribute can only appear once in the page. (The same `class` can be used as much as you want in a document.)
- Less used than `class`, but you might see it.
- In CSS: use `#` before the name to target it.

Example:

```html
<h1 id="main-title">This is the main title</h1>
``` 

```css
#main-title {
    color: green;
}
``` 

## The most specific rule wins

What happens when multiple rules can be applied to an element?

For example:

```html
<body>
    <h1>
        A title
    </h1>
    <p class="intro">
        This is the first paragraph.
    </p>
    <p>
        Another one.
    </p>
    <p>
        And another one.
    </p>
</body>
``` 

CSS:

```css
body {
    color: red;
}
p {
    color: blue;
}
p.intro {
    color: green;
}
``` 

What color will each element have?

- All elements are hierarchically inside the `<body>` elements, so they all will be red, unless there are more specific rules.
- There are no rules for the `<h1>` that are more specific, so it will be red.
- The `<p>` elements will be blue by default, because they have a rule that is more specific than the one for `<body>`.
- The first paragraph has an even more specific rule: a combination of the tag name and a class name. This is more specific than the general rule for paragraphs.
