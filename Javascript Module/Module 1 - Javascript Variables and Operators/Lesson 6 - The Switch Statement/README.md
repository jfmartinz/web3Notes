# Lesson 6: The Switch Statement

## Selecting from Many Options with Switch Statements

If you have many options to choose from, use a switch statement. A `switch` statement tests a value and can have many case statements which define various possible values. Statements are executed from the first matched `case` value until a `break` is encountered.

Here is an example of a `switch` statement:

```js
switch (lowercaseLetter) {
  case "a":
    console.log("A");
    break;
  case "b":
    console.log("B");
    break;
}
```

`case` values are tested with strict equality `(===)`. The `break` tells JavaScript to stop executing statements. If the `break` is omitted, the next statement will be executed.

## Adding a Default Option in Switch Statements

In a `switch` statement you may not be able to specify all possible values as `case` statements. Instead, you can add the `default` statement which will be executed if no matching `case` statements are found. Think of it like the final `else` statement in an `if/else` chain.

A `default` statement should be the last case.

```js
switch (num) {
  case value1:
    // statement1;
    break;
  case value2:
    // statement2;
    break;
...
  default:
    // defaultStatement;
    break;
}
```

## Multiple Identical Options in Switch Statements

If the `break` statement is omitted from a `switch` statement's `case`, the following `case` statement(s) are executed until a `break` is encountered. If you have multiple inputs with the same output, you can represent them in a `switch` statement like this:

```js
let result = "";
switch (val) {
  case 1:
  case 2:
  case 3:
    result = "1, 2, or 3";
    break;
  case 4:
    result = "4 alone";
}
```
Cases for 1, 2, and 3 will all produce the same result.

## Additional resources

- [JavaScript Switch Statement](https://www.w3schools.com/js/js_switch.asp)<br>
- [Switch Javascript | MDN docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch)