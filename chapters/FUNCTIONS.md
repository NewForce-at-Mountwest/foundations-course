# JavaScript Functions
In the last chapter, we learned about loops as a way to do repetitive tasks quickly. If you need to log something 100 times, it's way easier to write (and to read) to use a loop rather than writing out the same piece of code 100 times. 

One of the main principles of software development is that code should be as DRY as possible. DRY stands for "Don't repeat yourself". 

Functions are another way to DRY up your code. Functions are reusable chunks of code. If you think you might need to write a piece of code more than once, you should probably put it in a function. 

Here's a simple function declaration:
```js
function sayHelloWorld(){
  console.log("Hello, world!");
}
```
If you paste the code above in your JavaScript file right now and run it, nothing will happen. To run the code inside a function, you have to call the function.
```js
sayHelloWorld(); 
// Expected output: "Hello, world!"
```

***
## Lightning Exercise
### I Love JavaScript
- Write a function that logs the string `"I love JavaScript!"` to the console.
- Call the function. 
***

## Parameters
Functions can act like little factories. They can take in information, modify it, and spit it back out. 

```js
// friendName is our parameter. It's a placeholder that we can use inside the function
function greetAFriend(friendName){
  console.log(`Hello, ${friendName}!`)
}

// When we call the function, we give it the actual name that we want to print.
greetAFriend("Dwayne");
```

Functions can take more than one parameter.

```js


function greetAFriend(friendName, timeOfDay){
  var greeting;
  if(timeOfDay === "morning"){
    greeting = "Good morning";
  } else if (timeOfDay === "afternoon"){
    greeting = "Good afternoon";
  } else if (timeOfDay === "evening"){
    greeting = "Good evening";
  } else {
    greeting = "Hello";
  }
  var personalGgreeting = `${greeting}, ${friendName}!`;
  console.log(personalGreeting);
}

greetAFriend("Todd", "evening"); // Good evening, Todd!
greetAFriend("Jamie", "morning"); // Good morning, Jamie!
greetAFriend("Hannah", "afternoon"); // Good afternoon, Hannah!
greetAFriend("Norman", "midnight"); // Hello, Norman!
```

***
## Lightning Exercise
### Dream Vacation
1. Write a function that accepts two parameters of `name` and `destination`. 
2. The function should log a sentence to the console about where that person wants to go.
3. Call the function three different times with different parameters.
*Example: if you pass in `"Jessica"` and `"Mount Fuji"` as parameters, you should see the sentence `"Jessica would love to visit Mount Fuji."` logged to the console.*
***

## Return Statements
Functions have their own scope, which means variales we declare inside the function can't be accessed outside of it. **The following code won't work!!!!** 
```js
function makeAPizza(crustType, size, toppingsArray){
  var finishedPizza = `A ${size} pizza with ${crustType} crust and ${toppingsArray.join(", ")} on top.`
}

makeAPizza("wheat", "large", ["green peppers", "onions", "pepperoni"]);

console.log(finishedPizza) // THIS LIL BOOGER WILL BE UNDEFINED! Right now, the finishedPizza variable ONLY exists inside the function.

```

If we want to use the `finishedPizza` variable anywhere outside the function, we need a `return` statement.

```js
function makeAPizza(crustType, size, toppingsArray){
  var finishedPizza = `A ${size} pizza with ${crustType} crust and ${toppingsArray.join(", ")} on top.`
  return finishedPizza;
}

var myPizza = makeAPizza("wheat", "large", ["green peppers", "onions", "pepperoni"]);

var yourPizza = makeAPizza("white", "medium", ["anchovies", "feta", "pineapple"]);

console.log(myPizza); 
// Expected output: "A large pizza with wheat crust and green peppers, onions, pepperoni on top."

console.log(yourPizza);
// Expected output: "A medium pizza with white crust and green anchovies, feta, pineapple on top."

```

***
## Lightning Exercise
### Taco Truck
1. Write a function to represent a taco truck's ordering system. The function should accept two parameters: `typeOfShell` and `topping`. (Both will be strings.)
1. Inside the function, use string interpolation to build a sentence that announces the taco is ready. Use the information the customer passed in. For example: `"Your soft shell taco with chicken is ready!"`
1. Return the taco sentence.
1. Execute the function.
1. Log  the returned sentence to the console. 
***
## Practice

These commands are a helpful quick start. You may choose to ignore them completely and create your own directory structure. If you choose to use this recommendation, just copy the commands below. It doesn't matter what directory you are currently in.
```
mkdir -p ~/workspace/on-boarding/exercises/javascript/functions && cd $_
touch index.html script.js
```
Be sure to add boilerplate HTML to your `index.html` file and link it to `script.js`.
### 1. Calculator
1. Write a function called `add`. It should accept two numbers as parameters and log their sum to the console.
1. Write a function called `subtract`. It should accept two numbers as parameters and log the difference between the first and second number to the console.
1. Write a function called `multiply`. It should accept two numbers as parameters and log their product to the console.
1. Write a function called `divide.` It should accept two numbers as parameters, divide the first number by the second number, and log the result to the console.
1. Call each function three times with different parameters.

### 2. Calculator Refactor
1. Refactor your previous exercise so that each calculator function _returns_ the result of its calculations. You should not have any `console.log`s inside your functions. 
1. When you execute your calculator functions, store each result in a new variable and log the variable to the console. The `console.log`s should now be outside the scope of your functions. 

### 3. Greetings Pt. 2

1. Revisit the greetings exercise you did in the conditionals chapter, where you logged a greeting to the console based on the person's preferred language. 
1. Write a function that accepts two parameters: `name` and `language`. 
    - If the person's preferred language is English, the function should print "Hello, [name]!" to the console.
    - If the person's preferred language is Spanish print "Hola, [name]!" to the console.
    - If their preferred language is French, print "Bonjour, [name]!" to the console.

### 4. Sandwich Maker
1. Write a function that accepts three parameters: `breadType` (a string), `sandwichName`, and `isToasted` (a boolean). 
1. The function should check whether `isToasted` is true or false and build a sentence about the sandwich order accordingly. 
1. The function should return the sentence.
1. Call the function three times, passing in three different sets of parameters.

Example output:
```
"You ordered a toasted meatball sub sandwich on wheat."
```

### 5. The Rock's Hobbies
1. Copy and paste the following object into your JavaScript file:
```js
var dwayneObject = {
  firstName: "Dwayne",
  nickName: "The Rock",
  lastName: "Johnson",
  favoriteFood: "Eggs",
  hobbies: ["jumping out of planes", "personally holding the  San Andreas fault together", "building muscle mass"]
}

function printHobbies(){
// YOUR CODE GOES HERE
}
```
2. The `printHobbies` function should loop through the array of Dwayne The Rock Johnson's hobbies and print each one to the console.
3. Call the `printHobbies` function.

### 6. New Years Eve Party
Copy and paste the following array into your JavaScript file:
```js
var partyGuests = [
  {
    name: "Sam",
    age: 18
  },
  {
    name: "Jerry",
    age: 45
  },
  {
    name: "Lila",
    age: 29
  },
  {
    name: "Mary",
    age: 68
  },
  {
    name: "Todd",
    age: 10
  }
]

function ageChecker(){

  // YOUR CODE GOES HERE
}
```

1. Fill in the `ageChecker` function so that it does the following things:
    - Loop through the `partyGuests` and check if each guest is at least 21.
    - Build a sentence or two about who can drink and who can't. (Example: `"
"Jery, Lila, and Mary can drink. Sam and Todd are too young."`)
    - Log the sentnece to the console.


### 7. Celsius to Fahrenheit
You'll be writing two functions: one that converts Celsius to Fahrenheit and the other, vice versa.
- Write a function that takes the temperature in Celsius as the parameter
- The function should do the following calculation to get the temperature in Fahrenheit: T(F) = T(C) * 1.8 + 32
- Output the temperature in Fahrenheit to the console
- Write a second function that takes the temperature in Fahrenheit as the parameter
- The function should do the following calculation to get the temperature in Celsius: T(C) = (T(F) - 32) / 1.8
- Output the temperature in Celsius to the console
Example output:
```
"You entered [degrees in Celsius] Celsius. That converts to [degrees in Fahrenheit] Fahrenheit." "You entered [degrees in Fahrenheit] Fahrenheit. That converts to [degrees in Celsius] Celsius."
```

### 8. It All Adds Up!
Copy and paste the following code into your JavaScript file:
```js
var outsideArray =  [4, 7, 8008, 11, 9, -1];
```

- In your JavaScript file, create (declare) a function named `addThemUp`.
- The function should accept one argument: an array of numbers.
- Inside the function, loop over the array of numbers parameter and add them up to a running sum.
- The `addThemUp` function should return the sum.
- Call `addThemUp` and pass in `outsideArray` as an argument.
- Save the returned value in a variable called `mySum`.
- Log `mySum` to the console.
- Try changing the numbers in the array or adding new numbers. 

### 9. Law of Averages
Copy and paste the following code into your JavaScript file:
```js
var scoresToAverage =  [22, 34, 62, 11, 90, 88, 70, 65, 22, 89, 85, 39, 71, 92, 98, 84];
```

- In your JavaScript file, create (declare) a function named `findAverage`.
- The function should accept one argument: an array of numbers.
- Inside the function, loop over the array of numbers parameter and find their average.
- The `findAverage` function should return the average of all the numbers.
- Call `findAverage` and pass in `scoresToAverage` as an argument.
- Save the returned value in a variable called `myAverage`.
- Log `myAverage` to the console.
- Try adding new numbers to the `outsideArray`. Your function should still return the correct average no matter how many items are in the array.


### 10. Shipping Calculator 
1. You work for an online clothing retailer. Every time an order ships, your company needs to calculate the cost of shipping so they can charge the customer correctly. Because they need to make this calculation so many times and in so many places, they've asked you to write a function that calculates shipping cost based on package weight, distance to destination, and whether or not the package is oversized. 
    - The cost of shipping is always the weight of the package multiplied by the distance it needs to travel, divided by 100.
    - If the package is oversized, it adds ten dollars to the cost of shipping.
2. Write a function that accepts whatever information you need to calculate the cost of shipping and returns the cost as an integer. 
3. Execute the function and output the result to the console.
