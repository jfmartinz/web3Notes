# Lesson 1: Declaring and Initializing Variables


## Comment Your JavaScript Code

Comments are lines of code that JavaScript will intentionally ignore. Comments are a great way to leave notes to yourself and to
other people who will later need to figure out what that code does.

There are two ways to write comments in JavaScript:

Using `//` will tell JavaScript to ignore the remainder of the text on the current line. This is an **inline comment**.


```js
// This is an inline comment
```

You can make a multi-line comment beginning with `/*`
and ending with `*/`. This is a **multi-line comment**.


```js
/*
 This is a multi-line
  comment
*/
```


## Declare JavaScript Variables

### Data
In computer science, data is anything that is meaningful to the computer. JavaScript provides eight different data types which are
`undefined` , `null`, `boolean` , `string` , `symbol` , `bigint` , `number` , and `Object`.

### Variables

Variables allow computers to store and manipulate data in a dynamic fashion. They do this by using a **"label"** to point to the data rather than using the data itself. Any of the eight data types may be stored in a variable.

Variables are similar to the x and y variables you use in mathematics, which means they're a simple name to represent the data we want to refer to. Computer variables differ from mathematical variables in that they can store different values at different times.

We tell JavaScript to create or declare a variable by putting the keyword `var` in front of it, like so:

```js
var ourName;
```
creates a variable called `ourName`. In JavaScript, we end statements with semicolons. Variable names can be made up of numbers, letters, and `$` or `_`, but may not contain spaces or start with a number.

## Storing Values with the Assignment Operator
In JavaScript, you can store a value in a variable with the assignment operator `(=)`

```js
myVariable = 5;
```

This assigns the Number value 5 to myVariable.

If there are any calculations to the right of the `=` operator, those are performed before the value is assigned to the variable on the left of the operator

```js
var myVar;
myVar = 5;
```
First, this code creates a variable named `myVar`. Then, the code assigns 5 to `myVar`. Now, if `myVar` appears again in the code, the program will treat it as if it is 5.


## Assigning the Value of One Variable to Another
After a value is assigned to a variable using the assignment operator, you can assign the value of that variable to another variable using the assignment operator.

```js
var myVar;
myVar = 5;

var myNum;
myNum = myVar;
```

The above declares a `myVar` variable with no value, then assigns it the value 5. Next, a variable named `myNum` is declared with no value. Then, the contents of `myVar` (which is 5) is assigned to the variable `myNum`. Now, myNum also has the value of 5.

## Initializing Variables with the Assignment Operator
It is common to initialize a variable to an initial value in the same line as it is declared.

```js
var myVar = 0;
```
Creates a new variable called `myVar` and assigns it an initial value of 0.

## Declare String Variables

Previously you used the following code to declare a variable:

```js
var myName;
```

But you can also declare a string variable like this:
```js
var myName = "Your name";
```

`"your name"` is called a string literal. A string literal, or string, is a series of zero or more characters enclosed in single or double quotes.

## Understanding Case Sensitivity in Variables
In JavaScript, all variables and function names are case-sensitive. This means that capitalization matters.

### Best Practice
Write variable names in JavaScript in *camelCase*. In camelCase, multi-word variable names have the first word in lowercase and the first letter of each subsequent word is capitalized.

```js
var someVariable;
var anotherVariable;
var thisVariableIsTooLong;
```

## Explore Differences Between the var and let Keywords
One of the biggest problems with declaring variables with the var keyword is that you can easily overwrite variable declarations:

```js
var camper = "James";
var camper = "David";

console.log(camper);
```
In the code above, the `camper` variable is originally declared as `James`, and is then overridden to be `David`. The console then displays the string `David`.

In a small application, you might not run into this type of problem. But as your codebase becomes larger, you might accidentally overwrite a variable that you did not intend to. Because this behavior does not throw an error, searching for and fixing bugs becomes more difficult.

A keyword called `let` was introduced in ES6, a major update to JavaScript, to solve this potential issue with the `var` keyword. You'll learn about other ES6 features in later challenges.

If you replace var with let in the code above, it results in an error:

> SyntaxError: Identifier 'camper' has already been declared

So unlike var, when you use let, a variable with the same name can only be declared once.

## Declare a Read-Only Variable with the const Keyword
The keyword `let` is not the only new way to declare variables. In ES6, you can also declare variables using the `const` keyword.

`const` has all the awesome features that `let` has, with the added bonus that variables declared using const are **read-only**. They are a constant value, which means that once a variable is assigned with const, it cannot be reassigned:

```js
const FAV_PET = "Cats";
FAV_PET = "Dogs";
```

The console will display an error due to reassigning the value of `FAV_PET`.

> TypeError: Assignment to constant variable.

You should always name variables you don't want to reassign using the `const` keyword. This helps when you accidentally attempt to reassign a variable that is meant to stay constant.

 > Note: It is common for developers to use uppercase variable identifiers for immutable values and lowercase or camelCase for mutable values (objects and arrays). You will learn more about objects, arrays, and immutable and mutable values in later challenges. Also in later challenges, you will see examples of uppercase, lowercase, or camelCase variable identifiers.
 

 ## Additional resource 

 - Visit the W3Schools website for more information about [JavaScript Variables](https://www.w3schools.com/js/js_variables.asp)