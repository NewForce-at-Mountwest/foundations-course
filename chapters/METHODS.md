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
We've given our `hoagieObject` some data, but what if we want Hoagie to be able to *do* things? We give objects behaviors with methods. Methods are just functions stored inside of objects.

```js
var hoagieObject = {
  name: "Hoagie",
  color: "Gray",
  type: "Dog",
  favoriteThings: ["human laps", "floofy blankets", "dog parks"],
  bark: function(){
    console.log("woof!");
  },
  eat: function(food){
    console.log(`${this.name} eats ${food}.`);
  }
}

hoagieObject.bark(); // "woof!"
hoagieObject.eat("dog food"); // "Hoagie eats dog food." 
```

Let's look at another example:
```js

// Let's declare an object to represent our friend Emily
var emilyObject = {
  firstName: "Emily",
  lastName: "Lemmon",
  fullName: function(){
    return `${this.firstName} ${this.lastName}`;
  },
  greetSomeone: function(personsName){
    console.log(`Hi, ${personsName}, I'm ${this.fullName()}.`);
  }
}

// And another one to represent our other friend Jisie
var jisieObject = {
  firstName: "Jisie",
  lastName: "David",
  fullName: function(){
    return `${this.firstName} ${this.lastName}`;
  },
  greetSomeone: function(personsName){
    console.log(`Hi, ${personsName}, I'm ${this.fullName()}.`);
  }
}

// Now we can have them say hi to each other!

emilyObject.greetSomeone(jisieObject.firstName);
// Expected output: "Hi, Jisie, I'm Emily Lemmon.

jisieObject.greetSomeone(emilyObject.firstName);
// Expected output: "Hi, Emily, I'm Jisie David.

```

# Practice
#### Pet Store
Using the above example, create three new objects to represent different pets in a pet store. Each pet should have:
- A name
- A type (bird, lizard, cat, etc)
- An array that contains their favorite things
- A method to make a sound
- A method called `eat` that accepts one paramter called `foodName` and returns a string that looks something like the one in the dog example from up top.

#### Address Book
1. Create an object that represents your contact information. Use the code below as an example:
```js
var jordanContactInfo = {
  cell: "(999) 999-9999",
  email: "jordan.castelloe@gmail.com",
  address: "123 Sesame St"
}
```
1. Go ahead and create two more objects that represent two of your friends' contact information.
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

#### Calculator
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
- Add methods to the `calculator` object for subtraction, division, and multiplication.
- Call each method twice with different parameters.

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
  calculateTotal: function(){
    // YOUR CODE GOES HERE
    // Write a method that loops through the items array and adds up the totalPrice of each item. This method should return a total.
  }
}
```

Fill in the `calcualteTotal` method to add up a grand total for all the items in the shopping cart and return it. (Hint: you can access the `items` array from inside the object with `this.items`.)