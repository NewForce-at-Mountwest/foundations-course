# Arrays and Objects

## Arrays
Arrays are collections of data stored in order. You can put anything you want inside an array.
```js
let grabBagArray = [1, "Hello, world", true]
```

We'll access items in an array by their index, or their place in line. Arrays are zero-indexed, which means we start counting at 0 instead of 1.

```js
let gradesArray = [97, 55, 62, 82, 79, 91, 74, 86];
let firstItem = gradesArray[0] // 97
let secondItem = gradesArray[1] // 55
let thirdItem = gradesArray[2] // 62
```
You can find out how many items are in an array with the `.length` property. (We won't use this very much right now, but it'll come in very handy later when we cover loops.)
```js
console.log(gradesArray.length); // 8
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
let months = ['Jan', 'March', 'April', 'June'];

// Inserts 'Feb' at an index of 1 and removes 0 elements
months.splice(1, 0, 'Feb');

// Inserts 'May' at an index of 4 and removes one item (i.e. replaces 'June')
months.splice(4, 1, 'May');
```


***
## Lightning Exercise
### Favorite Movies
1. In your JavaScript file, instantiate and assign a variable called `movieArray`. This variable should hold an array of your favorite movie titles. (Don't go overboard- two or three is fine).
1. Log each movie in the array to the console.
***

## Objects
Arrays are great if we want to store data in order, but they have one big limitation: they can *only* keep track of our data by index. What if we want to label and organize our data in more detail? For example, let's say we want to store information about the students in a class instead of just their grades. Objects to the rescue!

Objects are constructed of key value pairs. The key, on the left, is the identifier. The value, on the right, is the data you want to store. You may also hear us refer to the _properties_ in an object. We'll use the terms key and property interchangebaly.

```js
// Here's a JavaScript object representing a student
// This particular object has three key value pairs, but objects can have as many key value pairs as you like
let leahObject = {
  firstName: "Leah", // On this line, the key is firstName and the value is "Leah"
  lastName: "Gwin",
  age: 27
}

console.log(leahObject.firstName); // We can access the value of "Leah" by referencing the key name
console.log(leahObject.age); // 27
```
Just like arrays, objects can hold any other data type- including arrays and objects.

```js
let robertObject = {
  firstName: "Robert",
  lastName: "Leedy",
  age: 32,
  hobbies: ["cooking", "rock climbing"]
}

let williamObject = {
  firstName: "William",
  lastName: "Kimball",
  age: 21
  hobbies: ["calligraphy", "travel", "banjo"]
}

console.log(williamObject.hobbies[0]) // "calligraphy"

// We can also have arrays of objects! Aaah!
let studentsArray = [leahObject, robertObject, williamObject];
console.log(studentsArray[0].firstName); // "Leah"
```
## New Vocab
These are some important new words we've learned so far. If you don't remember what any of these mean, re-read the chapter so far or ask an instructor.
1. Array
1. Index
1. Object
1. Key value pair

***
## Lightning Exercise
### All About Me Pt. 2
1. Instead of storing the data from your first lightning exercise in separate variables, store them in an object. Your object should have a property of  `firstName`, `lastName`, `age`, `likesToTravel`. It should also have a property called `favoriteMovies`, which should hold the array of  your favorite movies you created in the last lightning exercise.
***

## Practice
These commands are a helpful quick start. You may choose to ignore them completely and create your own directory structure. If you choose to use this recommendation, just copy the commands below. It doesn't matter what directory you are currently in.
```
mkdir -p ~/workspace/foundations/exercises/javascript/arrays_and_objects && cd $_
touch index.html script.js
```
Be sure to add boilerplate HTML to your `index.html` file and link it to `script.js`.


### 1. Weather Data
In your JavaScript file, copy and paste the following array:
```js
var highTemperatures = [55, 57, 53, 47, 56, 50];
var lowTemperatures = [33, 30, 29, 35, 31, 32];
```
1. Print the first high temperature to the console.
1. Print the last low temperature to the console.



### 2. Weather Object
1. In your JavaScript file, create an object that represents the current weather. Your can reuse your data from the first exercise. Your object should have the following properties:
    - `temperature`
    - `conditions`

1. Log the current temperature to the console.
1. Use string template literals to log a sentence about the weather console. (Example: "It's 64 degrees F and sunny.")

### 3. Nested Weather Objects
Refactor your weather object to include today's high and low temperature and sunrise/ sunset times. Now your object should look something like this:
```js
let todaysWeather = {
  temperature: {
    high: 55,
    low: 32
  },
  conditions: "sunny",
  astronomy: {
    sunrise: "7:43 AM",
    sunset: "5:09 PM"
  }
}
```
1. Log today's high temperature to the console.
1. Log today's low temperature to the console.
1. Log today's conditions to the console.
1. Log today's sunrise time to the console.
1. Use string template literals to create a more detailed description of today's weather.

### 4. Weather Forecast
Copy and paste the following array into your JavaScript file
```js
let weatherForecast = [
 {
  day: "Today",
  temperature: {
    high: 55,
    low: 32
  },
  conditions: "sunny",
  astronomy: {
    sunrise: "7:43 AM",
    sunset: "5:09 PM"
  }
 },
 {
  day: "Saturday",
  temperature: {
    high: 50,
    low: 29
   },
  conditions: "cloudy",
  astronomy: {
    sunrise: "7:44 AM",
    sunset: "5:08 PM"
  }
 },
 {
  day: "Sunday",
  temperature: {
    high: 47,
    low: 35
   },
  conditions: "chance of rain",
  astronomy: {
    sunrise: "7:45 AM",
    sunset: "5:07 PM"
  }
 }
]
```
1. Log today's weather conditions to the console.
1. Log Saturday's high temperature to the console.
1. Log Saturday's sunrise time to the console.
1. Log Sunday's conditions to the console.
1. Log Sunday's sunset time to the console.
1. Use string template literals to build few sentences about the weather forecast for Sunday. (Example: "The high on Sunday will be 47 and the low will be 35. We're predicting a chance of rain. The sun will rise at 7:45 AM and set at 5:07 PM.")

### 5. Student Grades
In your JavaScript file, copy and paste the following array:
```js
let williamGrades = [62, 97, 99, 85, 73, 97];
```
1. Print the first grade in the array to the console.
1. Print the last grade in the array to the console.
1. Use JavaScript to find William's average grade.


### 6. Movie Star
1. In your JavaScript file, create an object that represents a famous movie star. Your object should have the following properties:
    - `firstName`
    - `lastName`
    - `age`
    - `favoriteFood`

1. Log the movie star's favorite food to the console.
1. Use string template literals to log their full name to the console.
1. Use string template literals to log a sentence or two about your movie star to the console. (Example: "Dwayne The Rock Johnson is 46 years old. His favorite food is raw meat.")



### 7. Dwayne's Hobbies
Refactor your movie star object to add their hobbies. Now your object should look something like this:
```js
let dwayneObject = {
  firstName: "Dwayne",
  lastName: "Johnson",
  favoriteFood: "Eggs",
  hobbies: ["jumping out of planes", "personally holding the  San Andreas fault together", "building incredible muscle mass"]
}
```
1. Log each one of their hobbies individually to the console.
1. Use string template literals to create a sentence about their hobbies. You should include how many hobbies they have in your sentence. (Hint: use the `.length` property.) Example output: "They have three main hobbies: jumping out of planes, personally holding the San Andreas fault together, and building muscle mass.") Store your new setnence in a variable called `hobbiesSentence` then log it to the console.


## Challenge
### Weather Data
Here's some real data from the Yahoo Weather API:
```js
let weatherData = {
 "query": {
  "count": 1,
  "created": "2018-12-06T20:52:22Z",
  "lang": "en-US",
  "results": {
   "channel": {
    "units": {
     "distance": "mi",
     "pressure": "in",
     "speed": "mph",
     "temperature": "F"
    },
    "title": "Yahoo! Weather - Nome, AK, US",
    "link": "http://us.rd.yahoo.com/dailynews/rss/weather/Country__Country/*https://weather.yahoo.com/country/state/city-2460286/",
    "description": "Yahoo! Weather for Nome, AK, US",
    "language": "en-us",
    "lastBuildDate": "Thu, 06 Dec 2018 11:52 AM AKST",
    "ttl": "60",
    "location": {
     "city": "Nome",
     "country": "United States",
     "region": " AK"
    },
    "wind": {
     "chill": "14",
     "direction": "68",
     "speed": "36"
    },
    "atmosphere": {
     "humidity": "90",
     "pressure": "989.0",
     "rising": "0",
     "visibility": "11.0"
    },
    "astronomy": {
     "sunrise": "11:38 am",
     "sunset": "4:7 pm"
    },
    "image": {
     "title": "Yahoo! Weather",
     "width": "142",
     "height": "18",
     "link": "http://weather.yahoo.com",
     "url": "http://l.yimg.com/a/i/brand/purplelogo//uh/us/news-wea.gif"
    },
    "item": {
     "title": "Conditions for Nome, AK, US at 11:00 AM AKST",
     "lat": "64.499474",
     "long": "-165.405792",
     "link": "http://us.rd.yahoo.com/dailynews/rss/weather/Country__Country/*https://weather.yahoo.com/country/state/city-2460286/",
     "pubDate": "Thu, 06 Dec 2018 11:00 AM AKST",
     "condition": {
      "code": "15",
      "date": "Thu, 06 Dec 2018 11:00 AM AKST",
      "temp": "28",
      "text": "Blowing Snow"
     },
     "forecast": [
      {
       "code": "16",
       "date": "06 Dec 2018",
       "day": "Thu",
       "high": "29",
       "low": "25",
       "text": "Snow"
      },
      {
       "code": "26",
       "date": "07 Dec 2018",
       "day": "Fri",
       "high": "27",
       "low": "22",
       "text": "Cloudy"
      },
      {
       "code": "28",
       "date": "08 Dec 2018",
       "day": "Sat",
       "high": "22",
       "low": "8",
       "text": "Mostly Cloudy"
      },
      {
       "code": "34",
       "date": "09 Dec 2018",
       "day": "Sun",
       "high": "7",
       "low": "-11",
       "text": "Mostly Sunny"
      },
      {
       "code": "28",
       "date": "10 Dec 2018",
       "day": "Mon",
       "high": "3",
       "low": "-11",
       "text": "Mostly Cloudy"
      },
      {
       "code": "28",
       "date": "11 Dec 2018",
       "day": "Tue",
       "high": "10",
       "low": "2",
       "text": "Mostly Cloudy"
      },
      {
       "code": "26",
       "date": "12 Dec 2018",
       "day": "Wed",
       "high": "9",
       "low": "5",
       "text": "Cloudy"
      },
      {
       "code": "28",
       "date": "13 Dec 2018",
       "day": "Thu",
       "high": "14",
       "low": "8",
       "text": "Mostly Cloudy"
      },
      {
       "code": "30",
       "date": "14 Dec 2018",
       "day": "Fri",
       "high": "13",
       "low": "-3",
       "text": "Partly Cloudy"
      },
      {
       "code": "30",
       "date": "15 Dec 2018",
       "day": "Sat",
       "high": "7",
       "low": "-3",
       "text": "Partly Cloudy"
      }
     ],
     "description": "<![CDATA[<img src=\"http://l.yimg.com/a/i/us/we/52/15.gif\"/>\n<BR />\n<b>Current Conditions:</b>\n<BR />Blowing Snow\n<BR />\n<BR />\n<b>Forecast:</b>\n<BR /> Thu - Snow. High: 29Low: 25\n<BR /> Fri - Cloudy. High: 27Low: 22\n<BR /> Sat - Mostly Cloudy. High: 22Low: 8\n<BR /> Sun - Mostly Sunny. High: 7Low: -11\n<BR /> Mon - Mostly Cloudy. High: 3Low: -11\n<BR />\n<BR />\n<a href=\"http://us.rd.yahoo.com/dailynews/rss/weather/Country__Country/*https://weather.yahoo.com/country/state/city-2460286/\">Full Forecast at Yahoo! Weather</a>\n<BR />\n<BR />\n<BR />\n]]>",
     "guid": {
      "isPermaLink": "false"
     }
    }
   }
  }
 }
}

```
You'll need to use [bracket notation](https://codeburst.io/javascript-quickie-dot-notation-vs-bracket-notation-333641c0f781) to mine into this object because the keys are strings.

Use JavaScript to answer the following questions and log your answers to the console.

1. What time was sunrise this morning in Nome, AK?
1. What was the wind chill in Nome, AK when this data was generated?
1. What was the visibility?
1. What will be the high on Saturday the 8th?
1. Use string template literals to build a sentence about the weather forecast for Saturday, Dec 15. (Example: "Saturday, December 15 will be Partly Cloudy with a high of 7 and a low of -3".)
    - In the data, "Partly Cloudy" is capitalized, but in our sentence that doesn't really make sense. Look up the [method to convert a string to lowercase.](https://www.w3schools.com/jsref/jsref_tolowercase.asp)
1. What is the average forecasted high temperature for the next seven days?
