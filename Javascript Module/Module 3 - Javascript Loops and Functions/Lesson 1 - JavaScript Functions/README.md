# Lesson 1: JavaScript Functions

## Write Reusable JavaScript with Functions

In JavaScript, we can divide up our code into reusable parts called *functions*.

Here's an example of a function:

```js
function functionName() {
  console.log("Hello World");
}
```

You can call or *invoke* this function by using its name followed by parentheses, like this: `functionName()`; Each time the function is called it will print out the message `Hello World` on the dev console. All of the code between the curly braces will be executed every time the function is called.


## Passing Values to Functions with Arguments

*Parameters* are variables that act as placeholders for the values that are to be input to a function when it is called. When a function is defined, it is typically defined along with one or more parameters. The actual values that are input (or "passed") into a function when it is called are known as arguments.

Here is a function with two parameters, `param1`, and `param2`:

```js
function testFun(param1, param2) {
  console.log(param1, param2);
}
```

Then we can call `testFun` like this: `testFun("Hello", "World");`. We have passed two string arguments, `Hello` and `World`. Inside the function, `param1` will equal the string `Hello` and `param2` will equal the string `World`. Note that you could call `testFun` again with different arguments and the parameters would take on the value of the new arguments.

## Return a Value from a Function with Return

We can pass values into a function with *arguments*. You can use a `return` statement to send a value back out of a function.

Example

```js
function plusThree(num) {
  return num + 3;
}

const answer = plusThree(5);
```

`answer` has the value `8`.

`plusThree` takes an argument for `num` and returns a value equal to `num + 3`.

## Global Scope and Functions

In JavaScript, scope refers to the visibility of variables. Variables that are defined outside of a function block have Global scope. This means they can be seen everywhere in your JavaScript code.

Variables that are declared without the `let` or `const` keywords are automatically created in the global scope. This can create unintended consequences elsewhere in your code or when running a function again. You should always declare your variables with `let` or `const`.


## Local Scope and Functions

Variables that are declared within a function, as well as the function parameters, have local scope. That means they are only visible within that function.

Here is a function `myTest` with a local variable called `loc`.

```js
function myTest() {
  const loc = "foo";
  console.log(loc);
}

myTest();
console.log(loc);
```

The `myTest()` function call will display the string `foo` in the console. The `console.log(loc)` line (outside of the `myTest` function) will throw an error, as `loc` is not defined outside of the function.


## Global vs. Local Scope in Functions

It is possible to have both *local* and *global* variables with the same name. When you do this, the local variable takes precedence over the global variable.

In this example:

```js
const someVar = "Hat";

function myFun() {
  const someVar = "Head";
  return someVar;
}
```

The function `myFun` will return the string `Head `because the local version of the variable is present.

## Assignment with a Returned Value

If you'll recall from our discussion about [**Storing Values with the Assignment Operator**](https://github.com/jfmartinz/web3Notes/tree/main/Javascript%20Module/Module%201%20-%20Javascript%20Variables%20and%20Operators/Lesson%201%20-%20Declaring%20and%20Initializing%20Variables#storing-values-with-the-assignment-operator), everything to the right of the equal sign is resolved before the value is assigned. This means we can take the return value of a function and assign it to a variable.

Assume we have pre-defined a function `sum` that adds two numbers together, then:

```js
ourSum = sum(5, 12);
```

will call the `sum` function, which returns a value of `17` and assigns it to the `ourSum` variable.

## Returning Boolean Values from Functions

You may recall from [**Comparison with the Equality Operator**](https://github.com/jfmartinz/web3Notes/tree/main/Javascript%20Module/Module%201%20-%20Javascript%20Variables%20and%20Operators/Lesson%205%20-%20%20If%20Statements%20and%20Conditional%20Logic#comparison-with-the-equality-operator) that all comparison operators return a boolean `true` or `false` value.

Sometimes people use an `if/else` statement to do a comparison, like this:

```js
function isEqual(a, b) {
  if (a === b) {
    return true;
  } else {
    return false;
  }
}
```

But there's a better way to do this. Since `===` returns `true` or `false`, we can return the result of the comparison:

```js
function isEqual(a, b) {
  return a === b;
}
```

## Return Early Pattern for Functions

When a `return` statement is reached, the execution of the current function stops, and control returns to the calling location.

Example

```js
function myFun() {
  console.log("Hello");
  return "World";
  console.log("byebye")
}
myFun();
```