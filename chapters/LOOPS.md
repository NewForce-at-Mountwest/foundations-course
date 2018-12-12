# Loops

We've dealt with a few situations where we wanted to do something to every item in an array (log it to the console, print it to the DOM, etc). We purposefully kept our arrays short, but we won't always have that luxury. Let's revisit one of the practice exercises from the [Variables and Data Types](./VARIABLES_AND_DATATYPES.md) Chapter:

```
1. In your JavaScript file, instantiate and assign a variable called `movieArray`. This variable should hold an array of your favorite movie titles. (Don't go overboard- two or three is fine).

1. Log each movie in the array to the console.
```

What if, instead of making your own array of favorite movies, you were given an array with 200 movies in it and told to log each one the console? You'd probably want to throw your computer out the window after a few seconds of this:
```js
console.log(movieArray[0])
console.log(movieArray[1])
console.log(movieArray[2])
.
.
.
console.log(movieArray[200])
```
Fortunately, computers are really good at doing repetitve tasks quickly. Whenever we want to repeat an action multiple times, we use a loop to do the grunt work for us.
## While Loops
Here's a bare-bones while loop. This code will log `"Hello, world"` to the console 20 times and then stop.   
```js
var i = 1;

while(i < 20){
  console.log("Hello, world");
  i++;
}
```
Let's break it down:
- `var i = 0` declares `i` as our counter variable and sets it equal to 0.
- The code inside the curly braces will run *while* the expression in the parentehses evaluates to true.
- The first time the loop runs, `i` is `1`. Is `1` less than `20`? Yep, that's true! The code between the parentheses can run. It does two things:
    - Log `"Hello, world"` to the console
    - `i++` is the same thing as writing `i = i + 1`. We're reassigning it to be one more than itself. 
- The second time the loop runs, `i` will be 2. Is `2` less than `20`? Yep! The code block runs again.
- This process keeps going until `i` is no longer less than `20`. As soon as that expression evaluates to `false`, the loop stops.

Let's look at a more practical example. 
```js
var moviesArray = ["Casablanca", "Star Wars", "Singing in the Rain", "The Wizard of Oz", "Die Hard"];

var i = 0; 

while(i < moviesArray.length){
  console.log(moviesArray[i]);
  i++;
}
```
What's going on here?

- Remember that `moviesArray.length` evaluates to a number. In this example, `moviesArray.length` is 5 because there are 5 items in the array. 
- The first time the loop runs, it checks to see if `i < moviesArray.length` evaluates to true. We just set `i` equal to `0` and we know that `moviesArray.length` is `5`. Is `0` less than `5`? Yep! It evaluates to `true`, so the code inside the curly braces runs. 
    - We log `moviesArray[i]` to the console. Right now, `i` is `0`, so that's the same thing as writing `moviesArray[0]`. We should see `"Casablanca"` logged to the console.
    - `i` increments by 1. 
- Now, on the second iteration, `i` is `1`. We do the whole process again. Is `1` less than `5`? Yep, true! The code inside the curly braces runs again, except this time it prints `moviesArray[1]` to the console, so we see `"Star Wars"`.
- This process continues and `i` keeps incrementing until it's no longer less than 5. (At that point, we've gotten to the end of the array.) 

## For Loop
While loops are great for learning how loops work, but we won't actually use them very much. The for loop is much more common. It works the exact same way, but the syntax is different.

```js
for(var i = 0; i < moviesArray.length; i++){
  console.log(moviesArray[i]);
}
```
This does the exact same thing as the while loop we wrote in the first example. 
In a for loop, we have three expressions inside the parentheses that tell the loop how to behave:
1. The first expression (`var i = 0`) declares our counter variable. Our loop will start counting at 0.
1. The second expression (`i < moviesArray.length`) is the condition that must be `true` for the code block to run. In this case, the loop will keep going as long as `i` is less than `moviesArray.length`. 
1. The third expression (`i++`) tells the counter varaible how to increment. Each time the loop runs, `i` will increase by 1.


# Practice

These commands are a helpful quick start. You may choose to ignore them completely and create your own directory structure. If you choose to use this recommendation, just copy the commands below. It doesn't matter what directory you are currently in.
```
mkdir -p ~/workspace/on-boarding/exercises/javascript/loops && cd $_
touch index.html script.js
```
Be sure to add boilerplate HTML to your `index.html` file and link it to `script.js`.
#### 1. Psychotic Bird
In your JavaScript file, write a while loop that outputs the phrase "TWEET TWEET" 100 times to the console. 

#### 2. Psychotic Bird: For Loop Edition
In your JavaScript, write a for loop that outputs the phrase "TWEET TWEET" 100 times to the console. 

#### 3. Favorite Foods
- In your JavaScript array, create a new variable called `favoriteFoods`. It should store an array of strings representing five of your favorite foods.
- Loop through the array and print each food item to the console.

#### 4. Interests
- In your JavaScript file, create an array of 5 of your interests.
- Loop through the interests and console log the phrase "One of my interests is: [your interest]." for each of the interests in your array.
- Pick your favorite interest. Add an if statement in your loop that checks each time if the interest is your favorite interest. For the one item that is your favorite, console log "My absolute favorite interest is: [your favorite interest]." Still console log the message for each of your other interests from the step above.
##### Output:
```
One of my interests is: hiking. 
My absolute favorite interest is: coding. 
One of my interests is: math. 
One of my interests is: 30 Rock. 
One of my interests is: pizza.
```

#### 5. Harry Potter Titles
- Copy and paste the following array into your JavaScript file: 
```js
var harryPotterTitles = ["and the Sorcerer's Stone", "and the Chamber of Secrets", "and the Prisoner of Azkaban", "and the Goblet of Fire", "and the Order of the Phoenix", "and the Half-Blood Prince", "and the Deathly Hallows"];
```
- Use a for loop to output the complete titles to the console. Expected output: 
```
"Harry Potter and the Sorcerer's Stone"
"Harry Potter and the Chamber of Secrets"
.
.
.
"Harry Potter and the Deathly Hallows"
```

#### 6. Student Grades Take Two
- Copy and paste the folowing array of grades into your JavaScript file:
```js
var grades = [92, 91, 75, 66, 52, 90, 83, 85, 64, 90, 72, 88, 77, 98, 100, 73, 92]
```
- Loop through the grades with a for loop
    - If the current grade is greater than or equal to 0 and less than or equal to 69, log "You got an F" to the console.
    - If it's between 70 and 76, log "You got a D" to the console.
    - If it's between 77 and 84, log "You got a C" to the console.
    - If it's between 84 and 92, log "You got a B" to the console.
    - If it's between 93 and 100, log "You got an A" to the console.
    
    
    
#### 7. Interrupting Cow
1. Copy and paste the following array into your JavaScript file:
```js
var sentenceArray = ["the", "cow", "danced", "through", "the", "trees", "in", "the", "light", "of", "the", "moon"];
```
2. Copy and paste the following code into your HTML document:
```html
<span id="cow-sentence"></span>
```
3. Write a loop that builds `sentenceArray` into a real sentence, except every fourth word should be "MOOOOOO". Hint: look up the [modulus operator](https://www.w3schools.com/js/js_arithmetic.asp). 
4. Use `document.querySelector` and `.innerHTML` to print your sentence to the DOM.

Expected output:
```
the cow danced MOOOOOOOO through the trees MOOOOOOOO in the light MOOOOOOOO of the moon
```

#### 8. Downtown Restaurants
1. Copy and paste the following array into your JavaScript file:
```js
var HTMLString = "";

var downtownRestaurants = ["Backyard Pizza and Raw Bar", "The Bodega", "Surin of Thailand", "Bahnhof", "Jim's Steak and Spaghetti House", "The Peddler", "Jewel City Seafood Market", "Black Sheep Burritos & Brews", "La Famiglia", "Le Bistro", "Charlie Graingers", "The Cellar Door"];
```
2. Copy and paste the following code into your `index.html` file:
```html
<ul id="restaurants-list"></ul>
```
3. Loop over the `downtownRestaurants` array.
4. Inside the loop, build up your `HTMLString` with an `<li>` element for each item in the array.
5. Use `document.querySelector` and `.innerHTML` to print your `HTMLString` to the DOM.
6. Here's an example of what you should see on the DOM when you're done:
<ul>
 <li>Backyard Pizza and Raw Bar</li>
  <li>The Bodega</li>
  <li>Surin of Thailand</li>
  <li>Bahnhof</li>
  <li>Jim's Steak and Spaghetti House</li>
  <li>The Peddler</li>
  <li>Jewel City Seafood Market</li>
  <li>Black Sheep Burritos & Brews</li>
  <li>La Famiglia</li>
  <li>Le Bistro</li>
  <li>Charlie Graingers</li>
  <li>The Cellar Door</li>
</ul>


#### 9. Movie Schedule Take Two

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
- Use a for loop to loop through the movies and build up an HTML string to represent the data. 
- You can use any elements you like in your HTML string as long as all the data in the `movieSchedule` object is included. It'll probably look pretty similar to the movie poster you made in the chapter on [The DOM](./THE_DOM.md).
- (*Hint: if you want to take advantage of VS Code's autocomplete features, you can type most of this in your HTML document and then cut and paste it into your JavaScript file.*)
- Use `document.querySelector` to select the element in your HTML file with an id of `"movie-schedule"`
- Use the `.innerHTML` property to set the contents of the `"movie-schedule"` container equal to the HTML string you just created.



#### Challenge: Student Grades
Take the following array from the student grades exercise above. Each entry in the array represents a different student's percentage grade for the entire course:
```js
var grades = [92, 91, 75, 66, 52, 90, 83, 85, 64, 90, 72, 88, 77, 98, 100, 73, 92]
```
Use JavaScript to answer the following questions:
  1. How many students got A's?
  1. How many students got B's?
  1. Which was the most common letter grade?
  1. What was the average percentage grade in the class?
  
 
 #### Challenge: Movie Schedule Take Three
 - Revisit your movie schedule exercise from above.
 - Add a conditional so that you only print movies where the `currentlyPlaying` property is equal to `true`. 
 - Use flexbox to arrange your movie schedule side by side on your web page.
 - If a movie does not have a `poster` property, give it a [placeholder image like this](https://www.snhrc.com/wp-content/uploads/2018/09/Image-Coming-Soon.png)
 - Give all G-rated movies a dotted green border that's 2px wide.
 - Give all PG-rated movies a dotted yellow border that's 2px wide.
 - Give all PG-13 movies a dotted orange border that's 2px wide.
 - Give all R-rated movies a dotted red border that's 2px wide.

  




