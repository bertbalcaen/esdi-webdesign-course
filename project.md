# Final project

Make an online CV.

- 1 page.
- At least 3 sections. For example: about me, work, projects, contact details, education, experience, links, ...
- Use a variety of HTML: lists, tables, titles, ...
- There should be a navigation to the different sections. 
- Maximum 2 fonts.
- Maximum 5 images. They should be optimized for the web, so not too big.
- Add a contact form.

# Navigation links

You can use `id` attributes and anchor links to link to items on the same page.

For example, in the content:

```html
<h1 id="bio">Bio</h1>
<p>This is my bio ...</p>
```

You can create a link to this part using:

```html
<a href="#bio">Bio</a>
```

# Navigation design

You are free to choose. 

One option would be to use `position: static`, so that the menu always stays on top when scrolling down. You would apply this property to the element that needs to be fixed, so to something like a `<header>`, `<ul>`, ...  

A `<ul>` is always good option for a navigation menu. To create a horizontal menu, you can use `display: flex` on that element. You will still need to disable the padding and margin for the browser built-in style sheet.