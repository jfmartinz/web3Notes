# Lesson 3 - Compound Assignments

## Table of Contents

[1. Compound Assignment With Augmented Addition](#compound-assignment-with-augmented-addition)<br>
[2. Compound Assignment With Augmented Subtraction](#compound-assignment-with-augmented-subtraction)<br>
[3. Compound Assignment With Augmented Multiplication](#compound-assignment-with-augmented-multiplication)<br>
[4. Compound Assignment With Augmented Division](#compound-assignment-with-augmented-division)<br>
[5. Additional resource](#additional-resource)

## Compound Assignment With Augmented Addition

In programming, it is common to use assignments to modify the contents of a variable. Remember that everything to the right of the equals sign is evaluated first, so we can say:

```js
myVar = myVar + 5;
```
to add `5` to `myVar`. Since this is such a common pattern, there are operators which do both a mathematical operation and assignment in one step.

One such operator is the `+=` operator.

```js
let myVar = 1;
myVar += 5;
console.log(myVar);
```

`6` would be displayed in the console.

## Compound Assignment With Augmented Subtraction

Like the `+=` operator, `-=` subtracts a number from a variable.

```js
myVar = myVar - 5;
```

will subtract `5` from `myVar`. This can be rewritten as:

```js
myVar -= 5;
```

## Compound Assignment With Augmented Multiplication

The `*=` operator multiplies a variable by a number.

```js
myVar = myVar * 5;
```

will multiply `myVar` by `5`. This can be rewritten as:

```js
myVar *= 5;
```

## Compound Assignment With Augmented Division

The `/=` operator divides a variable by another number.

```js
myVar = myVar / 5;
```

will divide `myVar` by `5`. This can be rewritten as:

```js
myVar /= 5;
```

## Additional resource
 - Visit the W3Schools website for more information about [JavaScript Assignment](https://www.w3schools.com/js/js_assignment.asp).