# Methods in Objects

Back when we were first learning about JavaScript, we learned that objects are a great way to store information about people and things. Here's an object representing a dog:

```js
var hoagieObject = {
  name: "Hoagie",
  color: "Gray",
  type: "Dog",
  favoriteThings: ["human laps", "floofy blankets", "dog parks"]
}
```
If we wanted to print Hoagie's color to the console, we would use dot notation:
```js
console.log(hoagieObject.color)
```
We've given our `hoagieObject` some data, but what if we want Hoagie to be able to *do* things? We give objects behaviors with methods. Methods are just functions stored inside of objects.

```js
var hoagieObject = {
  name: "Hoagie",
  color: "Gray",
  type: "Dog",
  favoriteThings: ["human laps", "floofy blankets", "dog parks"],
  bark: function(){
    console.log("woof!");
  }
}

hoagieObject.bark(); // "woof!"
```

Let's look at another example:
```js

// Let's declare an object to represent our friend Emily
var emilyObject = {
  firstName: "Emily",
  lastName: "Lemmon",
  greetSomeone: function(personsName){
    console.log(`Hi, ${personsName}, I'm ${this.firstName} ${this.lastName}.`);
  }
}

// And another one to represent our other friend Jisie
var jisieObject = {
  firstName: "Jisie",
  lastName: "David",
  greetSomeone: function(personsName){
    console.log(`Hi, ${personsName}, I'm ${this.firstName} ${this.lastName}.`);
  }
}


// Now we can have them say hi to each other!

emilyObject.greetSomeone(jisieObject.firstName);
// Expected output: "Hi, Jisie, I'm Emily Lemmon.

jisieObject.greetSomeone(emilyObject.firstName);
// Expected output: "Hi, Emily, I'm Jisie David.

```

# Practice

These commands are a helpful quick start. You may choose to ignore them completely and create your own directory structure. If you choose to use this recommendation, just copy the commands below. It doesn't matter what directory you are currently in.
```
mkdir -p ~/workspace/on-boarding/exercises/javascript/methods && cd $_
touch index.html script.js
```
Be sure to add boilerplate HTML to your `index.html` file and link it to `script.js`.

#### 1. Pet Store
Create three new objects. Each object should represent a pet at a pet store. Each object should have:
- A name ("Dennis", "Stacy", "Flapjack", etc)
- A species (bird, lizard, cat, etc)
- An array that contains the pet's favorite things
- A method called `vocalize` that logs to the console whatever sound you think that animal would make.
- Call the `vocalize` method for each animal.

#### 2. Address Book
1. Create an object that represents your contact information. Use the code below as an example:
```js
var jordanContactInfo = {
  cell: "(999) 999-9999",
  email: "jordan.castelloe@gmail.com",
  address: "123 Sesame St"
}
```
2. Create two more objects that represent two of your friends' contact information.
1. Now give each of your three objects a method called `callCellPhone`. It should accept a parameter of `phoneNumber`. For example, my object would now look like this: 
```js
var jordanContactInfo = {
  cell: "(999) 999-9999",
  email: "jordan.castelloe@gmail.com",
  address: "123 Sesame St",
  callCellPhone: function(phoneNumber){
    console.log(`Now calling ${phoneNumber}`);
  }
}
```
1. Give each object a couple more methods: 
  - A method called `sendEmail` (which should accept a parameter of `emailAddress`)
  - A method called `sendMail` (which should accept a parameter called `mailingAddress`)
  - Don't worry to much about what the methods do- just logging something to the console is fine.
2. Now invoke some of the methods. Have one friend "call" another friend's cell phone number, etc.

#### 3. Calculator
Copy and paste the following code into your JavaScript file:
```js
var calculator = {
  add: function(x, y) {
    return x + y;
  }
}

var sum = calculator.add(2, 2);
console.log(sum); // Expected output: 4
```
- Add three more methods to the `calculator` object for subtraction, division, and multiplication.
- Call each method at least twice, passing in different parameters.

#### 4. Movie Poster
Copy and paste the following object into your JavaScript file:
```js
var movieObject = {
  title: "Star Wars: A New Hope",
  genre: "Science Fiction",
  releaseDate: "May 25, 1977"
  printMoviePoster: function(){
    // YOUR CODE GOES HERE
  }
}
```
Copy and paste the following code into your `index.html` file:
```html
<section id="movie-poster"></section>
```
1. Fill in the `printMoviePoster` method to do the following things:
    - Create an HTML string that represents the movie's title, genere, and release date in HTML elements. (You can use any elements you want.)
    - Use `document.querySelector` and `.innerHTML` to print your HTML string to the `"#movie-poster"` element in the DOM.
    
#### 5. Movie Schedule



#### Challenge: Shopping Cart

Copy and paste the following code into your JavaScript file: 
```js
var shoppingCart = {
  items: [
    {
      name: "Bananas",
      totalPrice: 2.75
    },
    {
      name: "English Muffins",
      totalPrice: 3.99
    },
    {
      name: "Peanut Butter",
      totalPrice: 2.99
    }
  ],
  addToCart: function(objectToAdd){
    // YOUR CODE GOES HERE
  },
  calculateTotal: function(){
    // YOUR CODE GOES HERE
  },
  printShoppingCart: function(){
    // YOUR CODE GOES HERE
  }
}
```

Copy and paste the following code into your `index.html` file:
```html
<div id="shopping-cart"></div>
```
Your job is to fill in the three empty methods in the `shoppingCart` object. *(Hint: you can access the `items` array from inside the object with `this.items`.)*
1. The `addToCard` method should take in a parameter of an object that represents a new item and add it to the shopping cart array. *Hint: look up [.push()](https://www.w3schools.com/jsref/jsref_push.asp)*
1. The `calcualteTotal` method to loop over all the items in your shopping cart, add up a total, and return it.
1. The `printShoppingCart` method should loop over all the items in the cart, build up an HTML string, and print them to the `"#shopping-cart"` element in the DOM. 
1. Call each method.

