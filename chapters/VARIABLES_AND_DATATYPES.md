# JavaScript Variables and Data Types

JavaScript is the programming language of the web. This is how we'll make our web pages *do* things:
- Respond to clicks
- Log in users
- Show us our saved information
- Keep track of our friend's information
- And pretty much everything else you can think of that happens on the web

But before we can do any of that cool stuff, we need to learn the basic building blocks of JavaScript. 

First, create two new files: an HTML document and a JavaScript file.
```
touch index.html script.js
```

In `index.html`, add the following code right before the closing body tag:
```html
<body>
  <!-- All your HTML goes here -->
  <script src='script.js'></script>
</body>

```

To make sure it works, add the following code to `script.js`:
```js
alert("Hello, world")
```

Open `index.html` in your web browser. If your script tag is linked correctly, you should see an alert box pop up immediately with the text you entered.

## Variales
A variable is a little box to store information that you want to reference or modify later. Let's start by declaring a simple variable to hold a name:

```js
var myName = "Dwayne The Rock Johnson";
```

We can also instantiate the variable first and then assign it later. (This is like setting up an empty box and then putting something in it later.)
```js
var myName;

myName = "Dwayne The Rock Johnson";
```
Variable values can change. For example, lets' say we want to change our name to just "The Rock" for the sake of brevity.

```js
// We declare the variable just like we did before
var myName = "Dwayne The Rock Johnson";

// Except this time we reassign it to hold a different value. Notice we don't have to use the var keyword for reassignments.
myName = "The Rock";

// This should log "The Rock" to the console
console.log("myName");
```


## Data Types
So far, all of our variables have been strings(i.e. they've had quotes around them). JavaScript doesn't care what data type our variables are when we assign them, but data types behave differently once you start trying to manipulate them. 
## Primitive Data Types
#### Numbers
Unlike strings, numbers do not have quotes around them. JavaScript treats both integers (whole numbers) and floats (decimal numbers) the same.
```
var age = 46;
```
You can perform basic math with JavaScript just like you would on a calculator.

```js
var totalCost;
var totalWithTax;

var costPerItem = 2.50;
var numberOfItems = 4;
var taxRate = 0.06;
 
totalCost = costPerItem * numberOfItems;
totalWithTax = totalCost + (taxRate * totalCost);

console.log(totalWithTax);
```

#### Booleans
Booleans are true/ false values. They do not have quotes around them.

```js
var likesDogs = true;

var allergicToDogs = false;
```
#### Strings 
Strings are anything that has a quotes around it. For now, the main thing we'll do with strings combine them with other values. This is called concatenation (when you combine a string with another string) or interpolation (when you combine a string with a variable or expression). Don't worry too much about the vocab for right now.

```js
var firstName = "Dwayne";
var lastName = "Johnson";

// There are a couple different ways to combine strings. These two examples produce the same result:

// Option A: String Concatenation with the + symbol
var fullName = firstName + " " + lastName;

// Option B: String template literals
fullName = `${firstName} ${lastName}`;
```

Anything becomes a string when you put quotes around it. This can cause some funky behavior if you're not careful.

```js
var x = "2";
var y = "4";
var total = x + y;
// In this case, the value of total woudl be 24, not 6.

```

## Arrays
Arrays are collections of data stored in order. You can put anything you want inside an array. 
```js
var grabBagArray = [1, "Hello, world", true]
```

We'll access items in an array by their index, or their place in line. Arrays are zero-indexed, which means we start counting at 0 instead of 1.

```js
var gradesArray = [97, 55, 62, 82, 79, 91, 74, 86];
var firstItem = gradesArray[0] // 97
var secondItem = gradesArray[1] // 55
var thirdItem = gradesArray[2] // 62
```
You can find out how many items are in an array with the `.length` property. (We won't use this very much right now, but it'll come in very handy later when we cover loops.)
```js
console.log(gradesArray.length); // 8
```
We can add items to an array with the `.push()` method.

```js
// Add a grade to the array
gradesArray.push(92);

// You can also add a grade (or replace one that's already in there) by accessing its index
gradesArray[9] = 83;
```
We can add, remove, or replace items with the `.splice()` method. This one's a bit more complicated, but it's very powerful.
```js
var months = ['Jan', 'March', 'April', 'June'];

// Inserts 'Feb' at an index of 1 and removes 0 elements 
months.splice(1, 0, 'Feb');

// Inserts 'May' at an index of 4 and removes one item (i.e. replaces 'June')
months.splice(4, 1, 'May');
```
## Objects
Arrays are great if we want to store data in order, but they have one big limitation: they can *only* keep track of our data by index. What if we want to label and organize our data in more detail? For example, let's say we want to store information about the students in a class instead of just their grades. Objects to the rescue!

```js
var leahObject = {
  firstName: "Leah",
  lastName: "Gwin",
  age: 27
}

console.log(leahObject.firstName); // "Leah"
console.log(leahObject.age); // 27
```
Just like arrays, objects can hold any other data type- including arrays and objects. 

```js
var robertObject = {
  firstName: "Robert",
  lastName: "Leedy",
  age: 32,
  hobbies: ["cooking", "rock climbing"]
}

var williamObject = {
  firstName: "William",
  lastName: "Kimball",
  age: 21
  hobbies: ["calligraphy", "travel", "banjo"]
}

console.log(williamObject.hobbies[0]) // "calligraphy"

// We can also have arrays of objects! Aaah!
var studentsArray = [leahObject, robertObject, williamObject];
console.log(studentsArray[0].firstName); // "Leah"
```

# Practice
These commands are a helpful quick start. You may choose to ignore them completely and create your own directory structure. If you choose to use this recommendation, just copy the commands below. It doesn't matter what directory you are currently in.
```
mkdir -p ~/workspace/on-boarding/exercises/javascript/variables_and_datatypes && cd $_
touch index.html script.js
```
Be sure to add boilerplate HTML to your `index.html` file and link it to `script.js`.

#### 1. All About Me
1. In your JavaScript file, instantiate and assign the following variables with information about yourself:
  - `firstName` should hold a string of your first name
  - `lastName` should hold a string of your last name
  - `age` should hold a number of your age
  - `likesTravle` should hold a boolean representing whether or not you like to travel 
  - Log each variable to the console.

#### 2. Favorite Movies
1. In your JavaScript file, instantiate and assign a variable called `movieArray`. This variable should hold an array of your favorite movie titles. (Don't go overboard- two or three is fine).
1. Log each movie in the array to the console.

#### 3. Movie Star
In your JavaScript file, use the following code as an example to create an object that represents a famous movie star.
```js
var dwayneObject = {
  firstName: "Dwayne",
  lastName: "Johnson",
  favoriteFood: "Raw meat",
  age: 46
}
```
1. Log the movie star's favorite food to the console.
1. Use string template literals to log their full name to the console.


**Challenge**
Refactor your movie star object to add their hobbies. Now your object should look something like this: 
```js
var dwayneObject = {
  firstName: "Dwayne",
  lastName: "Johnson",
  favoriteFood: "Eggs",
  hobbies: ["jumping out of planes", "personally holding the  San Andreas fault together", "building muscle mass"]
}
```
1. Log each one of their hobbies individually to the console.
1. Use string template literals to create a sentence about their hobbies. You should include how many hobbies they have in your sentence. (Hint: use the `.length` property.) Example output: "They have three main hobbies: jumping out of planes, personally holding the San Andreas fault together, and building muscle mass.") Store your new setnence in a variable called `hobbiesSentence` then log it to the console.





