# JavaScript Conditionals
Conditionals decide whether or not pieces of code should run.
```js
if(2+2 === 4){
  console.log("Math works!");
} else {
  console.log("Math is broken.")
}

// Expected output: "Math works!"
```

In the example above, the first thing JavaScript does is evaluate the code inside the parentheses to see if it's `true` or `false`. In this case, it checks to see if `2+2` equals `4`. It does! That statement evaluates to `true`, so the code inside the `if` block runs. If that statement had evaluated to `false`, the code inside the `else` block would have run instead.

### Comparison Operators
Did you notice the weird looking triple equals sign up there?  That wasn't a typo; that's how we compare two values in JavaScript to see if they're equal. Comparison operators always evaluate to `true` or `false`. 

```js
// Triple equals will check to see if the type and the value are equal
"Hello" === "Hello"; //true
24 === "24"; // false

// Double equals will compare values as if they're the same type, even if they're not. This can get messy, so you should default to triple equals 
24 == "24" // true


3 > 23 // false, 3 is not greater than 23
22 < 100 // true, 22 is less than 100
24 <= 25 // true, 24 is less than or equal to 25
62 >= 4 // true, 62 is greater than or equal to 4
```
We can also check to see if things are NOT equal.
```js
var name = "Jordan";
if(name !== "Dwayne"){
  console.log("Too bad for you!");
}
// Expected output: "Too bad for you!"
```

### Logical Operators
We can also check to see if more than one condition is true.

```js
var fullMoon = true;
var isWolf = false;

// This block of code will only run if the moon is full AND you're a wolf. Right now, this code won't run because the value of isWolf is false.
if(fullMoon && isWolf){
  console.log("AWOOOOOOOOOOO");
}

// What if we want non-wolves to be able to howl at the full moon too? This block will run if you're a wolf OR if the moon is full. However, if both conditions are false (you're not a wolf and the moon is not full), the code will not run.
if(fullMoon || isWolf){
  console.log("AWOOOOOOOOOOO");
}

```

# Practice