# Who?

- Bert Balcaen
- webdeveloper at https://rekall.be since 2001
- bert@rekall.be

# Software requirements

- a browser
- a text editor

## Browsers

Most popular browsers (August 2019)

On desktop:
 
- Chrome (Windows + Mac): 71%
- Firefox (Windows + Mac): 9%
- Safari (Mac only): 6%
- rest: Edge (Windows only), Internet Explorer (Windows only), Opera (Windows + Mac), ...

See https://gs.statcounter.com/browser-market-share/desktop/worldwide.

On mobile:

- Chrome (iOS + Android): 61% + 7% (Samsung Internet) = 68% 
- Safari (iOS): 20%

See https://gs.statcounter.com for more statistics.

- Browsers are not 100% the same. There are standards for HTML, CSS and JS, but you can never be completely sure that a page will look exactly the same in all browsers.
- Chrome for desktop is not the same as Chrome for mobile. Same with Safari.
- You should your work in different browsers.
- On desktop, a page should at least work in Chrome, Firefox and Safari.
- On mobile, you should test in Chrome and Safari.

## Text editor

You are free to choose.

Recommendation: [atom](https://atom.io)

# 3 layers in a webpage

A webpage is a cake with 3 layers:

- HTML = structure
- CSS = design
- JavaScript = interaction

Each technology has its responsibility.

TODO: show how to disable JS and CSS

# HTML

- The bottom layer.
- This layer is all about structure, semantics, meaning.
- Use HTML to tell people and machines how the page is structured.

Examples:

- `<h1>` = this is the most important title
- `<h2>` = this is a subtitle
- `<p>` = just a paragraph

HTML is very important for machines (software, computers):

- If HTML is used properly, a search engine (like Google) can understand the structure of the document. For example, if the search engine sees `<h1>` tags, it know that this text is important.

You can easily abuse HTML and use it for design. A classic bad example is using HTML tables to make columns in the page.

A good web designer never uses HTML for design.

# CSS

- CSS = aka 'stylesheets'.
- CSS determines what the page looks like.

CSS is not required to make a webpage. If you don't add a stylesheet yourself, the browser's default stylesheet will be used.

# JavaScript

- JS: used for interaction
- For example: animations, popups, form validation, ...