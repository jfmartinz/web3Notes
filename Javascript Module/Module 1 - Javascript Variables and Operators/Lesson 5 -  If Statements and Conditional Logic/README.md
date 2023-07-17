# Lesson 5: If Statements and Conditional Logic


## Table of Contents

[1. Understanding Boolean Values](#understanding-boolean-values)<br>
[2. Use Conditional Logic with If Statements](#use-conditional-logic-with-if-statements)<br>
[3. Comparison with the Equality Operator](#comparison-with-the-equality-operator)<br>
[4. Comparison with the Strict Equality Operator](#comparison-with-the-strict-equality-operator)<br>
[5. Comparison with the Inequality Operator](#comparison-with-the-inequality-operator)<br>
[6. Comparison with the Strict Inequality Operator](#comparison-with-the-strict-inequality-operator)<br>
[7.Comparison with the Greater Than Operator](#comparison-with-the-greater-than-operator)<br>
[8. Comparison with the Greater Than Or Equal To Operator](#comparison-with-the-greater-than-or-equal-to-operator)<br>
[9. Comparison with the Less Than Operator](#comparison-with-the-less-than-operator)<br>
[10. Comparison with the Less Than Or Equal To Operator](#comparison-with-the-less-than-or-equal-to-operator)<br>
[11. Comparisons with the Logical And Operator](#comparisons-with-the-logical-and-operator)<br>
[12. Comparisons with the Logical Or Operator](#comparisons-with-the-logical-or-operator)<br>
[13. Introducing Else Statements](#introducing-else-statements)<br>
[14. Introducing Else If Statements](#introducing-else-if-statements)<br>
[15. Logical Order in If Else Statements](#logical-order-in-if-else-statements)<br>
[16.Chaining If Else Statements](#chaining-if-else-statements)<br>
[17. Additional resources](#additional-resources)

## Understanding Boolean Values
Another data type is the Boolean. Booleans may only be one of two values: `true` or `false`. They are basically little on-off switches, where *true is on* and *false is off*. These two states are mutually exclusive.

> Note: Boolean values are never written with quotes. The strings `"true"` and `"false"` are not Boolean and have no special meaning in JavaScript.

## Use Conditional Logic with If Statements

`if` statements are used to make decisions in code. The keyword `if` tells JavaScript to execute the code in the curly braces under certain conditions, defined in the parentheses. These conditions are known as `Boolean` conditions and they may only be `true` or `false`.

Pseudocode

```js
if (condition is true) {
 statement is executed
 }
```

Example

```js
function test (myCondition) {
  if (myCondition) {
    return "It was true";
  }
  return "It was false";
}

test(true);
test(false);
```

`test(true)` returns the string `It was true`, and `test(false)` returns the string `It was false`.

When `test` is called with a value of `true`, the `if` statement evaluates `myCondition` to see if it is `true` or not. Since it is `true`, the function returns `It was true`. When we call `test` with a value of `false`, `myCondition` is not `true` and the statement in the curly braces is not executed and the function returns `It was false`.

## Comparison with the Equality Operator

There are many comparison operators in JavaScript. All of these operators return a boolean `true` or `false` value.

The most basic operator is the equality operator `==`. The equality operator compares two values and returns `true` if they're equivalent or `false` if they are not. Note that equality is different from assignment `(=)`, which assigns the value on the right of the operator to a variable on the left.

```js
function equalityTest(myVal) {
  if (myVal == 10) {
    return "Equal";
  }
  return "Not Equal";
}
```

If `myVal` is equal to `10`, the equality operator returns `true`, so the code in the curly braces will execute, and the function will return `Equal`. Otherwise, the function will return `Not Equal`. In order for JavaScript to compare two different data types (for example, `numbers` and `strings`), it must convert one type to another. This is known as `Type Coercion`. Once it does, however, it can compare terms as follows:

```js
1   ==  1  // true
1   ==  2  // false
1   == '1' // true
"3" ==  3  // true
```

## Comparison with the Strict Equality Operator
Strict equality `(===)` is the counterpart to the equality operator `(==)`. However, unlike the equality operator, which attempts to convert both values being compared to a common type, the strict equality operator does not perform a type conversion.

If the values being compared have different types, they are considered unequal, and the strict equality operator will return false.

```js
3 ===  3  // true
3 === '3' // false
```
In the second example, `3` is a `Number` type and `'3'` is a `String` type.

## Comparison with the Inequality Operator

The inequality operator `(!=)` is the opposite of the equality operator. It means not equal and returns `false` where equality would return `true` and vice versa. Like the equality operator, the inequality operator will convert data types of values while comparing.

```js
1 !=  2    // true
1 != "1"   // false
1 != '1'   // false
1 != true  // false
0 != false // false
```

## Comparison with the Strict Inequality Operator

The strict inequality operator `(!==)` is the logical opposite of the strict equality operator. It means **"Strictly Not Equal"** and returns `false` where strict equality would return `true` and vice versa. The strict inequality operator will not convert data types.

```js
3 !==  3  // false
3 !== '3' // true
4 !==  3  // true
```

## Comparison with the Greater Than Operator

The greater than operator `(>)` compares the values of two numbers. If the number to the left is greater than the number to the right, it returns `true`. Otherwise, it returns `false`.

Like the equality operator, the greater than operator will convert data types of values while comparing.

```js
5   >  3  // true
7   > '3' // true
2   >  3  // false
'1' >  9  // false
```

## Comparison with the Greater Than Or Equal To Operator

The greater than or equal to operator `(>=)` compares the values of two numbers. If the number to the left is greater than or equal to the number to the right, it returns `true`. Otherwise, it returns `false`.

Like the equality operator, the greater than or equal to operator will convert data types while comparing.

Examples

```js
6   >=  6  // true
7   >= '3' // true
2   >=  3  // false
'7' >=  9  // false
```

## Comparison with the Less Than Operator

The less than operator `(<)` compares the values of two numbers. If the number to the left is less than the number to the right, it returns `true`. Otherwise, it returns `false`. Like the equality operator, the less than operator converts data types while comparing.

Examples

```js
 2  < 5 // true
'3' < 7 // true
 5  < 5 // false
 3  < 2 // false
'8' < 4 // false
```

## Comparison with the Less Than Or Equal To Operator

The less than or equal to operator `(<=)` compares the values of two numbers. If the number to the left is less than or equal to the number to the right, it returns `true`. If the number on the left is greater than the number on the right, it returns `false`. Like the equality operator, the less than or equal to operator converts data types.

```js
 4  <= 5 // true
'7' <= 7 // true
 5  <= 5 // true
 3  <= 2 // false
'8' <= 4 // false
```

## Comparisons with the Logical And Operator

Sometimes you will need to test more than one thing at a time. The logical and operator `(&&)` returns `true` if and only if the operands to the left and right of it are true.

The same effect couldbe achieved by nesting an if statement inside another if:

```js
if (num > 5) {
  if (num < 10) {
    return "Yes";
  }
}
return "No";
```

will only return `Yes` if `num` is greater than `5` and less than `10`. The same logic can be written as:

```js
if (num > 5 && num < 10) {
  return "Yes";
}
return "No";
```

This approach is recommended as it allows us to avoid excessive nested `if-else` statements, leading to code that is more readable and maintainable.

## Comparisons with the Logical Or Operator

The logical or operator `(||)` returns `true` if either of the operands is `true`. Otherwise, it returns `false`.

The logical or operator is composed of two pipe symbols: `(||)`. This can typically be found between your Backspace and Enter keys.

The pattern below should look familiar from prior waypoints:

```js
if (num > 10) {
  return "No";
}
if (num < 5) {
  return "No";
}
return "Yes";
```

will return `Yes` only if `num` is between `5` and `10` (5 and 10 included). The same logic can be written as:

```js
if (num > 10 || num < 5) {
  return "No";
}
return "Yes";
```

## Introducing Else Statements

When a condition for an `if` statement is true, the block of code following it is executed. What about when that condition is false? Normally nothing would happen. With an `else` statement, an alternate block of code can be executed.

```js
if (num > 10) {
  return "Bigger than 10";
} else {
  return "10 or Less";
}
```


## Introducing Else If Statements
If you have multiple conditions that need to be addressed, you can chain `if` statements together with `else if` statements.

```js
if (num > 15) {
  return "Bigger than 15";
} else if (num < 5) {
  return "Smaller than 5";
} else {
  return "Between 5 and 15";
}
```

## Logical Order in If Else Statements

Order is important in `if`,`else if` statements.

The function is executed from top to bottom so you will want to be careful of what statement comes first.

Take these two functions as an example.

Here's the first:

```js
function foo(x) {
  if (x < 1) {
    return "Less than one";
  } else if (x < 2) {
    return "Less than two";
  } else {
    return "Greater than or equal to two";
  }
}
```

And the second just switches the order of the statements:


```js
function bar(x) {
  if (x < 2) {
    return "Less than two";
  } else if (x < 1) {
    return "Less than one";
  } else {
    return "Greater than or equal to two";
  }
}
```

While these two functions look nearly identical if we pass a number to both we get different outputs.

```js
foo(0)
bar(0)
```

`foo(0)` will return the string `Less than one`, and `bar(0)` will return the string `Less than two`.

## Chaining If Else Statements

`if/else` statements can be chained together for complex logic. Here is the pseudocode of multiple chained `if` / `else if` statements:

```js
if (condition1) {
  statement1
} else if (condition2) {
  statement2
} else if (condition3) {
  statement3
. . .
} else {
  statementN
}
```

## Additional resources
- [What is Type Coercion in JavaScript ?](https://www.geeksforgeeks.org/what-is-type-coercion-in-javascript/)<br>
- [JavaScript if, else, and else if](https://www.w3schools.com/js/js_if_else.asp)<br>
- [JavaScript Comparison and Logical Operators](https://www.w3schools.com/js/js_comparisons.asp)
