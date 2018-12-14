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
1. Write a function that accepts three parameters: `breadType` (a string), `sandwichName`, and `isToasted` (a boolean). 
1. The function should check whether `isToasted` is true or false and build a sentence about the sandwich order accordingly. 
1. Log the sentence to the console.
1. Call the function three times, passing in three different sets of parameters.

Example output:
```
"You ordered a toasted meatball sub sandwich on wheat."
```

#### 4. The Rock's Hobbies
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

#### 5. Sandwich Toppings
1. Copy and paste the following array into your JavaScript file:
```js
var sandwichToppings = ["pickles", "extra cheese", "lettuce", "tomatoes", "avocado", "bacon", "mayo", "mustard"]
```
2. Copy and paste the following code into your `index.html` file:
```html
<ul id="sandwich-container"></ul>
```
3. Write a function that does the following things:
    - Loop through `sandwichToppings`
    - Build up an  HTML string with an `<li>` element for each item in the array.
    - Use `document.querySelector` and `.innerHTML` to print your HTML string to the `"#sandwich-container"`.
4. Call the function. You should see a bulleted list of all the sandwich toppings in the DOM.

#### 6. New Years Eve Party
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

Copy and paste the following HTML into your `index.html` file:
```html
<div id="party-guests"></div>
```
1. Fill in the `ageChecker` function so that it does the following things:
    - Loop through the `partyGuests` and check if each guest is at least 21.
    - Build a sentence or two about who can drink and who can't. (Example: `"
"Jery, Lila, and Mary can drink. Sam and Todd are too young."`)
    - Use `document.querySelector` and `.innerHTML` to print the sentence(s) to the `"#party-guests"` container in the DOM.
2. Call the function.


#### 7. Celsius to Fahrenheit
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

#### 8. It All Adds Up!
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

#### 9. Law of Averages
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

#### Challenge: Cohort Website
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
 endDate: "Feb 12, 2020",
 instructors: ["Kim", "Josh", "Jordan"],
 techStack: ["HTML", "CSS", "JavaScript", "React", "C#", ".NET"]
}

var cohort3 = {
 name: "Cohort Three",
 startDate: "September 15, 2020",
 endDate: "March 12, 2021",
 instructors: ["Kim", "Josh", "Jordan"],
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


 


