# JavaScript Variables and Data Types

[ WHAT IS JS??]
[HOW TO LINK A JS FILE INTO YOUR HTML]

## Variales
A variable is a little box to store information that you want to reference or modify later. Let's start by declaring a simple variable to hold a name:

```js
var myName = "Dwayne The Rock Johnson";
```

We can also declare the variable first and then assign it later. (This is like setting up an empty box and then putting something in it later.)
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
  age: 27,
  hobbies: ["travel", "cycling", "reading"],
  grades: [97, 85, 76, 92]
}

console.log(leahObject.firstName); // "Leah"
console.log(leahObject.age); // 27
console.log(leahObject.hobbies[0]) // "travel"
```
Just like arrays, objects can hold any other data type- including arrays and objects. 

```js
var robertObject = {
  firstName: "Robert",
  lastName: "Leedy",
  age: 32,
  hobbies: ["cooking", "rock climbing"],
  grades: [91, 85, 79, 82]
}

var williamObject = {
  firstName: "William",
  lastName: "Kimball",
  age: 21
  hobbies: ["calligraphy", "travel", "banjo"]
}

//Aaaah! An array of objects! Actually, this is a really common data structure and we'll see it a lot. 
var studentsArray = [leahObject, robertObject, williamObject];
console.log(studentsArray[0].firstName); // "Leah"
```

# Practice
1. 