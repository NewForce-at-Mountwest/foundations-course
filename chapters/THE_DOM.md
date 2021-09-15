# Printing to the DOM

So far we've dealt with JavaScript in isolation from HTML and CSS. Let's learn how to combine them.


When a web page is loaded, the browser creates something called a Document Object Model (DOM) of the page. It's basically a copy of your web page that gets stored in the browser's memory. (The word DOM is confusing. We get it. For now, any time you hear it you can just substitue in "how the website looks"). We can use JavaScript to access and change the DOM.

## Setting up your project
You will need two files:
1. `index.html`
3. `script.js`

Once you have your files, use the `Shift` + `!` shortcut in your HTML document to generate your boilerplate HTML. Then add the following line of code before the closing body tag:

```js
<script src="script.js"></script>
```
This will link your JavaScript file to your HTML document so that your JS file loads in the browser. 
_(Note: You don't need CSS for this chapter, but if you wanted to add some CSS you would have to add a `link` element inside the `<head>` tags of your HTML document as well.)_

## Accessing the DOM
Say you have the following HTML element:

```html
  <h1 id="main-heading"></h1>
```

Empty, right? Super boring. Let's use JavaScript to put some fun text in that sad, lonely `h1` element. 

First, we need JavaScript to know which element we're talking about.

```js
const headingElement = document.querySelector("#main-heading");
```
## Printing to the DOM
Now we have a reference to our DOM element in our JavaScrpt file. It's stored in a variable called `headingElement`. Let's put some text in it:
```js
headingElement.innerHTML = "TIME TO PARTY!";
```
We should see a big old "TIME TO PARTY" at the top of our page.

(Note: The `innerHTML` property will overwrite anything that's already in the element you're targeting. If there had already been text in our `h1` element, this example code would've replaced it.) 
*** 

## Lightning Exercise 
### Hello, world
1. In your `index.html` file, add an `h2` element with an id of `#hello-container`.
1. In your JavaScript file, target the `h2` element you just created by its id
2. Use the `.innerHTML` property to print the text "Hello, world" into the H2 

***

## Pulling it all together

Imagine we wanted to print the entire menu to the DOM. Let's start with an array of  menu items:
```js
const menuItemsArray = ["Chicken tenders", "pizza", "spaghetti", "french fries", "pie"]
```
We can go ahead and add an unordered list container to our HTML file. This is where we'll put our list of menu items:
```html
<ul id="menu-items-container"></ul>
```
Now our job is to loop through the menu items and add each one to the `#menu-items-container` element.
```js
for(let i = 0; i < menuItemsArray.length; i++){
  // target the menu items container and add a bullet for each item in the array
  document.querySelector("#menu-items-container").innerHTML += `<li>${menuItemsArray[i]}</li>`

}
```

Notice that we use `+=` here. The `+=` operator _adds to_ the existing HTML content of `#menu-items-container`. Here's another way of writing it:
```js
document.querySelector("#menu-items-container").innerHTML =  document.querySelector("#menu-items-container").innerHTML + `<li>${menuItemsArray[i]}</li>`
```

***
## Lightning Exercise 
### Keeping track of chores
1. In your `index.html` file, create an empty `<ul>` element and give it an id of `#chores-container`
1. In your JavaScript file, declare a new variable called `choresArray`. This should be an array of chores you do regularly.
1. Loop through your `choresArray`. For each chore, create a new `<li>` element and insert it into the `#chores-container` element. 
1. You should end up with a bulleted list of all your regular chores.

*** 

## Practice

These commands are a helpful quick start. You may choose to ignore them completely and create your own directory structure. If you choose to use this recommendation, just copy the commands below. It doesn't matter what directory you are currently in.
```
mkdir -p ~/workspace/on-boarding/exercises/javascript/the_dom && cd $_
touch index.html script.js
```
Be sure to add boilerplate HTML to your `index.html` file and link it to `script.js`.

### 1. Movie Poster

- Copy and paste the following code between the `<body>` tags of your HTML document:
```html
<section id="movie-poster">
  <h1 id="title"></h1>
  <h2 id="genre"></h2>
  <h3 id="release-date"></h3>
</section>
```

- In your JavaScript file, copy and paste the following object:
```js
const movieObject = {
  title: "Star Wars: A New Hope",
  genre: "Science Fiction",
  releaseDate: "May 25, 1977"
}
```
- Use `document.querySelector()` to grab a reference to each element in your HTML. Use the `.innerHTML` property to set the text of each element to the matching value in your object. (For example, the `h1` with the id of "title" should contain the `title` property of your `movieObject`, etc). 


### 2. Downtown Restaurants
- Copy and paste the following array into your JavaScript file:
```js
var downtownRestaurants = ["Backyard Pizza and Raw Bar", "The Bodega", "Surin of Thailand", "Bahnhof", "Jim's Steak and Spaghetti House", "The Peddler", "Jewel City Seafood Market", "Black Sheep Burritos & Brews", "La Famiglia", "Le Bistro", "Charlie Graingers", "The Cellar Door"];
```
- Copy and paste the following code into your `index.html` file:
```html
<ul id="restaurants-list"></ul>
```
- Loop over the `downtownRestaurants` array.
- Use the loop to create an `<li>` element for each item in the array.
- Use `document.querySelector` and `.innerHTML` to add each new `<li>` element to the `#restaurants-list` container.
- You should see a bulleted list of restaurants in the DOM.

### 3. Sandwich Toppings
- Copy and paste the following array into your JavaScript file:
```js
var sandwichToppings = ["pickles", "extra cheese", "lettuce", "tomatoes", "avocado", "bacon", "mayo", "mustard"]
```
- Copy and paste the following code into your `index.html` file:
```html
<ul id="sandwich-container"></ul>
```
- Write a function that does the following things:
    - Loop through `sandwichToppings`
    - Build an `<li>` element for each item in the array.
    - Use `document.querySelector` and `.innerHTML` to print your HTML string to the `"#sandwich-container"`.
- Call the function. You should see a bulleted list of all the sandwich toppings in the DOM.



## Challenges

### 4. Movie Schedule 

You've been hired to build an app for a movie theater. You need to list all of the movies that are currently playing. 

Start with some basic HTML: 
```html
<body>
  <div id="movie-schedule"></div>
</body>
```
In your JavaScript file, copy and paste the following array of objects: 
```js
let movieSchedule = [
  {
    title: "Ralph Breaks the Internet",
    rating: "PG",
    currentlyPlaying: true,
    poster: "https://lumiere-a.akamaihd.net/v1/images/r_ralphbreakstheinternet_header_ddt-17403_08ef6d92.jpeg?region=0,0,1024,1274&optimize=true"
  }, 
  {
    title: "The Grinch",
    rating: "G",
    currentlyPlaying: true,
    poster: "https://images-na.ssl-images-amazon.com/images/I/71vgX4VFdiL._SY679_.jpg"
  },
  {
    title: "A Star is Born",
    rating: "R",
    currentlyPlaying: false,
    poster: "https://images-na.ssl-images-amazon.com/images/I/718zWbDKmvL._SY606_.jpg"
  },
   {
    title: "Bohemian Rhapsody",
    rating: "PG-13",
    currentlyPlaying: true
  },
  {
    title: "Fantastic Beasts: The Crimes of Grindlewald",
    rating: "PG-13",
    currentlyPlaying: true,
    poster: "https://images-na.ssl-images-amazon.com/images/I/716fk%2BBZ-NL._SY606_.jpg"
  },
  {
    title: "Robin Hood",
    rating: "PG-13",
    currentlyPlaying: false,
    poster: "https://images-na.ssl-images-amazon.com/images/I/61K%2BTyGjsCL.jpg"
  },
  {
    title: "Spider-Man: Into the Spider-Verse",
    rating: "PG-13",
    currentlyPlaying: true,
  }
]
```
- Use a for loop to loop through the movies, build an HTML representation of each movie, and insert it into the `#movie-schedule` container in the DOM.
- You can use any elements you like in your HTML string as long as all the data in the `movieSchedule` object is included.


 
 ## More Challenges: 

### 5. Movie Schedule: Revamped and Reloaded: The Scheduling
 - Revisit your movie schedule exercise from above.
 - Add a conditional so that you only print movies where the `currentlyPlaying` property is equal to `true`. 
 - Use flexbox to arrange your movie schedule side by side on your web page.
 - If a movie does not have a `poster` property, give it a [placeholder image like this](https://www.snhrc.com/wp-content/uploads/2018/09/Image-Coming-Soon.png)
 - Give all G-rated movies a dotted green border that's 2px wide.
 - Give all PG-rated movies a dotted yellow border that's 2px wide.
 - Give all PG-13 movies a dotted orange border that's 2px wide.
 - Give all R-rated movies a dotted red border that's 2px wide.


### 6. Cohort Website
1. Copy and paste the following code inside the `body` tags of your HTML file:
```html
<div id = "cohort-one-container">
</div>
<div id = "cohort-two-container">
</div>
<div id = "cohort-three-container">
</div>
```
2. Copy and paste the following code in your JavaScript file:
```js
var cohort1 = {
  name: "Cohort One",
  startDate: "January 15, 2018",
  endDate: "July 12, 2019",
  instructors: ["Kim", "Josh", "Jordan"],
  techStack: ["HTML", "CSS", "JavaScript", "React", "C#", ".NET"]
}

var cohort2 = {
 name: "Cohort Two",
 startDate: "August 15, 2019",
 endDate: "Feb 10, 2020",
 instructors: ["Tommy", "Jordan],
 techStack: ["HTML", "CSS", "JavaScript", "React", "C#", ".NET"]
}

var cohort3 = {
 name: "Cohort Three",
 startDate: "April 6, 2020",
 endDate: "August 20, 2020",
 instructors: ["Tommy", "Jordan"],
 techStack: ["HTML", "CSS", "JavaScript", "React", "C#", ".NET"]
}

function buildHtmlString(cohortObjectParameter){
  // YOUR CODE GOES HERE
}

function printHtmlString(htmlStringParameter, elementIdParameter){
  // YOUR CODE GOES HERE
}

```
3. The `buildHtmlString` function should take an cohort object as a parameter and return a HTML string with the following elements:
    - An `h1` of the cohort's name
    - An `h3` for the start date
    - An `h3` for the end date
    - An unordered list of instructors
    - An unordered list of technologies learned
4. The `printHtmlString` function should take two parameters:
    - An HTML string
    - The `id` of the element into which you want to print your HTML string
5. The `printHtmlString` function should do the following things:
    - Use `document.querySelector` to get a reference to the element in the DOM with whatever id you passed in.
    - Use `innerHTML` to print the HTML string you passed in to the DOM.
6. Call the `buildHTMLString` function and pass in `cohort1` as an example.
7. Store the returned value in a new variable called `cohort1HTML`.
8. Call the `printHtmlString` function and pass in your `cohort1HTML` variable and the id of the element you want to print to (`"cohort-one-container"`).
9. Repeat steps 6-8 for `cohort2` and `cohort3`

### 7. Weather Data 

1. Copy and paste the data from the Yahoo Weather API into your JS file. You can find it at the bottom of the [variables and data types chapter](./VARIABLES_AND_DATATYPES.md).

1. Copy and paste the following HTML anywhere between the `<body>` tags of your `index.html` file.
```html
<header id="current-weather">
</header>
<div id="weather-forecast">
</div>
```
2. In your JavaScript file, use the weather data to create an HTML string representing the current weather conditions. Your HTML string should include the following elements:
    - An `h1` representing location (city, country, and region)
    - An `h2` representing current conditions weather conditions including temperature ("28 degrees F and blowing snow" is fine)
3. Use `document.querySelector` to grab a reference to the element with an id of `"current-weather"`
4. Use `.innerHTML` to insert your HTML string into the `"current-weather"` element.
5. Create another HTML string representing a three day forecast. Each day should have its own `div` with a class of `forecast-day`. Each `div` should have the following child elements:
    - An `h3` element with the day of the week and the date (Example: "Thu, 06 Dec 2018")
    - A `p` element with the high temperature
    - A `p` element with the low temperature
    - A `p` element with the text (i.e. "snow")
6. Use `document.querySelector` to grab a reference to the element with an id of `"weather-forecast"`
4. Use `.innerHTML` to insert your HTML string into the `"weather-forecast"` element.
3. If you don't already have one, create a CSS stylesheet in your directory.
4. Use flexbox to arrange your `.forecast-day` elements side by side on the page. They should be spaced evenly and wrap when the screen is resized.
5. Each `.forecast-day` element should have a padding of `1rem`;
6. If *all* the high temperatures in the three day forecast are above 85, the background color of the page should be light red.
7. If *all* of the high temperatures in the three day forecast are below 40, the background color of the page should be light blue.
8. If *any* of the low temperatures are below 20, the background of each individual `".forecast-day"` element should be dark blue. 
9. If *any* of the high temperatures are above 95, the background of each individual `".forecast-day"` element should be dark red.
