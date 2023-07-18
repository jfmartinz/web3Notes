# Lesson 2: JavaScript Loops

## Iterate with JavaScript While Loops

You can run the same code multiple times by using a loop.

The first type of loop we will learn is called a `while` loop because it runs while a specified condition is true and stops once that condition is no longer true.

```js
const ourArray = [];
let i = 0;

while (i < 5) {
  ourArray.push(i);
  i++;
}
```

In the code example above, the `while` loop will execute 5 times and append the numbers 0 through 4 to `ourArray`.

## Iterate with JavaScript For Loops

The most common type of JavaScript loop is called a `for` loop because it runs for a specific number of times.

`for` loops are declared with three optional expressions separated by semicolons:

`for (a; b; c)`, where `a` is the initialization statement, `b` is the condition statement, and `c` is the final expression.

The initialization statement is executed one time only before the loop starts. It is typically used to define and setup your loop variable.

The condition statement is evaluated at the beginning of every loop iteration and will continue as long as it evaluates to `true`. When the condition is `false` at the start of the iteration, the loop will stop executing. This means if the condition starts as false, your loop will never execute.

The final expression is executed at the end of each loop iteration, prior to the next condition check and is usually used to increment or decrement your loop counter.

In the following example we initialize with `i = 0` and iterate while our condition `i < 5` is true. We'll increment `i` by 1 in each loop iteration with `i++` as our final expression.

```js
const ourArray = [];

for (let i = 0; i < 5; i++) {
  ourArray.push(i);
}
```

`ourArray` will now have the value `[0, 1, 2, 3, 4]`.


## Iterate Odd Numbers With a For Loop

'for' loops don't have to iterate one at a time. By changing our `final-expression`, we can count by even numbers.

We'll start at `i = 0` and loop while `i < 10`. We'll increment `i` by 2 each loop with `i += 2`.

`ourArray` will now contain `[0, 2, 4, 6, 8]`. Let's change our `initialization` so we can count by odd numbers.

## Count Backwards With a For Loop

A `for` loop can also count backwards, so long as we can define the right conditions.

In order to decrement by two each iteration, we'll need to change our initialization, condition, and final expression.

We'll start at `i = 10` and loop while `i > 0`. We'll decrement `i` by 2 each loop with `i -= 2`.

`ourArray` will now contain `[10, 8, 6, 4, 2]`.

## Iterate Through an Array with a For Loop

A common task in JavaScript is to iterate through the contents of an array. One way to do that is with a `for` loop. This code will output each element of the array `arr` to the console:

```js
const arr = [10, 9, 8, 7, 6];

for (let i = 0; i < arr.length; i++) {
   console.log(arr[i]);
}
```

Remember that arrays have zero-based indexing, which means the last index of the array is `length - 1`. Our condition for this loop is `i < arr.length`, which stops the loop when `i` is equal to `length`. In this case the last iteration is `i === 4` i.e. when `i` becomes equal to `arr.length - 1` and outputs `6` to the console. Then `i` increases to `5`, and the loop terminates because `i < arr.length` is `false`.

## Nesting For Loops

If you have a multi-dimensional array, you can use the same logic as the prior waypoint to loop through both the array and any sub-arrays. Here is an example:

```js
const arr = [
  [1, 2], [3, 4], [5, 6]
];

for (let i = 0; i < arr.length; i++) {
  for (let j = 0; j < arr[i].length; j++) {
    console.log(arr[i][j]);
  }
}
```

This outputs each sub-element in `arr` one at a time. Note that for the inner loop, we are checking the `.length` of `arr[i]`, since `arr[i]` is itself an array.

## Iterate with JavaScript Do...While Loops

The next type of loop you will learn is called a `do...while` loop. It is called a `do...while` loop because it will first `do` one pass of the code inside the loop no matter what, and then continue to run the loop `while` the specified condition evaluates to `true`.

```js
const ourArray = [];
let i = 0;

do {
  ourArray.push(i);
  i++;
} while (i < 5);
```

The example above behaves similarly to other types of loops, and the resulting array will look like `[0, 1, 2, 3, 4]`. However, what makes the `do...while` different from other loops is how it behaves when the condition fails on the first check. Let's see this in action. Here is a regular `while` loop that will run the code in the loop as long as `i < 5`:

```js
const ourArray = []; 
let i = 5;

while (i < 5) {
  ourArray.push(i);
  i++;
}
```

In this example, we initialize the value of `ourArray` to an empty array and the value of `i` to 5. When we execute the `while` loop, the condition evaluates to `false` because `i` is not less than 5, so we do not execute the code inside the loop. The result is that `ourArray` will end up with no values added to it, and it will still look like `[]` when all of the code in the example above has completed running. Now, take a look at a `do...while` loop:

```js
const ourArray = []; 
let i = 5;

do {
  ourArray.push(i);
  i++;
} while (i < 5);
```

In this case, we initialize the value of `i` to 5, just like we did with the `while` loop. When we get to the next line, there is no condition to evaluate, so we go to the code inside the curly braces and execute it. We will add a single element to the array and then increment `i` before we get to the condition check. When we finally evaluate the condition `i < 5` on the last line, we see that `i` is now 6, which fails the conditional check, so we exit the loop and are done. At the end of the above example, the value of `ourArray` is `[5]`. Essentially, a `do...while` loop ensures that the code inside the loop will run at least once.

## Use the parseInt Function

The `parseInt()` function parses a string and returns an integer. Here's an example:

```js
const a = parseInt("007");
```

The above function converts the string `007` to the integer `7`. If the first character in the string can't be converted into a number, then it returns `NaN`.





