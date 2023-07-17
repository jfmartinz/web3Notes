# Lesson 2: Understanding Operators

<!-- Table contents here make  -->

## Table of contents
[1. Add Two Numbers with Javascript](#add-two-numbers-with-javascript)<br>
[2. Subtract One Number from Another with JavaScript](#subtract-one-number-from-another-with-javascript)<br>
[3. Multiply Two Numbers with JavaScript](#multiply-two-numbers-with-javascript)<br>
[4. Divide One Number by Another with JavaScript](#divide-one-number-by-another-with-javascript)<br>
[5. Increment a Number with JavaScript](#increment-a-number-with-javascript)<br>
[6. Decrement a Number with JavaScript](#decrement-a-number-with-javascript)<br>
[7. Create Decimal Numbers with JavaScript](#create-decimal-numbers-with-javascript)<br>
[8. Multiply Two Decimals with JavaScript](#multiply-two-decimals-with-javascript)<br>
[9. Divide One Decimal by Another with JavaScript](#divide-one-decimal-by-another-with-javascript)<br>
[10. Finding a Remainder in JavaScript](#finding-a-remainder-in-javascript)<br>

* [Usage](#usage) 

[11. Additional resources](#additional-resources)



<!-- Table contents here make  -->

## Add Two Numbers with Javascript

`Number` is a data type in JavaScript that represents numeric data.

Now let's try to add two numbers using JavaScript.

JavaScript uses the `+ ` symbol as an addition operator when placed between two numbers.

```js
const myVar = 5 + 10;
myVar now has the value 15.
```

## Subtract One Number from Another with JavaScript

We can also subtract one number from another.

JavaScript uses the `-` symbol for subtraction.

```js
const myVar = 12 - 6;
myVar would have the value 6.
```

## Multiply Two Numbers with JavaScript

We can also multiply one number by another.

JavaScript uses the `*` symbol for multiplication of two numbers.

```js
const myVar = 13 * 13;
myVar would have the value 169.
```

## Divide One Number by Another with JavaScript

We can also divide one number by another.

JavaScript uses the `/` symbol for division.

```js
const myVar = 16 / 2;
myVar now has the value 8.
```

## Increment a Number with JavaScript

You can easily increment or add one to a variable with the `++` operator.

```js
i++;
```

is the equivalent of

```js
i = i + 1;
```
> Note: The entire line becomes `i++`;, eliminating the need for the equal sign.

## Decrement a Number with JavaScript

You can easily decrement or decrease a variable by one with the `--` operator.

```js
i--;
```

is the equivalent of

```js
i = i - 1;
```

> Note: The entire line becomes `i--`;, eliminating the need for the equal sign.


## Create Decimal Numbers with JavaScript

We can store decimal numbers in variables too. Decimal numbers are sometimes referred to as *floating point* numbers or *floats*.

> Read this short blog [JavaScript Working with Decimal Numbers](https://enlear.academy/create-decimal-numbers-with-javascript-25a170759f61)
 <br>

> Note: when you compute numbers, they are computed with finite precision. Operations using floating points may lead to different results than the desired outcome. If you are getting one of these results, open a topic on the [freeCodeCamp forum](https://forum.freecodecamp.org/).


## Multiply Two Decimals with JavaScript

In JavaScript, you can also perform calculations with decimal numbers, just like whole numbers.

Let's multiply two decimals together to get their product.

```js
var product = 2.0 * 2.5;
console.log(product) // output: 5

var product = 2.1 * 2.1;
console.log(product) // output: 4.41
```

## Divide One Decimal by Another with JavaScript

Now let's divide one decimal by another.

```js
var quotient = 5 / 2;
console.log(quotient) // output: 2.5
```

## Finding a Remainder in JavaScript

The remainder operator `%` gives the remainder of the division of two numbers.

```js
var remainder = 5 % 2;
console.log(remainder) // output: 1
```

The `%` operator in JavaScript returns the remainder of a division operation. In the code snippet, `5 % 2` evaluates to `1` because `5` divided by `2` is `2` with a remainder of `1`. 

### Usage
In mathematics, a number can be checked to be even or odd by checking the remainder of the division of the number by 2.

```js
17 % 2 = 1 (17 is Odd)
48 % 2 = 0 (48 is Even)
```
> Note: The remainder operator is sometimes incorrectly referred to as the modulus operator. It is very similar to modulus, but does not work properly with negative numbers.

## Additional resources
- Visit the W3Schools website for more information about [Javascript Operators](https://www.w3schools.com/js/js_operators.asp)<br>
- Visit the W3Schools website for more information about [JavaScript Arithmetic](https://www.w3schools.com/js/js_arithmetic.asp)