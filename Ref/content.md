# Content

- [Content](#content)
- [Document Description](#document-description)
  - [HTML basics](#html-basics)
    - [So what is HTML?](#so-what-is-html)
      - [Anatomy of an HTML element](#anatomy-of-an-html-element)
      - [Nesting elements](#nesting-elements)
      - [Void elements](#void-elements)
      - [HTML documents](#html-documents)
    - [Images](#images)
    - [Marking up text](#marking-up-text)
      - [Headings](#headings)
      - [Paragraphs](#paragraphs)
      - [Lists](#lists)
    - [Links](#links)
  - [CSS Basics](#css-basics)
    - [What is CSS?](#what-is-css)
      - [Anatomy of a CSS ruleset](#anatomy-of-a-css-ruleset)
      - [Selecting multiple elements](#selecting-multiple-elements)
      - [Different types of selectors](#different-types-of-selectors)
    - [Fonts and text](#fonts-and-text)
    - [CSS: all about boxes](#css-all-about-boxes)
      - [Changing the page color](#changing-the-page-color)
      - [Styling the body](#styling-the-body)
      - [Positioning and styling the main page title](#positioning-and-styling-the-main-page-title)
      - [Centering the image](#centering-the-image)
  - [JavaScript basics](#javascript-basics)
    - [What is JavaScript?](#what-is-javascript)
    - [A "Hello world!" example](#a-hello-world-example)
      - [What happened?](#what-happened)
    - [Language basics crash course](#language-basics-crash-course)
      - [Variables](#variables)
      - [Comments](#comments)
      - [Operators](#operators)
      - [Conditionals](#conditionals)
      - [Functions](#functions)
      - [Events](#events)
    - [Supercharging our example website](#supercharging-our-example-website)
      - [Adding an image changer](#adding-an-image-changer)
      - [Adding a personalized welcome message](#adding-a-personalized-welcome-message)
      - [A user name of null?](#a-user-name-of-null)

# Document Description

HTML (HyperText Markup Language) is the most basic building block of the Web. It defines the meaning and structure of web content. Other technologies besides HTML are generally used to describe a web page's appearance/presentation (CSS) or functionality/behavior (JavaScript).

## HTML basics

HTML (HyperText Markup Language) is the code that is used to structure a web page and its content. For example, content could be structured within a set of paragraphs, a list of bulleted points, or using images and data tables. As the title suggests, this article will give you a basic understanding of HTML and its functions.

### So what is HTML?

HTML is a markup language that defines the structure of your content. HTML consists of a series of elements, which you use to enclose, or wrap, different parts of the content to make it appear a certain way, or act a certain way. The enclosing tags can make a word or image hyperlink to somewhere else, can italicize words, can make the font bigger or smaller, and so on. For example, take the following line of content:

```console
My cat is very grumpy
```

If we wanted the line to stand by itself, we could specify that it is a paragraph by enclosing it in paragraph tags:

```html
<p>My cat is very grumpy</p>
```

#### Anatomy of an HTML element

Let's explore this paragraph element a bit further.

![paragraph element including opening tag, content reading 'my cat is very grumpy', and a closing tag](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics/grumpy-cat-small.png)

The main parts of our element are as follows:

1. **The opening tag:** This consists of the name of the element (in this case, p), wrapped in opening and closing **angle brackets**. This states where the element begins or starts to take effect — in this case where the paragraph begins.
2. **The closing tag:** This is the same as the opening tag, except that it includes a *forward* slash before the element name. This states where the element ends — in this case where the paragraph ends. Failing to add a closing tag is one of the standard beginner errors and can lead to strange results.
3. **The content:** This is the content of the element, which in this case, is just text.
4. **The element:** The opening tag, the closing tag, and the content together comprise the element.

Elements can also have attributes that look like the following:

![Paragraph opening tag with a class attribute highlighted: class=editor-note](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics/grumpy-cat-attribute-small.png)

Attributes contain extra information about the element that you don't want to appear in the actual content. Here, `class` is the attribute *name* and `editor-note` is the attribute *value*. The class attribute allows you to give the element a non-unique identifier that can be used to target it (and any other elements with the same `class` value) with style information and other things.

An attribute should always have the following:

1. A space between it and the element name (or the previous attribute, if the element already has one or more attributes).
2. The attribute name followed by an equal sign.
3. The attribute value wrapped by opening and closing quotation marks.

> **Note:** Simple attribute values that don't contain ASCII whitespace (or any of the characters " ' ` = < >) can remain unquoted, but it is recommended that you quote all attribute values, as it makes the code more consistent and understandable.

#### Nesting elements

You can put elements inside other elements too — this is called nesting. If we wanted to state that our cat is **very** grumpy, we could wrap the word "very" in a `<strong>` element, which means that the word is to be strongly emphasized:

```html
<p>My cat is <strong>very</strong> grumpy.</p>
```

You do however need to make sure that your elements are properly nested. In the example above, we opened the `<p>` element first, then the `<strong>` element; therefore, we have to close the `<strong>` element first, then the `<p>` element. The following is incorrect:

```html
<p>My cat is <strong>very grumpy.</p></strong>
```

The elements have to open and close correctly so that they are clearly inside or outside one another. If they overlap as shown above, then your web browser will try to make the best guess at what you were trying to say, which can lead to unexpected results. So don't do it!

#### Void elements

Some elements have no content and are called **void elements**. Take the `<img>` element that we already have in our HTML page:

```html
<img src="images/firefox-icon.png" alt="My test image" />
```

This contains two attributes, but there is no closing `</img>` tag and no inner content. This is because an image element doesn't wrap content to affect it. Its purpose is to embed an image in the HTML page in the place it appears.

#### HTML documents

That wraps up the basics of individual HTML elements, but they aren't handy on their own. Now we'll look at how individual elements are combined to form an entire HTML page. Let's revisit the code we put into our `index.html` example (which we first met in the **Dealing with files** article):

```html
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>My test page</title>
  </head>
  <body>
    <img src="images/firefox-icon.png" alt="My test image" />
  </body>
</html>
```

Here, we have the following:

- `<!DOCTYPE html>` — doctype. It is a required preamble. In the mists of time, when HTML was young (around 1991/92), doctypes were meant to act as links to a set of rules that the HTML page had to follow to be considered good HTML, which could mean automatic error checking and other useful things. However, these days, they don't do much and are basically just needed to make sure your document behaves correctly. That's all you need to know for now.
- `<html></html>` — the `<html>` element. This element wraps all the content on the entire page and is sometimes known as the root element. It also includes the `lang` attribute, setting the primary language of the document.
- `<head></head>` — the `<head>` element. This element acts as a container for all the stuff you want to include on the HTML page that isn't the content you are showing to your page's viewers. This includes things like **keywords** and a page description that you want to appear in search results, CSS to style our content, character set declarations, and more.
- `<meta charset="utf-8">` — This element sets the character set your document should use to UTF-8 which includes most characters from the vast majority of written languages. Essentially, it can now handle any textual content you might put on it. There is no reason not to set this, and it can help avoid some problems later on.
- `<meta name="viewport" content="width=device-width">` — This **viewport element** ensures the page renders at the width of viewport, preventing mobile browsers from rendering pages wider than the viewport and then shrinking them down.
- `<title></title>` — the `<title>` element. This sets the title of your page, which is the title that appears in the browser tab the page is loaded in. It is also used to describe the page when you bookmark/favorite it.
- `<body></body>` — the `<body>` element. This contains all the content that you want to show to web users when they visit your page, whether that's text, images, videos, games, playable audio tracks, or whatever else.

### Images

Let's turn our attention to the `<img>` element again:

```html
<img src="images/firefox-icon.png" alt="My test image" />
```

As we said before, it embeds an image into our page in the position it appears. It does this via the `src` (source) attribute, which contains the path to our image file.

We have also included an `alt` (alternative) attribute. In the `alt` **attribute**, you specify descriptive text for users who cannot see the image, possibly because of the following reasons:

1. They are visually impaired. Users with significant visual impairments often use tools called screen readers to read out the alt text to them.
2. Something has gone wrong causing the image not to display. For example, try deliberately changing the path inside your src attribute to make it incorrect. If you save and reload the page, you should see something like this in place of the image:

![The words: my test image](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics/alt-text-example.png)

The keywords for alt text are "descriptive text". The alt text you write should provide the reader with enough information to have a good idea of what the image conveys. In this example, our current text of "My test image" is no good at all. A much better alternative for our Firefox logo would be "The Firefox logo: a flaming fox surrounding the Earth."

Try coming up with some better alt text for your image now.

> **Note:** Find out more about accessibility in our **accessibility learning module**.

### Marking up text

This section will cover some essential HTML elements you'll use for marking up the text.

#### Headings

Heading elements allow you to specify that certain parts of your content are headings — or subheadings. In the same way that a book has the main title, chapter titles, and subtitles, an HTML document can too. HTML contains 6 heading levels, `<h1> - <h6>`, although you'll commonly **only use 3 to 4 at most**:

```html
<!-- 4 heading levels: -->
<h1>My main title</h1>
<h2>My top level heading</h2>
<h3>My subheading</h3>
<h4>My sub-subheading</h4>
```

> **Note:** Anything in HTML between `<!--` and `-->` is an HTML comment. The browser ignores comments as it renders the code. In other words, they are not visible on the page - just in the code. HTML comments are a way for you to write helpful notes about your code or logic.

Now try adding a suitable title to your HTML page just above your `<img>` element.

> **Note:** You'll see that your heading level 1 has an implicit style. Don't use heading elements to make text bigger or bold, because they are used for **accessibility** and **other reasons such as SEO**. Try to create a meaningful sequence of headings on your pages, without skipping levels.

#### Paragraphs

As explained above, `<p>` elements are for containing paragraphs of text; you'll use these frequently when marking up regular text content:

```html
<p>This is a single paragraph</p>
```

Add your sample text (you should have it from **What will your website look like?**) into one or a few paragraphs, placed directly below your `<img>` element.

#### Lists

A lot of the web's content is lists and HTML has special elements for these. Marking up lists always consists of at least 2 elements. The most common list types are ordered and unordered lists:

1. **Unordered lists** are for lists where the order of the items doesn't matter, such as a shopping list. These are wrapped in a `<ul>` element.
2. **Ordered lists** are for lists where the order of the items does matter, such as a recipe. These are wrapped in an `<ol>` element.

Each item inside the lists is put inside an `<li>` (list item) element.

For example, if we wanted to turn the part of the following paragraph fragment into a list

```html
<p>
  At Mozilla, we're a global community of technologists, thinkers, and builders
  working together…
</p>
```

We could modify the markup to this

```html
<p>At Mozilla, we're a global community of</p>

<ul>
  <li>technologists</li>
  <li>thinkers</li>
  <li>builders</li>
</ul>

<p>working together…</p>
```

Try adding an ordered or unordered list to your example page.

### Links

Links are very important — they are what makes the web a web! To add a link, we need to use a simple element — `<a>` — "a" being the short form for "anchor". To make text within your paragraph into a link, follow these steps:

1. Choose some text. We chose the text "Mozilla Manifesto".
2. Wrap the text in an `<a>` element, as shown below:

```html
<a>Mozilla Manifesto</a>
```

3. Give the `<a>` element an `href` attribute, as shown below:

```html
<a href="">Mozilla Manifesto</a>
```

4. Fill in the value of this attribute with the web address that you want the link to:

```html
<a href="https://www.mozilla.org/en-US/about/manifesto/">Mozilla Manifesto</a>
```

You might get unexpected results if you omit the `https://` or `http://` part, called the protocol, at the beginning of the web address. After making a link, click it to make sure it is sending you where you wanted it to.

> **Note:** `href` might appear like a rather obscure choice for an attribute name at first. If you are having trouble remembering it, remember that it stands for **hypertext reference**.

---

## CSS Basics

CSS (Cascading Style Sheets) is the code that styles web content. CSS basics walks through what you need to get started. We'll answer questions like: How do I make text red? How do I make content display at a certain location in the (webpage) layout? How do I decorate my webpage with background images and colors?

### What is CSS?

Like HTML, CSS is not a programming language. It's not a markup language either. **CSS is a style sheet language**. CSS is what you use to selectively style HTML elements. For example, this CSS selects paragraph text, setting the color to red:

```css
p {
  color: red;
}
```

Let's try it out! Using a text editor, paste the three lines of CSS (above) into a new file. Save the file as `style.css` in a directory named `styles`.

To make the code work, we still need to apply this CSS (above) to your HTML document. Otherwise, the styling won't change the appearance of the HTML. (If you haven't been following our project, pause here to read **Dealing with files** and **HTML basics**.)

1. Open your `index.html` file. Paste the following line in the head (between the `<head>` and `</head>` tags):

```html
<link href="styles/style.css" rel="stylesheet" />
```

2. Save `index.html` and load it in your browser. You should see something like this:

![A Mozilla logo and some paragraphs. The paragraph text has been styled red by our css.](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics/website-screenshot-styled.png)

If your paragraph text is red, congratulations! Your CSS is working.

#### Anatomy of a CSS ruleset

Let's dissect the CSS code for red paragraph text to understand how it works:

![CSS p declaration color red](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics/css-declaration-small.png)

The whole structure is called a **ruleset**. (The term ruleset is often referred to as just *rule*.) Note the names of the individual parts:

**Selector**
  This is the HTML element name at the start of the ruleset. It defines the element(s) to be styled (in this example, `<p>` elements). To style a different element, change the selector.

**Declaration**
  This is a single rule like `color: red;`. It specifies which of the element's *properties* you want to style.

**Properties**
  These are ways in which you can style an HTML element. (In this example, `color` is a property of the `<p>` elements.) In CSS, you choose which properties you want to affect in the rule.

**Property value**
  To the right of the property—after the colon—there is the *property value*. This chooses one out of many possible appearances for a given property. (For example, there are many `color` values in addition to `red`.)

Note the other important parts of the syntax:

- Apart from the selector, each ruleset must be wrapped in curly braces. (`{}`)
- Within each declaration, you must use a colon (`:`) to separate the property from its value or values.
- Within each ruleset, you must use a semicolon (`;`) to separate each declaration from the next one.

To modify multiple property values in one ruleset, write them separated by semicolons, like this:

```css
p {
  color: red;
  width: 500px;
  border: 1px solid black;
}
```

#### Selecting multiple elements

You can also select multiple elements and apply a single ruleset to all of them. Separate multiple selectors by commas. For example:

```css
p,
li,
h1 {
  color: red;
}
```

#### Different types of selectors

There are many different types of selectors. The examples above use **element selectors**, which select all elements of a given type. But we can make more specific selections as well. Here are some of the more common types of selectors:

| Selector name | What does it selects | Example|
|---|---|---|
| Element selector (sometimes called a tag or type selector) | All HTML elements of the specified type. | p selects `<p>` |
| ID selector | The element on the page with the specified ID. On a given HTML page, each id value should be unique. | `#my-id` selects `<p id="my-id">` or `<a id="my-id">` |
| Class selector | The element(s) on the page with the specified class. Multiple instances of the same class can appear on a page.| `.my-class` selects `<p class="my-class">` and `<a class="my-class">` |
| Attribute selector | The element(s) on the page with the specified attribute. | `img[src]` selects `<img src="myimage.png">` but not `<img>`|
| Pseudo-class selector | The specified element(s), but only when in the specified state. (For example, when a cursor hovers over a link.) | `a:hover` selects `<a>`, but only when the mouse pointer is hovering over the link.|

There are many more selectors to discover. To learn more, see the **MDN Selectors guide**.

### Fonts and text

Now that we've explored some CSS fundamentals, let's improve the appearance of the example by adding more rules and information to the `style.css` file.

1. First, find the **output from Google Fonts** that you previously saved from **What will your website look like?**. Add the `<link>` element somewhere inside your `index.html`'s head (anywhere between the `<head>` and `</head>` tags). It looks something like this:

```html
<link
  href="https://fonts.googleapis.com/css?family=Open+Sans"
  rel="stylesheet" />
```

This code links your page to a style sheet that loads the Open Sans font family with your webpage.

2. Next, delete the existing rule you have in your `style.css` file. It was a good test, but let's not continue with lots of red text.
3. Add the following lines (shown below), replacing the `font-family` assignment with your `font-family` selection from **What will your website look like?**. The property `font-family` refers to the font(s) you want to use for text. This rule defines a global base font and font size for the whole page. Since `<html>` is the parent element of the whole page, all elements inside it inherit the same `font-size` and `font-family`.

```css
html {
  font-size: 10px; /*px means "pixels": the base font size is now 10 pixels high*/
  font-family: "Open Sans", sans-serif; /*this should be the rest of the output you got from Google Fonts*/
}
```

> **Note:** Anything in CSS between `/*`and`*/` is a CSS comment. The browser ignores comments as it renders the code. CSS comments are a way for you to write helpful notes about your code or logic.

4. Now let's set font sizes for elements that will have text inside the HTML body (`<h1>`, `<li>`, and `<p>`). We'll also center the heading. Finally, let's expand the second ruleset (below) with settings for line height and letter spacing to make body content more readable.

```css
h1 {
  font-size: 60px;
  text-align: center;
}

p,
li {
  font-size: 16px;
  line-height: 2;
  letter-spacing: 1px;
}
```

Adjust the `px` values as you like. Your work-in-progress should look similar to this:

![A Mozilla logo and some paragraphs. A sans-serif font has been set, the font sizes, line height and letter spacing are adjusted, and the main page heading has been centered](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics/website-screenshot-font-small.png)

### CSS: all about boxes

Something you'll notice about writing CSS: a lot of it is about boxes. This includes setting size, color, and position. Most HTML elements on your page can be thought of as boxes sitting on top of other boxes.

![A big stack of boxes or crates sat on top of one another](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics/boxes.jpg)

Photo from <https://www.geograph.org.uk/photo/3418115> Copyright © **Jim Barton** cc-by-sa/2.0

CSS layout is mostly based on the **box model**. Each box taking up space on your page has properties like:

- `padding`, the space around the content. In the example below, it is the space around the paragraph text.
- `border`, the solid line that is just outside the padding.
- `margin`, the space around the outside of the border.

![Three boxes sat inside one another. From outside to in they are labelled margin, border and padding](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics/box-model.png)

In this section we also use:

- `width` (of an element).
- `background-color`, the color behind an element's content and padding.
- `color`, the color of an element's content (usually text).
- `text-shadow` sets a drop shadow on the text inside an element.
- `display` sets the display mode of an element. (keep reading to learn more)

To continue, let's add more CSS. Keep adding these new rules at the bottom of `style.css`. Experiment with changing values to see what happens.

#### Changing the page color

```css
html {
  background-color: #00539f;
}
```

This rule sets a background color for the entire page. Change the color code to **the color you chose in What will my website look like?**.

#### Styling the body

```css
body {
  width: 600px;
  margin: 0 auto;
  background-color: #ff9500;
  padding: 0 20px 20px 20px;
  border: 5px solid black;
}
```

There are several declarations for the `<body>` element. Let's go through these line-by-line:

- `width: 600px;` This forces the body to always be 600 pixels wide.
- `margin: 0 auto;` When you set two values on a property like `margin` or `padding`, the first value affects the element's top and bottom side (setting it to `0` in this case); the second value affects the left and right side. (Here, `auto` is a special value that divides the available horizontal space evenly between left and right). You can also use one, two, three, or four values, as documented in **Margin Syntax**.
- `background-color: #FF9500;` This sets the element's background color. This project uses a reddish orange for the body background color, as opposed to dark blue for the `<html>` element. (Feel free to experiment.)
- `padding: 0 20px 20px 20px;` This sets four values for padding. The goal is to put some space around the content. In this example, there is no padding on the top of the body, and 20 pixels on the right, bottom and left. The values set top, right, bottom, left, in that order. As with `margin`, you can use one, two, three, or four values, as documented in **Padding Syntax**.
- `border: 5px solid black;` This sets values for the width, style and color of the border. In this case, it's a five-pixel–wide, solid black border, on all sides of the body.

#### Positioning and styling the main page title

```css
h1 {
  margin: 0;
  padding: 20px 0;
  color: #00539f;
  text-shadow: 3px 3px 1px black;
}
```

You may have noticed there's a horrible gap at the top of the body. That happens because browsers apply default styling to the `<h1>` element (among others). That might seem like a bad idea, but the intent is to provide basic readability for unstyled pages. To eliminate the gap, we overwrite the browser's default styling with the setting `margin: 0;`.

Next, we set the heading's top and bottom padding to 20 pixels.

Following that, we set the heading text to be the same color as the HTML background color.

Finally, `text-shadow` applies a shadow to the text content of the element. Its four values are:

- The first pixel value sets the **horizontal offset** of the shadow from the text: how far it moves across.
- The second pixel value sets the **vertical offset** of the shadow from the text: how far it moves down.
- The third pixel value sets the **blur radius** of the shadow. A larger value produces a more fuzzy-looking shadow.
- The fourth value sets the **base color** of the shadow.

Try experimenting with different values to see how it changes the appearance.

#### Centering the image

```css
img {
  display: block;
  margin: 0 auto;
}
```

Next, we center the image to make it look better. We could use the `margin: 0 auto` trick again as we did for the body. But there are differences that require an additional setting to make the CSS work.

The `<body>` is a block element, meaning it takes up space on the page. The margin applied to a block element will be respected by other elements on the page. In contrast, images are **inline** elements, for the auto margin trick to work on this image, we must give it block-level behavior using `display: block;`.

> **Note:** The instructions above assume that you're using an image smaller than the width set on the body. (600 pixels) If your image is larger, it will overflow the body, spilling into the rest of the page. To fix this, you can either: 1) reduce the image width using a **graphics editor**, or 2) use CSS to size the image by setting the `width` property on the `<img>` element with a smaller value.

> **Note:** Don't be too concerned if you don't completely understand `display: block;` or the differences between a block element and an inline element. It will make more sense as you continue your study of CSS. You can find more information about different display values on MDN's **display reference page**.

---

## JavaScript basics

**JavaScript** is a programming language that adds interactivity to your website. This happens in games, in the behavior of responses when buttons are pressed or with data entry on forms; with dynamic styling; with animation, etc. This article helps you get started with JavaScript and furthers your understanding of what is possible.

### What is JavaScript?

JavaScript is a powerful programming language that can add interactivity to a website. It was invented by Brendan Eich.

JavaScript is versatile and beginner-friendly. With more experience, you'll be able to create games, animated 2D and 3D graphics, comprehensive database-driven apps, and much more!

JavaScript itself is relatively compact, yet very flexible. Developers have written a variety of tools on top of the core JavaScript language, unlocking a vast amount of functionality with minimum effort. These include:

- Browser Application Programming Interfaces (**APIs**) built into web browsers, providing functionality such as dynamically creating HTML and setting CSS styles; collecting and manipulating a video stream from a user's webcam, or generating 3D graphics and audio samples.
- Third-party APIs that allow developers to incorporate functionality in sites from other content providers, such as Twitter or Facebook.
- Third-party frameworks and libraries that you can apply to HTML to accelerate the work of building sites and applications.

It's outside the scope of this article—as a light introduction to JavaScript—to present the details of how the core JavaScript language is different from the tools listed above. You can learn more in **MDN's JavaScript learning area**, as well as in other parts of MDN.

The section below introduces some aspects of the core language and offers an opportunity to play with a few browser API features too. Have fun!

### A "Hello world!" example

JavaScript is one of the most popular modern web technologies! As your JavaScript skills grow, your websites will enter a new dimension of power and creativity.

However, getting comfortable with JavaScript is more challenging than getting comfortable with HTML and CSS. You may have to start small, and progress gradually. To begin, let's examine how to add JavaScript to your page for creating a Hello world! example. (Hello world! is **the standard for introductory programming examples**.)

> **Warning:** If you haven't been following along with the rest of our course, **download this example code** and use it as a starting point.

1. Go to your test site and create a new folder named `scripts`. Within the scripts folder, create a new text document called `main.js`, and save it.
2. In your `index.html` file, enter this code on a new line, just before the closing `</body>` tag:

```html
<script src="scripts/main.js"></script>
```

3. This is doing the same job as the `<link>` element for CSS. It applies the JavaScript to the page, so it can have an effect on the HTML (along with the CSS, and anything else on the page).
4. Add this code to the `main.js` file:

```js
const myHeading = document.querySelector("h1");
myHeading.textContent = "Hello world!";
```

5. Make sure the HTML and JavaScript files are saved. Then load index.html in your browser. You should see something like this:

![Heading "hello world" above a firefox logo](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics/hello-world.png)

> **Note:** The reason the instructions (above) place the `<script>` element near the bottom of the HTML file is that **the browser reads code in the order it appears in the file**.
>
> If the JavaScript loads first and it is supposed to affect the HTML that hasn't loaded yet, there could be problems. Placing JavaScript near the bottom of an HTML page is one way to accommodate this dependency. To learn more about alternative approaches, see **Script loading strategies**.

#### What happened?

The heading text changed to *Hello world!* using JavaScript. You did this by using a function called `querySelector()` to grab a reference to your heading, and then store it in a variable called `myHeading`. This is similar to what we did using CSS selectors. When you want to do something to an element, you need to select it first.

Following that, the code set the value of the `myHeading` variable's **textContent** property (which represents the content of the heading) to *Hello world!*.

> **Note:** Both of the features you used in this exercise are parts of the **Document Object Model (DOM) API**, which has the capability to manipulate documents.

### Language basics crash course

To give you a better understanding of how JavaScript works, let's explain some of the core features of the language. It's worth noting that these features are common to all programming languages. If you master these fundamentals, you have a head start on coding in other languages too!

> **Warning:** In this article, try entering the example code lines into your JavaScript console to see what happens. For more details on JavaScript consoles, see **Discover browser developer tools**.

#### Variables

**Variables** are containers that store values. You start by declaring a variable with the `let` keyword, followed by the name you give to the variable:

```js
let myVariable;
```

A semicolon at the end of a line indicates where a statement ends. It is only required when you need to separate statements on a single line. However, some people believe it's good practice to have semicolons at the end of each statement. There are other rules for when you should and shouldn't use semicolons. For more details, see **Your Guide to Semicolons in JavaScript**.

You can name a variable nearly anything, but there are some restrictions. (See **this section about naming rules**.) If you are unsure, you can check your **variable name** to see if it's valid.

JavaScript is case sensitive. This means `myVariable` is not the same as `myvariable`. If you have problems in your code, check the case!

After declaring a variable, you can give it a value:

```js
myVariable = "Bob";
```

Also, you can do both these operations on the same line:

```js
let myVariable = "Bob";
```

You retrieve the value by calling the variable name:

```js
myVariable;
```

After assigning a value to a variable, you can change it later in the code:

```js
let myVariable = "Bob";
myVariable = "Steve";
```

Note that variables may hold values that have different **data types**:

| Variable | Explanation | Example |
|----|----|----|
| `String` | This is a sequence of text known as a string. To signify that the value is a string, enclose it in single quote marks. | `let myVariable = 'Bob';` |
| `Number` | This is a number. Numbers don't have quotes around them. | `let myVariable = 10;` |
| `Boolean` | This is a True/False value. The words **true** and **false** are special keywords that don't need quote marks. | `let myVariable = true;` |
| `Array` | This is a structure that allows you to store multiple values in a single reference. | `let myVariable = [1,'Bob','Steve',10];` Refer to each member of the array like this: `myVariable[0]`, `myVariable[1]`, etc. |
| `Object` | This can be anything. Everything in JavaScript is an object and can be stored in a variable. Keep this in mind as you learn. | `let myVariable = document.querySelector('h1');` All of the above examples too. |

So why do we need variables? Variables are necessary to do anything interesting in programming. If values couldn't change, then you couldn't do anything dynamic, like personalize a greeting message or change an image displayed in an image gallery.

#### Comments

Comments are snippets of text that can be added along with code. The browser ignores text marked as comments. You can write comments in JavaScript just as you can in CSS:

```js
/*
Everything in between is a comment.
*/
```

If your comment contains no line breaks, it's an option to put it behind two slashes l
ike this:

```js
// This is a comment
```

#### Operators

An `operator` is a mathematical symbol that produces a result based on two values (or variables). In the following table, you can see some of the simplest operators, along with some examples to try in the JavaScript console.

| Operator | Explanation | Symbol(s) | Example |
|----|----|----|----|
| `Addition` | Add two numbers together or combine two strings. | `+` | `6 + 9;` `'Hello ' + 'world!';` |
| `Subtraction, Multiplication, Division` | These do what you'd expect them to do in basic math. | `-`, `*`, `/` | `9 - 3;` `8* 2; // multiply in JS is an asterisk 9 / 3;` |
| `Assignment` | As you've seen already: this assigns a value to a variable.  | `=`  | `let myVariable = 'Bob';` |
| `Strict equality` | This performs a test to see if two values are equal. It returns a `true`/`false` (Boolean) result. | `===` | `let myVariable = 3;` `myVariable === 4;` |
| `Not, Does-not-equal` | This returns the logically opposite value of what it precedes. It turns a true into a false, etc.. When it is used alongside the Equality operator, the negation operator tests whether two values are not equal. | `!`, `!==` | For "Not", the basic expression is true, but the comparison returns false because we negate it: `let myVariable = 3;``!(myVariable === 3);` "Does-not-equal" gives basically the same result with different syntax. Here we are testing "is `myVariable` NOT equal to 3". This returns `false` because `myVariable` IS equal to 3: `let myVariable = 3;` `myVariable !== 3;` |

There are a lot more operators to explore, but this is enough for now. See Expressions and operators for a complete list.

> **Note:** Mixing data types can lead to some strange results when performing calculations. Be careful that you are referring to your variables correctly, and getting the results you expect. For example, enter `'35' + '25'` into your console. Why don't you get the result you expected? Because the quote marks turn the numbers into strings, so you've ended up concatenating strings rather than adding numbers. If you enter `35 + 25` you'll get the total of the two numbers.

#### Conditionals

Conditionals are code structures used to test if an expression returns true or not. A very common form of conditionals is the `if...else` statement. For example:

```js
let iceCream = "chocolate";
if (iceCream === "chocolate") {
  alert("Yay, I love chocolate ice cream!");
} else {
  alert("Awwww, but chocolate is my favorite…");
}
```

The expression inside the `if ()` is the test. This uses the strict equality operator (as described above) to compare the variable `iceCream` with the string `chocolate` to see if the two are equal. If this comparison returns `true`, the first block of code runs. If the comparison is not true, the second block of code—after the `else` statement—runs instead.

#### Functions

`Functions` are a way of packaging functionality that you wish to reuse. It's possible to define a body of code as a function that executes when you call the function name in your code. This is a good alternative to repeatedly writing the same code. You have already seen some uses of functions. For example:

```js
let myVariable = document.querySelector("h1");
```

```js
alert("hello!");
```

These functions, `document.querySelector` and `alert`, are built into the browser.

If you see something which looks like a variable name, but it's followed by parentheses— `()` —it is likely a function. Functions often take **arguments**: bits of data they need to do their job. Arguments go inside the parentheses, separated by commas if there is more than one argument.

For example, the `alert()` function makes a pop-up box appear inside the browser window, but we need to give it a string as an argument to tell the function what message to display.

You can also define your own functions. In the next example, we create a simple function which takes two numbers as arguments and multiplies them:

```js
function multiply(num1, num2) {
  let result = num1 * num2;
  return result;
}
```

Try running this in the console; then test with several arguments. For example:

```js
multiply(4, 7);
multiply(20, 20);
multiply(0.5, 3);
```

> **Note:** The `return` statement tells the browser to return the `result` variable out of the function so it is available to use. This is necessary because variables defined inside functions are only available inside those functions. This is called variable **scoping**. (Read more about **variable scoping**.)

#### Events

Real interactivity on a website requires event handlers. These are code structures that listen for activity in the browser, and run code in response. The most obvious example is handling the **click event**, which is fired by the browser when you click on something with your mouse. To demonstrate this, enter the following into your console, then click on the current webpage:

```js
document.querySelector("html").addEventListener("click", function () {
  alert("Ouch! Stop poking me!");
});
```

There are a number of ways to attach an event handler to an element. Here we select the `<html>` element. We then call its `addEventListener()` function, passing in the name of the event to listen to (`'click'`) and a function to run when the event happens.

The function we just passed to `addEventListener()` here is called an *anonymous function*, because it doesn't have a name. There's an alternative way of writing anonymous functions, which we call an *arrow function*. An arrow function uses `() =>` instead of `function ()`:

```js
document.querySelector("html").addEventListener("click", () => {
  alert("Ouch! Stop poking me!");
});
```

### Supercharging our example website

With this review of JavaScript basics completed (above), let's add some new features to our example site.

Before going any further, delete the current contents of your `main.js` file — the bit you added earlier during the "Hello world!" example — and save the empty file. If you don't, the existing code will clash with the new code you are about to add.

#### Adding an image changer

In this section, you will learn how to use JavaScript and DOM API features to alternate the display of one of two images. This change will happen as a user clicks the displayed image.

1. Choose an image you want to feature on your example site. Ideally, the image will be the same size as the image you added previously, or as close as possible.
2. Save this image in your `images` folder.
3. Rename the image **firefox2.png**.
4. Add the following JavaScript code to your `main.js` file.

```js
const myImage = document.querySelector("img");

myImage.onclick = () => {
  const mySrc = myImage.getAttribute("src");
  if (mySrc === "images/firefox-icon.png") {
    myImage.setAttribute("src", "images/firefox2.png");
  } else {
    myImage.setAttribute("src", "images/firefox-icon.png");
  }
};
```

5. Save all files and load `index.html` in the browser. Now when you click the image, it should change to the other one.

This is what happened. You stored a reference to your `<img>` element in the `myImage` variable. Next, you made this variable's `onclick` event handler property equal to a function with no name (an "anonymous" function). So every time this element is clicked:

1. The code retrieves the value of the image's `src` attribute.
2. The code uses a conditional to check if the `src` value is equal to the path of the original image:
    - If it is, the code changes the `src` value to the path of the second image, forcing the other image to be loaded inside the `<img>` element.
    - If it isn't (meaning it must already have changed), the `src` value swaps back to the original image path, to the original state.

#### Adding a personalized welcome message

Next, let's change the page title to a personalized welcome message when the user first visits the site. This welcome message will persist. Should the user leave the site and return later, we will save the message using the **Web Storage API**. We will also include an option to change the user, and therefore, the welcome message.

1. In `index.html`, add the following line just before the `<script>` element:

```html
<button>Change user</button>
```

2. In `main.js`, place the following code at the bottom of the file, exactly as it is written. This takes references to the new button and the heading, storing each inside variables:

```js
let myButton = document.querySelector("button");
let myHeading = document.querySelector("h1");
```

3. Add the following function to set the personalized greeting. This won't do anything yet, but this will change soon.

```js
function setUserName() {
  const myName = prompt("Please enter your name.");
  localStorage.setItem("name", myName);
  myHeading.textContent = `Mozilla is cool, ${myName}`;
}
```

The `setUserName()` function contains a `prompt()` function, which displays a dialog box, similar to `alert()`. This `prompt()` function does more than `alert()`, asking the user to enter data, and storing it in a variable after the user clicks OK. In this case, we are asking the user to enter a name. Next, the code calls on an API `localStorage`, which allows us to store data in the browser and retrieve it later. We use localStorage's `setItem()` function to create and store a data item called `'name'`, setting its value to the `myName` variable which contains the user's entry for the name. Finally, we set the `textContent` of the heading to a string, plus the user's newly stored name.

4. Add the following condition block. We could call this initialization code, as it structures the app when it first loads.

```js
if (!localStorage.getItem("name")) {
  setUserName();
} else {
  const storedName = localStorage.getItem("name");
  myHeading.textContent = `Mozilla is cool, ${storedName}`;
}
```

This first line of this block uses the negation operator (logical NOT, represented by the `!`) to check whether the `name` data exists. If not, the `setUserName()` function runs to create it. If it exists (that is, the user set a user name during a previous visit), we retrieve the stored name using `getItem()` and set the `textContent` of the heading to a string, plus the user's name, as we did inside `setUserName()`.

5. Put this `onclick` event handler (below) on the button. When clicked, `setUserName()` runs. This allows the user to enter a different name by pressing the button.

```js
myButton.onclick = () => {
  setUserName();
};
```

#### A user name of null?

When you run the example and get the dialog box that prompts you to enter your user name, try pressing the Cancel button. You should end up with a title that reads Mozilla is cool, null. This happens because—when you cancel the prompt—the value is set as `null`. Null is a special value in JavaScript that refers to the absence of a value.

Also, try clicking OK without entering a name. You should end up with a title that reads Mozilla is cool, for fairly obvious reasons.

To avoid these problems, you could check that the user hasn't entered a blank name. Update your `setUserName()` function to this:

```js
function setUserName() {
  const myName = prompt("Please enter your name.");
  if (!myName) {
    setUserName();
  } else {
    localStorage.setItem("name", myName);
    myHeading.textContent = `Mozilla is cool, ${myName}`;
  }
}
```

In human language, this means: If `myName` has no value, run `setUserName()` again from the start. If it does have a value (if the above statement is not true), then store the value in `localStorage` and set it as the heading's text.

---
