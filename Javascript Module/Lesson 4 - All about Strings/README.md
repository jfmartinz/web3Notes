# All about Strings

## Table of Contents
[Escaping Literal Quotes in Strings](#escaping-literal-quotes-in-strings)<br>
[Quoting Strings with Single Quotes](#quoting-strings-with-single-quotes)<br>
[Escape Sequences in Strings](#escape-sequences-in-strings)<br>
[Concatenating Strings with Plus Operator](#concatenating-strings-with-plus-operator)<br>
[Concatenating Strings with the Plus Equals Operator](#concatenating-strings-with-the-plus-equals-operator)<br>
[Constructing Strings with Variables](#constructing-strings-with-variables)<br>
[Appending Variables to Strings](#appending-variables-to-strings)<br>
[Find the Length of a String](#find-the-length-of-a-string)<br>
[Understand String Immutability](#understand-string-immutability)


## Escaping Literal Quotes in Strings

When you are defining a string you must start and end with a single or double quote. What happens when you need a literal quote: `"` or `'` inside of your string?

In JavaScript, you can escape a quote from considering it as an end of string quote by placing a backslash `(\)` in front of the quote.

```js
const sampleStr = "Alan said, \"Peter is learning JavaScript\"."; 
```

This signals to JavaScript that the following quote is not the end of the string, but should instead appear inside the string. So if you were to print this to the console, you would get:

```js
Alan said, "Peter is learning JavaScript".
```

## Quoting Strings with Single Quotes
String values in JavaScript may be written with single or double quotes, as long as you start and end with the same type of quote. Unlike some other programming languages, single and double quotes work the same in JavaScript.

```js
const doubleQuoteStr = "This is a string"; 
const singleQuoteStr = 'This is also a string';
```

The reason why you might want to use one type of quote over the other is if you want to use both in a string. This might happen if you want to save a conversation in a string and have the conversation in quotes. Another use for it would be saving an `<a>` tag with various attributes in quotes, all within a string.

```js
const conversation = 'Finn exclaims to Jake, "Algebraic!"';
```

However, this becomes a problem if you need to use the outermost quotes within it. Remember, a string has the same kind of quote at the beginning and end. But if you have that same quote somewhere in the middle, the string will stop early and throw an error.

```js
const goodStr = 'Jake asks Finn, "Hey, let\'s go on an adventure?"'; 
const badStr = 'Finn responds, "Let's go!"';
```

Here `badStr` will throw an error.

In the `goodStr` above, you can use both quotes safely by using the backslash \ as an escape character.

> Note: The backslash `\` should not be confused with the forward slash `/`. They do not do the same thing.

## Escape Sequences in Strings

Quotes are not the only characters that can be escaped inside a string. There are two reasons to use escaping characters:

To allow you to use characters you may not otherwise be able to type out, such as a newline. To allow you to represent multiple quotes in a string without JavaScript misinterpreting what you mean. We learned this in the previous challenge.

| Code  | Output |
| ------------- | ------------- |
|  `\'`         | single quote |
|   `\"`         | double quote  |
|  `\\`         | backlash |
|   `\n`         | new line  |
|   `\t`         | tab |
|   `\r`         | carriage return  |
|   `\b`         | word boundary  |
|   `\f`         | form feed |

> Note: that the backslash itself must be escaped in order to display as a backslash.


## Concatenating Strings with Plus Operator
In JavaScript, when the `+` operator is used with a String value, it is called the *concatenation operator*. You can build a new string out of other strings by concatenating them together.

```js
'My name is Alan,' + ' I concatenate.'
```

> Note: Watch out for spaces. Concatenation does not add spaces between concatenated strings, so you'll need to add them yourself.

Example: 


```js
const ourStr = "I come first. " + "I come second.";
```
The string `I come first. I come second`. would be displayed in the console.

## Concatenating Strings with the Plus Equals Operator

We can also use the `+=` operator to concatenate a string onto the end of an existing string variable. This can be very helpful to break a long string over several lines.

> Note: Watch out for spaces. Concatenation does not add spaces between concatenated strings, so you'll need to add them yourself.


```js
let ourStr = "I come first. ";
ourStr += "I come second.";
```

`ourStr` now has a value of the string `I come first. I come second.`.

## Constructing Strings with Variables

Sometimes you will need to build a string. By using the concatenation operator `(+)`, you can insert one or more variables into a string you're building.

```js
const ourName = "Metacrafters";
const ourStr = "Hello, our name is " + ourName + ", how are you?";
```

`ourStr` would have a value of the string `Hello, our name is Metacrafters, how are you?`

## Appending Variables to Strings

Just as we can build a string over multiple lines out of string literals, we can also append variables to a string using the plus equals `(+=)` operator.

Example: 
```js
const anAdjective = "awesome!";
let ourStr = "Metacrafters is ";
ourStr += anAdjective;
```

`ourStr` would have the value `Metacrafters is awesome`!

## Find the Length of a String

You can find the length of a `String` value by writing `.length` after the string variable or string literal.

```js
console.log("Alan Peter".length);
```

The value `10` would be displayed in the console. Note that the space character between "Alan" and "Peter" is also counted.

For example, if we created a variable `const firstName = "Ada"`, we could find out how long the string `Ada` is by using the `firstName.length` property.


## Understand String Immutability

In JavaScript, `String` values are immutable, which means that they cannot be altered once created.

For example, the following code will produce an error because the letter `B` in the string `Bob` cannot be changed to the letter `J`:

Note that this does not mean that `myStr` could not be re-assigned. The only way to change `myStr` would be to assign it with a new value, like this:

```js
let myStr = "Bob";
myStr = "Job";
```


