# JavaScript Functions

You're already very familiar with the idea of wrapping our code as methods in Ruby in order to make them reusable. In JavaScript, we call them functions and the syntax is slightly different, but the general idea is the same.

## Objectives
+ Explain how function return values work
+ Write a function in JavaScript without parameters
+ Return a value from a function in JavaScript
+ Write a function with parameters

## Function without parameters
Here's the basic syntax for a function that doesn't take any parameters (you know them as arguments):
```js
function nameOfFunction() {
  // code goes here
  return valueToReturn;
}
```

Notice the `def` keyword has been replaced with the `function` keyword. The name of the function is always followed by `()` and then curly braces that begin and end the function.

Further, the name of the function is not snake_cased, but rather lowerCamelCased. Snakecase is not used in JavaScript, so leave your underscores at home, people!

One last important thing to note is that JavaScript functions will always return `undefined` unless you use the `return` keyword. In Ruby, writing `return` is optional because Ruby always returns the value of the last line of code evaluated, but this is not the case for JavaScript.

Here's a simple example of a function that will greet us good morning:
```js
function greet() {
  return "Good morning you!";
}
```

To call a function, you type the function's name followed by parentheses and a semicolon:
```js
// Returns "Good morning you!"
greet();
```

If you try to call on a function using just its name, as you can in Ruby, the entire function will get returned back to you instead of the function's return value, so be careful!

```js
// Returns [Function: greet]
greet;
```

It's important to note that JavaScript does not run the code during a function definition. All it does is read that there is a function called `greet` and store it in memory. It doesn't actually create any of the variables inside the function (if there are any) until the method is called.

## Function Return Values
Unless you use the `return` keyword or call a function that explicitly returns a value, the implicit return value in JavaScript is  `undefined`.

> Undefined represents the absence of a primitive value

Other special return values in JavaScript are `null`

> Null represents the absence of an object

and `NaN`

> NaN represents an error from the improper use of a math operator.

## Parameters
The above function is fine, but it could be better. For instance, what if you wanted your program to say the person's name instead of just "you" (ex. "Good morning Adam!" or "Good morning Steph!"). Well, just like in Ruby, you'd want to pass this function an argument. In JavaScript, arguments are called parameters.

```js
function greet(name) {
  return "Good morning " + name + "!";
}

// Returns "Good morning Adam!"
greet("Adam");

// Returns "Good morning Steph!"
greet("Steph");
```

Cool! So much better and more dynamic than having JavaScript return "Good morning you!". What if we also wanted it to greet us based on the time of day, for instance "Good afternoon Harold!" or "Good night Jasmine!"? Well, then we'd have to pass our function a second parameter, the time of day:
```js
function greet(name, timeOfDay) {
  return "Good "+ timeOfDay + " "+ name + "!";
}

// Returns "Good afternoon Harold!"
greet("Harold", "afternoon");

// Returns "Good night Jasmine!"
greet("Jasmine", "night");
```

Like in Ruby, you can add as many parameters to your JavaScript functions as you like. Or you can pass them none. Just depends on what task you're trying to accomplish.

Unlike Ruby, JavaScript doesn't force you to call a function with a set number of parameters. If a JavaScript function is defined to accept two parameters, and you call the function with only one parameter, the function will still run, placing `undefined` in the spot of the missing paramater:
```js
function greet(name, timeOfDay) {
  return "Good "+ timeOfDay + " "+ name + "!";
}

greet("joe");
// returns "Good undefined joe!"
```

Be careful when calling functions with parameters. This could inadvertently mess up your return values.

## Function Expression
There are two different ways to write functions in JavaScript. You can write them as a function **declaration**, which is how we've been writing them, or as a function **expression**.

While a function declaration looks like this:
```js
function greet(name, timeOfDay) {
  return "Good "+ timeOfDay + " "+ name + "!";
}
```

A function expression looks something like this:
```js
var greet = function(name, timeOfDay){
  return "Good "+ timeOfDay + " "+ name + "!";
};
```

Here, the function is created and assigned to the variable `greet` explicitly, like any other value. No matter how the function is defined, it’s just a value stored in a variable called `greet`.

The meaning of these code samples is the same: "create a function and put it into the variable `greet`".

We can still call this function in the same way we would a function written with a function declaration:
```js
// Returns "Good afternoon Grover!"
greet("Grover", "afternoon");
```

It's good to be familiar with both ways of writing a function for when you start working with other developers (but remember that you can always Google resources for help).


## Resources
* [Eloquent JavaScript - Functions](http://eloquentjavascript.net/03_functions.html)
* [MDN - Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions)


<p data-visibility='hidden'>View <a href='https://learn.co/lessons/intro-to-functions.js' title='JavaScript Functions'>JavaScript Functions</a> on Learn.co and start learning to code for free.</p>
