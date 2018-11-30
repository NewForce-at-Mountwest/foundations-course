The DOM

So far we've only dealt with JavaScript in isolation. Let's learn how to use JavaScript to print data directly to our web page. 


When a web page is loaded, the browser creates a Document Object Model of the page. The DOM allows JavaScript to access and alter your HTML in the browser.

Say you had the following HTML:

```html
<body>
  <h1 id="main-heading"></h1>
</body>
```

Let's fill in that empty `h1` element. First, we need to get a reference to it. With CSS, it's best practice to target elements with classes. With JavaScript, it's best to target them with id's. 

```js
var headingElement = document.querySelector("#main-heading");
```

Cool! We have a reference to our DOM element. Now let's put some text in it:
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
#### 4. Movie Poster
1. In your HTML document, create the following elements. Don't add any text yet.
    - An `h1` element with an id of "title"
    - An `h3` element with an id of "genre"
    - Another `h3` element with an id of "release-date"

2. In your JavaScript file, create an object that represents a movie. Your object should include the following data:
    - Title
    - Genre
    - Release date
3. Use `document.querySelector()` to grab a reference to each element in your HTML. Use the `.innerHTML` property to set the text of each element to the matching value in your object. (For example, the `h1` with the id of "title" should contain the title from your object, etc). 

### Challenge: Movie Schedule
You've been hired to build an app for a movie theater. You need to list all of the movies that are currently playing. Here's some sample data to 
