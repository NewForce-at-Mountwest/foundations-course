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
var greeting;

function greetAFriend(friendName, timeOfDay){
  if(timeOfDay === "morning"){
    greeting = "Good morning";
  } else if (timeOfDay === "afternoon"){
    greeting = "Good afternoon";
  } else if (timeOfDay === "evening"){
    greeting = "Good evening";
  } else {
    greeting = "Hello";
  }
  greeting = `${greeting}, ${friendName}!`;
  console.log(greeting);
}

greetAFriend("Todd", "evening"); // Good evening, Todd!
greetAFriend("Jamie", "morning"); // Good morning, Jamie!
greetAFriend("Hannah", "afternoon"); // Good afternoon, Hannah!
greetAFriend("Norman", "midnight"); // Hello, Norman!
```
## Return Statements
Functions have their own scope, which means variales we declare inside the function can't be accessed outside of it. **The following code won't work:** 
```js
function makeAPizza(crustType, size, toppingsArray){
  var finishedPizza = `A ${size} pizza with ${crustType} crust and ${toppingsArray.join(", ")} on top.`
}

makeAPizza("wheat", "large", ["green peppers", "onions", "pepperoni"]);

console.log(finishedPizza) // this will be undefined!

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
# Practice

These commands are a helpful quick start. You may choose to ignore them completely and create your own directory structure. If you choose to use this recommendation, just copy the commands below. It doesn't matter what directory you are currently in.
```
mkdir -p ~/workspace/on-boarding/exercises/javascript/functions && cd $_
touch index.html script.js
```
Be sure to add boilerplate HTML to your `index.html` file and link it to `script.js`.
#### 1. I Love JavaScript
- Write a function that logs the string `"I love JavaScript!"` to the console.
- Call the function. 

#### 2. Dream Vacation
1. Write a function that accepts two parameters of `name` and `destination`. 
2. The function should log a sentence to the console about where that person wants to go.
3. Call the function three different times with different parameters.
*Example: if you pass in `"Jessica"` and `"Mount Fuji"` as parameters, you should see the sentence `"Jessica would love to visit Mount Fuji."` logged to the console.*
#### 3. Sandwich Maker
1. Write a function that accepts three parameters: `breadType` (a string), `sandwichName`, and `toasted` (a boolean). 
1. The function should check whether `toasted` is true or false and build a sentence about the sandwich order accordingly. 
1. Return the sandwich sentence. 
1. Call the function three times, passing in three different sets of parameters.
1. Log each sandwich to the console. (Since you're returning it, your `console.log` should be outside the sandiwch maker function.) 

Example output:
```
"You ordered a toasted meatball sub sandwich on wheat."
```
#### 4. Sandwich Toppings
1. Copy and paste the following array into your JavaScript file:
```js
var sandwichToppings = ["pickles", "extra cheese", "lettuce", "tomatoes", "avocado", "bacon", "mayo", "mustard"]
```
1. Write a function that loops through the `sandwichToppings` array and builds a sentence about all the toppings the sandwich shops offers.

Expected output:
```
"Our topping choices are pickles, extra cheese, lettuce, tomatoes, avocado, bacon, mayo, and mustard."
```
#### 5. New Years Eve Party
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
1. The `ageChecker` function should loop through the `partyGuests` and determine if each guest is of legal drinking age.
1. When called, the `ageChecker` function should return a sentence that tells us which guests are of drinking age and which ones are too young to drink. 
1. Log the returned sentence to the console.

#### 6. The Rock's Hobbies
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

#### 7. Challenge: Cohort Website
1. Copy and paste the following code inside the `body` tags of your HTML file:
```html
<div id = "cohort-container">
</div>
```
2. Copy and paste the following code in your JavaScript file:
```js
var cohort1 = {
  name: "Cohort One",
  startDate: "January 15, 2018",
  endDate: "July 12, 2018",
  instructors: ["Jordan", "Josh", "Kim"],
  techStack: ["HTML", "CSS", "JavaScript", "React", "C#", ".NET"]
}

function printCohort(cohortObject){
  // YOUR CODE GOES HERE
}

```
3. The `printCohort` function should take in the `cohort1` object as a parameter and return a HTML string with the following elements:
    - An `h1` of the cohort's name
    - An `h3` for the start date
    - An `h3` for the end date
    - An unordered list of instructors
    - An unordered list of technologies learned
4. Call the `printCohort` function.
5. Use the `document.querySelector` method to grab a reference to the `div` with the id of `"cohort-container"` in the DOM
6. Use the `innerHTML` property to insert your returned HTML string into the DOM

 


