# Javascript 101 - Part 1

## Prerequisite Homework

1. Read chapters 1-9 of "**A smarter way to learn JavaScript**".
1. Do all of the interactive coding exercises for each chapter.
1. *Treehouse* > *JavaScript Basics Course*: Watch first two videos and do the review questions
1. Make sure all students can boot Vagrant machine.

## Overview

Javascript is **the most important language** you will use as a front end developer, and possibly for much of your career, because it is the language of the web browser. All browser based applications - Facebook, Twitter, Etsy, Pinterest - are all written with JavaScript.

## The Alert

Use alert to show messages to people using your application.

`alert("Thank you for using our product");`

## Variables

Learn how to store values in human readable variables that can be used throughout your code, and changed when necessary. It is the same as your bank account number. That number never changes, but the actual value of your bank account changes daily as you make money and spend money.

### Number values

You bank account number is a variable, and the money contained in it is the value of the variable. In JavaScript, you can create a variable name that will hold any value you want.

`var bankAccount = 1000;`

Now, anywhere else in the code that you use the `bankAccount` variable, the value of 1000 will actually be used.

`var combinedAccount = 2000 + bankAccount;`

The new variable called `combinedAccount` will now hold the value 3000.

### String values
Variables can hold all kinds of values. Here's one holding a string value. Strings are a continuous collection of letters and values inside two quote characters.

```
var instructor = "Steve";
var numberOfStudents = "15";
```

### Boolean values

These variables will hold the value of `true` or `false`.

```
var studentsAreAwesome = true;
var limaBeansAreYummy = false;
```

### Declaring variables

You can declare a variable first, and then assign it a value later.
```
var fruit;
fruit = "apple";
```

But, as we saw before, you can declare it and assign it a value on the same line of code.
```
var fruit = "apple";
```

### Changing variable values

Declare a variable and give it an initial value.

```
var name = "Beth";
```

You can modify the value of a variable at any time, which is why they are called variables, because their value varies any time you want.

```
var name = "Susan";
```

If you tried to use the variable `name` at this point, it's value would be `Susan` even though you initially provided the value of `Beth`. 

## Math Expressions

How to do math with JavaScript. Show the main mathematical operators, and their use with integer value variables.

`+`,`-`,`/`,`%`, `*`

## Conditions with *if* and *else*

Learn how to check if something is true or false, and execute different code for each case. First, you evaluate if a condition is true or false.  If it is true, execute the code inside the surrounding curly braces (or mustaches).

> **Tip: ** There are several types of punctuation in JavaScript. {} are braces, [] are brackets, () are parenthesis, <> are angle brackets.

```
if (studentsAreAwesome) {
   alert("Congratulations!! You get a new career.");
}
```

If `studentsAreAwesome` was **false**, then the alert would not be shown. Use the else condition to handle when your evaluation is false.

```
if (studentsAreAwesome) {
   alert("Congratulations!! You get a new career.");
} else {
   alert("Back to the plutonium mines for you!");
}
```

## The console

Learn how to output the value of variables to the browser's console.

```
console.log("Hello, world!");
```

> **Instructor Suggestion:** 
> Break now for class exercises. Have students do at least 3 different challenges that makes them create variables, perform math functions, and check boolean expressions.
> 
> * How many hours are in a year
> * How many minutes are in a decade
> * How many seconds old they are
> * If they are older than some arbitrary number, alert "I'm old", else "I'm young"

## Arrays

Arrays are like buckets that you can use to store a collection numbers and/or strings.

```
var commands = ["blue", 42, "shift left", "hut"];
```

### Adding/removing items to an array

You can specify a value to place at a specific index (position).

```
commands[0] = "periwinkle";
commands[3] = 24;

// ["periwinkle", 42, "shift left", 24]
```

You can use the `push()` method which is available on an variable that holds an array. This method puts a new item on the end of the array.

```
commands.push("hot route");

// ["periwinkle", 42, "shift left", 24, "hot route"]
```

To remove the last item, you have to `pop()` it off.

```
var lastOne = commands.pop();

// ["periwinkle", 42, "shift left", 24]
// lastOne now contains the value "hot route"
```

The `unshift()` and `shift()` methods add and remove items from the beginning of the array.


## Loops with *for*

Learn how to execute the same code against every items in an array. The *for* loop has several key elements that allow you to execute the same logic over and over again, a predetermined number of times.

First, you state an initial value that will be checked each time through the loop.

```
for (var count = 1;;) {
   // Do something
}
```
Next, you put in a condition check. If it evaluates to true, then the logic inside the loop will execute.
```
for (var count = 1; count < 10;) {
   // Do something
}
```
The last element is what will be executed each time through your loop. In this example, we're simply going to increase the value of our `count` variable by 1.
```
for (var count = 1; count < 10; count = count + 1) {
   console.log("Current value of count = ", count);
}
```

You can perform any mathematical operation on the `count` variable that you want. Increment by 1, decrement by 5, multiply by 3, divide by 10... whatever you need for the problem you're trying to solve.

> **Instructor Suggestion:** 
> Break now for class exercises. Have students do 4 different challenges that makes them start at different initial values, use different evaluation punctuation (>, <, <=, >=), and increment/decrement the counter by different amounts.
>
> * Write a for loop that increments the counter variable by 10 each time, and displays the value.
> * Write a for loop that divides the counter variable by 2 each time, and displays the value.
> * Augment the loop to insert each new value into an array
> * Write a loop that starts at 100 and decrements a variable by 1. If the number is even, add the number to the beginning of an array, else add it to the end of the array.

## String manipulation

### Joining two strings together
It's called concatenation.
```
var firstName = "Michael";
var lastName = "Corleone";
var fullName = firstName + " " + lastName;

alert(fullName);
```

In JavaScript, the `+` character not only adds two numbers together, but it also concatenates strings

### How long is it?
```
var phrase = "How much wood would a woodchuck chuck if a woodchuck could chuck wood";
alert(phrase.length);
```
### Finding characters in a string
You use the `indexOf()` method that is automatically added to any variable that holds a string value.

```js
var phrase = "The quick brown fox jumps over the lazy dog.";

// In JavaScript, the first position of a string 
// (called the index) is actually 0, not 1. The 
// same is true in arrays.
alert(phrase.indexOf("T"));

alert(phrase.indexOf("x"));
```

### Determine which character is at a position in a string
Yo use the `charAt()` method that is automatically added to any variable that holds a string value.

```js
var phrase = "How now brown cow?";
var position = phrase.charAt(8);
alert(position); // Will alert "b"
```

### Replacing characters in a string
You use the `replace()` method that is automatically added to any variable that holds a string value.

```js
var phrase = "The lazy dog";
var newPhrase = phrase.replace("lazy", "bounding");
alert(newPhrase);
```

Change every occurrence by using a regular expression. Try this out.

```js
var phrase = "The lazy dog likes the weird fox";
var newPhrase = phrase.replace(/o/g, "i");
alert(newPhrase);
```

### Converting strings to numbers

```js
var five = "5"; // "5"
var numberFive = parseInt(five); // 5
```

## Adding strings to your web page

Learn to use `document.getElementById()` and  `element.innerHTML` to add text to a web page with JavaScript. This is an alternative to `document.write()` which is taught in the Treehouse video for their first JavaScript program.

##### **Example**
---
```html
<div id="container">

</div>
```

```javascript
var phrase = "Hey, look at me!";
var element = document.getElementById("container");
element.innerHTML = phrase;
```

> **Instructor Suggestion:** 
> Break now for class exercises. Have students do exercises for each of the string methods you covered, and then use Codepen to build up some HTML inside a string (for example, using some p, a, div tags) and insert that code in the document. Build multiple JS strings, multiple HTML elements, and then do multiple inserts into different elements.  Also have them insert new HTML inside HTML they already inserted.

---

## Homework

1. Read chapters 10-25 of "**A smarter way to learn JavaScript**".
2. Do all of the interactive coding exercises for each chapter.
3. Watch the following Treehouse videos
  4. *Where does JavaScript go?*
  5. *Write another program*
  6. *Link to an external script*

---

# Javascript 101 - Part 2

Time to move on from CodePen. From this point on, work will be done in SublimeText and Chrome, and files will be served from the Vagrant box.

## Switch statement

```js
var value = 10;
switch (value) {
  case 1:
    console.log("Small number");
  case 5:
    console.log("Medium number");
  case 1:
    console.log("Large number");
  default:
    console.log("Dunno");
}
```

## Vagrant

Have each student go to their CLI and run `vagrant up` and `vagrant ssh`. 

## First full web page

In this part, students will be creating a full, but basic, web document that combines the HTML and the JavaScript - both inline and via an external link - and open it up in Chrome.

1. Have students create `/vagrant/js-101` directory.
1. Each student should grab the `resources/__basic.html`, copy it into the **js-101** directory, and rename it as `index.html`.
1. Have students create a script element before the closing body tag, and put some basic JS in there that logs to the console, or creates an alert box, whatever you like.

## Starting basic web server

```
cd /vagrant
http-server ./
```

## Open page and linking JS

1. Open `http://192.168.33.10:8080/js-101/` and make sure the code works.
1. Then have them create `main.js` file in same directory.
1. Copy the code from the script element into the new JS file.
1. Update the script element to be an external link.
1. Refresh browser and ensure code still works.

> **Instructor Suggestion:** 
> Start the students on the [colored reindeer](http://codepen.io/chortlehoort/pen/WbZPze?editors=101) problem, and then [boy bands & vegetables](http://codepen.io/chortlehoort/pen/myBvrL?editors=101).
> 
> After those have been completed, and reviewed, move on to have students write a program that loops over an array of student grades (values from 50-100) and outputs how many of each grades there are.  50-60=F, 61-70=D, 71-80=C, 81-90=B, 91-100=A.
> 
> Start with array of random scores: 
> `var scores = [82, 71, 95, 55, 98, 69, 72, 78, 84, 64, 58, 87];`
> 
> * How many of each grade?
> * What is the lowest grade?
> * What is the highest grade?


## Homework 

Students must use JavaScript to create a list of songs in their Music History page. Have them download the `resources/js-101.js` file, which contains an array of strings with song information.

1. Each student must add one song to the beginning and the end of the array.
1. Loop over the array and remove any words that obviously don't belong. Hint, use a [JavaScript regular expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions).
1. Students must find and replace the `>` character in each item with a `-` character.
1. Must add each string to the DOM container that holds the song list.

 ------------------------------------------------
|  {Song name} by {Artist} on the album {Album}  | 
 ------------------------------------------------

Suggest that the students use a `div` element to insert each item into the DOM.

---

# Want to learn more?

1. You've learned how to use a boolean condition check with *if..else* statements, but what if a condition has more than just a true/false state? Learn how to use a [switch statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch)
1. Learn how to catch exceptions (errors) in your code and handle them gracefully with a [*try..catch..finally*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/try...catch) block.
1. When trying to find out what's causing an error in your code, a useful command is the [debugger](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/debugger) statement. Try putting it in your code and watch what happens when you run it in Chrome.
1. Now that you know how to declare variables, you can learn about how JavaScript [hoists](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var#var_hoisting) variable declarations.
1. Learn how to assign the [same value to two variables](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var#Assigning_two_variables_with_single_string_value) with a single line of code.

---

# Challenge \#1

What is the smallest number  that can be divided by each of the numbers from 1 to 10 without any remainder?

# Challenge \#2

Write a [Fibonacci number](https://en.wikipedia.org/wiki/Fibonacci_number) generator that outputs the numbers in the series that are less than 500.

# Challenge \#3

What is the difference between the sum of the squares of the first ten natural numbers, and the square of the sum of the first ten natural numbers?
