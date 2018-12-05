# The DOM

So far we've only dealt with JavaScript in isolation. Let's learn how to use JavaScript to print data directly to our web page. 


When a web page is loaded, the browser creates a Document Object Model of the page. The DOM allows JavaScript to access and alter your HTML in the browser.

Say you had the following HTML:

```html
<body>
  <h1 id="main-heading"></h1>
</body>
```

Let's use JavaScript to put some text in that empty `h1` element. 

First, we need to get a reference to it. With CSS, it's best practice to target elements with classes. With JavaScript, it's best to target them with id's. 

```js
var headingElement = document.querySelector("#main-heading");
```

Cool! We have a reference to our DOM element in our JavaScrpt file. It's stored in a variable called `headingElement`. Now let's put some text in it:
```js
headingElement.innerHTML = "Hello, world!";
```
When we refresh, we should see a big old "Hello, world!" at the top of our page.

(Note: The `innerHTML` property will overwrite anything that's already in the element you're targeting. If there had already been text in our `h1` element, this example code would've replaced it.) 

Let's look at a slightly more complex example. Let's say we run a restaurant store and want to feature our daily special on our website. Rather than hard-coding it into our HTML we should populate the `div` dynamically with JavaScript.

Here's some sample HTML:
```html
<body>
  <div id="daily-special">
  </div>
</body>
```
```js
// The contents of this object will change depending on what today's special is
var currentSpecial = {
  name: "Fried Green Tomato BLT",
  description: "So good you'll cry",
  price: 9.99
}

// We'll use the object to build up an HTML string 
var htmlString = `
  <h3 class="dish-name">${currentSpecial.name}</h3>
  <p class="dish-description">
    ${currentSpecial.description}
  </p>
  <h5 class= "dish-price">${currentSpecial.price}</h5>
`
// Then we'll put the html string in the #daily-special div
document.querySelector("#daily-special").innerHTML = htmlString;
```

Now, when the daily specia changes, we only need to change the contents of the object.

# Practice

These commands are a helpful quick start. You may choose to ignore them completely and create your own directory structure. If you choose to use this recommendation, just copy the commands below. It doesn't matter what directory you are currently in.
```
mkdir -p ~/workspace/on-boarding/exercises/javascript/the_dom && cd $_
touch index.html script.js
```
Be sure to add boilerplate HTML to your `index.html` file and link it to `script.js`.
#### 1. Movie Poster

1. Copy and paste the following code between the `<body>` tags of your HTML document:
```html
<section id="movie-poster">
  <h1 id="title"></h1>
  <h2 id="genre"></h2>
  <h3 id="release-date"></h3>
</section>
```

2. In your JavaScript file, copy and paste the following object:
```js
var movieObject = {
  title: "Star Wars: A New Hope",
  genre: "Science Fiction",
  release-date: "May 25, 1977"
}
```
3. Use `document.querySelector()` to grab a reference to each element in your HTML. Use the `.innerHTML` property to set the text of each element to the matching value in your object. (For example, the `h1` with the id of "title" should contain the `title` property of your `movieObject`, etc). 

#### 2. Challenge: Movie Schedule
You've been hired to build an app for a movie theater. You need to list all of the movies that are currently playing. 

Start with some basic HTML: 
```html
<body>
  <div id="movie-schedule"></div>
</body>
```
In your JavaScript file, copy and paste the following array of objects: 
```js
var movieSchedule = [
  {
    title: "Ralph Breaks the Internet",
    rating: "PG",
    poster: "https://lumiere-a.akamaihd.net/v1/images/r_ralphbreakstheinternet_header_ddt-17403_08ef6d92.jpeg?region=0,0,1024,1274&optimize=true"
  }, 
  {
    title: "The Grinch",
    rating: "G",
    poster: "https://images-na.ssl-images-amazon.com/images/I/71vgX4VFdiL._SY679_.jpg"
  },
  {
    title: "Fantastic Beasts: The Crimes of Grindlewald",
    rating: "PG-13",
    poster: "https://images-na.ssl-images-amazon.com/images/I/716fk%2BBZ-NL._SY606_.jpg"
  }
]
```
- In your JavaScript file, use the `movieSchedule` data to build up an HTML string like the one in the "daily special" example above. 
- You can use any elements you like in your HTML string as long as all the data in the `movieSchedule` object is included. 
- (*Hint: if you want to take advantage of VS Code's autocomplete features, you can type most of this in your HTML document and then cut and paste it into your JavaScript file.*)
- Use `document.querySelector` to select the element in your HTML file with an id of `"movie-schedule"`
- Use the `.innerHTML` property to set the contents of the `"movie-schedule"` container equal to the HTML string you just created.

