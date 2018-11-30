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
Functions have their own scope, which means variales we declare inside the function can't be accessed outside of it. 
```js
function makeAPizza(crustType, size, toppingsArray){
  var finishedPizza = `A ${size} pizza with ${crustType} crust and ${toppingsArray.join(", ")} on top.`
}

makeAPizza("wheat", "large", ["green peppers", "onions", "pepperoni"]);

// if we try to access finishedPizza out here, it will be undefined-- it only exists inside the function
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


