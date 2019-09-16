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

# Selectors

- There are many different types of selectors.