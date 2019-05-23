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
***
## Lightning Exercise
#### Lightning McQueen
1. Create a new object representing a sports car
1. Give the object a property of make, model, and year, and the date of its last oil change to the console.
1. Give the object a method called `drive`. It should log a string to the console that says "vroom vroom"
1. Print the car's make, model, year, an d date of last oil change to the console.
1. Call the car's `drive` method.
***

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

***
## Lightning Exercise
#### Car Maintenance 
1. Create a new object representing a mechanic. The mechanic object should have properties representing their name and place of work. 
1. Give your mechanic object a property of `changeOil`. This method sould accept a parameter of a car object. It should reassign the date of the car's last oil change to [today](https://www.w3schools.com/js/js_dates.asp).
1. Call the mechanic's `changeOil` method on the car object you created in the last lightning exercise. Log the car's last oil change date before _and_ after you call the `changeOil` method. They should be different!

***

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


#### 2. Calculator
Copy and paste the following code into your JavaScript file:
```js
var calculator = {
  add: function(x, y) {
    // YOUR CODE GOES HERE
  }
}

var sum = calculator.add(2, 2);
console.log(sum); // Expected output: 4
```
- Add three more methods to the `calculator` object for subtraction, division, and multiplication. Each method should return the result of the calculation.
- Call each method at least twice, passing in different parameters. 


#### 4. Address Book
1. Create an object that represents your contact information. Use the code below as an example:
```js
var jordanContactInfo = {
  name: "Jordan Castelloe",
  cell: "(999) 999-9999",
  email: "jordan.123@gmail.com",
  address: "123 Sesame St"
}
```
2. Create another object that represents your one of your friend's contact information. Example: 
```js
var emilyContactInfo = {
  name: "Emily Lemmon",
  cell: "(888) 888-8888",
  email: "eclair@gmail.com",
  address: "124 Sesame St"
}
```
3. Now give each of your objects a method called `callCellPhone`. It should accept a parameter of `phoneNumber`. For example, my object would now look like this: 
```js
var jordanContactInfo = {
  name: "Jordan Castelloe",
  cell: "(999) 999-9999",
  email: "jordan.123@gmail.com",
  address: "123 Sesame St",
  callCellPhone: function(phoneNumberParameter){
    console.log(`${this.name} is now calling ${phoneNumberParameter}`);
  }
}
```
4. Give each object two more methods: 
  - A method called `sendEmail` (which should accept a parameter of `emailAddress`)
  - A method called `sendMail` (which should accept a parameter called `mailingAddress`)
  - Don't worry to much about what the methods do- just logging something to the console is fine.
5. Invoke your `callCellPhone` method and pass in your friend's phone number as a parameter. (In this example, my expected output would be `"Jordan Castelloe is now calling (888) 888-8888"`).
6. Invoke your friend's `sendEmail` method and pass in your email address as a parameter.
7. Invoke your `sendMail` method and pass in your friend's mailing address as a parameter.


## Challenges

#### Shopping Cart

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


Your job is to fill in the three empty methods in the `shoppingCart` object. *(Hint: you can access the `items` array from inside the object with `this.items`.)*
1. The `addToCard` method should take in a parameter of an object that represents a new item and add it to the shopping cart array. *Hint: look up [.push()](https://www.w3schools.com/jsref/jsref_push.asp)*
1. The `calcualteTotal` method should calculate and return a total for all the items in your shopping cart.
1. The `printShoppingCart` method should loop over all the items in the cart and print them to the console. It should also print the total price of all the items in your shopping cart.

#### Library System

Your job is to represent a library system with JavaScript objects and methods. 
In your JavaScript file, create the following objects:
1. A `library` object with the following properties and methods:
    - A `name` property
    - A `location property`
    - A `currentInventory` property that holds an array of book titles (strings)
1. A `patron` object with the following properties and methods:
    - A `firstName` property
    - A `lastName` property
    - A `checkedOutBooks` property that holds an array of book titles (strings)
    - A `overdueFees` property that holds a number
    - A `printBooks` method that builds an unordered list of all the patron's checked out books and prints it to the DOM.
1. A `librarian` object with these properties and methods:
    - A `firstName` property
    - A `lastName` property
    - A `checkOutBook` method that accepts three parameters: a string of a book title, a patron object, and a library object. If the book is currently in stock, this method should add the given book title to the patron's `checkedOutBooks` array and remove it from the library's `currentInventory` array. *(Hint: look up [.splice()](https://www.w3schools.com/jsref/jsref_splice.asp))*.
    - A `chargeFee` method that accepts two parameters: a number that represents the fee amount and a patron object. This method should add the fee object to the patron's `overdueFees` property.
    - A `checkInBook` method that accepts three parameters: a string of a book title, a patron object, and a library object. This method should remove the given book title from the patron's `checkedOutBooks` array and add it back to the library's `currentInventory` array. 
   - Patrons can check out a maximum of ten books. If they go over that maximum, the librarian should see an error message in the console.
   - Patrons should not be able to check in a book that they haven't checked out. If they try to do this, the librairan should see an error message in the console.
   - If a patron tries to check out a book that's out of stock, the librarian should see an error message.
   