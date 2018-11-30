# Loops

In the previous chapter, we dealt with a few situations where we wanted to do something to every item in an array (log it to the console, print it to the DOM, etc). We purposefully kept our arrays short, but we won't always have that luxury. Let's revisit the first practice exercise from the last chapter:

```
1. In your JavaScript file, instantiate and assign a variable called `movieArray`. This variable should hold an array of your favorite movie titles. (Don't go overboard- two or three is fine).

1. Log each movie in the array to the console.
```

What if, instead of making your own array of favorite movies, you were given an array with 50 movies in it and told to log each one the console. You'd probably want to throw your computer out the window after a few seconds of this:
```js
console.log(movieArray[0])
console.log(movieArray[1])
console.log(movieArray[2])
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

Let's look at a more practical example. Remember our `moviesArray`?
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
