# HTML

HTML stands for __Hyper Text Markup Language__. It defines the structure and content of a web page.

## The Building Blocks of HTML

__Elements__ are the building blocks of HTML pages. This is an HTML element representing a page heading:
```html
<h1> My Awesome Website </h1>
```

Elements are labeled with __tags__. In the example above, `<h1>` is the opening tag and `</h1>` is the closing tag. Everything that goes between them is the content you'll see on the web page.

Here's a few basic HTML tags to take for a spin:

Headings
```html
<h1>, <h1>, <h3> ... <h6>
```

Text
```html
<p>, <section>, <article>
```

Images
```html
<img src="path/to/image" alt="Alternate text">
```

Links
```html
<a href="www.spacejam.com"> Click Here </a>
```

All-purpose container:
```html
<div>
```

## Nesting HTML Elements
When we nest HTML elements inside each other, we talk about the relationships in terms of parents and children. Unordered and ordered lists are a good example of this:
```html
<ul>
  <li> I'm one bulleted item</li>
  <li> I'm another bulleted item </li>
<ul>

<ol>
  <li>I'm one numbered item</li>
  <li> I'm another numbered item</li>
<ol>
```
In the first example above, the `<li>` elements are children of the `<ul>` element.

In the example below, the article element is a child of the section element. It's also the parent of the heading 3 and two paragraph elements.

```html
<h1> How To Wrestle Gators </h1>

<section>
  <h2> Gator Wrestling 101 </h2>
  <article>
    <h3> Step One: Picking the Right Gator </h3>
    <p> Lorem ipsum dolor sit amet, consectetur adipiscing elit. </p>
    <p> Lorem ipsum dolor sit amet, consectetur adipiscing elit. </p>
  </article>
</section>

```
***
## Lightning Exercise

### HTML Elements
In your `index.html` file, create the following elements:
  - An `h1` element with your name in it.
  - A `p` element with some copy-and-pasted text from the [Bob Ross Lorem Ipsum Generator](https://www.bobrosslipsum.com/)
  - An `img` element with the `src` value of `"https://media.giphy.com/media/Z3ChoP3rZewhy/giphy.gif"` and any `"alt"` value you like.

***

## Attributes

HTML elements can have attributes that distinguish them from other elements or tell the how to behave.

In the example above, imagine you needed to tell the difference between the two paragraphs. You could give them a `class` and/or an  `id`.

- Ids have to be unique.
- Classes can be used for multiple elements

```html
<p id="firstParagraph" class="background-blue">
 Lorem ipsum dolor sit amet, consectetur adipiscing elit.
</p>

<p id="secondParagraph" class="background-blue">
 Lorem ipsum dolor sit amet, consectetur adipiscing elit.
</p>
```

Remember our friends the ```<img>``` and ```<a>``` tags?

```html
<img src="path/to/image" alt="Alternate text">

<a href="www.spacejam.com"> Click Here </a>
```

Both `src` and `href` are attributes. The `src` attribute tells the browser where to look for the image file and `alt` specifies an alternate text for an image. The `href` attribute tells the browser where to go when the user clicks on the hyperlink.

We'll use ids and classes a lot when we get to CSS and JavaScript.

***
## Lightning Exercise
### Classes and Ids
In your `index.html` file, create the following elements:
  - A `section` element with a class of `"bio"`
  - Inside the `"bio"` section, a `"ul"` element with a class of `"tech-stack"`
  - Inside `"tech-stack"`, two `"li"` elements:
      - The first `"li"` element should have an id of `"html"`
      - The second should have an id of `"css"`

***

## HTML Document Structure

Here's an example of an HTML document:

```html

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Document</title>
</head>
<body>
  <!-- Everything you want to show up on your web page goes between these two tags -->
</body>
</html>

```

Now let's break it down:
1. `<!DOCTYPE html>` lets the browser know that it's getting an HTML document
1. ` <html lang="en">` tells the browser that our document is written in English.
1. The `<head>` element contains meta information about our web page that helps the browser figure out how to read it. Nothing inside the `<head>` tags will be displayed on the web page.
1. The `<body>` element contains everything you'll see on the page. All the HTML you write should go between the `body` tags.





## Practice

These commands are a helpful quick start. You may choose to ignore them completely and create your own directory structure. If you choose to use this recommendation, just copy the commands below. It doesn't matter what directory you are currently in.
```
mkdir -p ~/workspace/foundations/exercises/personal-website && cd $_
touch index.html
```

1. In `index.html`, press `shift` + `!` and you should see some boilerplate HTML.
1. Create a personal website to market yourself as a developer. Don't worry about coming up with all the text, just use a [lorem ipsum generator](https://www.shopify.com/partners/blog/79940998-15-funny-lorem-ipsum-generators-to-shake-up-your-design-mockups). The web page should have:
  - A  `header` element with the following child elements:
      - An `<h1>` element with your name
      - An `<h2>` element with your job title
  - An `<aside>` element with your bio:
      - An `<h3>` heading
      - A `<p>` element with your bio text
      - An `<img>` element with a picture of yourself
  - A `<section>` element for the techologies you'll know at the end of this program. It should contain:
      -  An `<h3>` heading
      - A bulleted list of at least three languages. (HTML, CSS, and JavaScript are fine for now.)
  - A `<section>` element about your work experience. It should contain:
      - An `<h3>` heading
      - An `<article>` element for each major point in your work history
  - A `<footer>` element with the text "Built by [your name]"

Your website will look pretty bad right now, but that's okay! CSS is up next.
