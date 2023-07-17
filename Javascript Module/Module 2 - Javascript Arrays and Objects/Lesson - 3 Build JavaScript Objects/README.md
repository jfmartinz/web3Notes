# Lesson 3: Build JavaScript Objects

You may have heard the term `object` before.

Objects are similar to `arrays`, except that instead of using indexes to access and modify their data, you access the data in objects through what are called `properties`.

Objects are useful for storing data in a structured way, and can represent real world objects, like a cat.

Here's a sample cat object:

```js
const cat = {
  "name": "Whiskers",
  "legs": 4,
  "tails": 1,
  "enemies": ["Water", "Dogs"]
};
```

In this example, all the properties are stored as strings, such as `name`, `legs`, and `tails`. However, you can also use numbers as properties. You can even omit the quotes for single-word string properties, as follows:

```js
const anotherObject = {
  make: "Ford",
  5: "five",
  "model": "focus"
};
```

However, if your object has any non-string properties, JavaScript will automatically typecast them as strings.

## Accessing Object Properties with Dot Notation

There are two ways to access the properties of an object: dot notation `(.)` and bracket notation `([])`, similar to an array.

Dot notation is what you use when you know the name of the property you're trying to access ahead of time.

Here is a sample of using dot notation `(.)` to read an object's property:

```js
const myObj = {
  prop1: "val1",
  prop2: "val2"
};

const prop1val = myObj.prop1;
const prop2val = myObj.prop2;
```

`prop1val` would have a value of the string `val1`, and `prop2val` would have a value of the string `val2`.

## Accessing Object Properties with Bracket Notation

The second way to access the properties of an object is bracket notation `([])`. If the property of the object you are trying to access has a space in its name, you will need to use bracket notation.

However, you can still use bracket notation on object properties without spaces.

Here is a sample of using bracket notation to read an object's property:

```js
const myObj = {
  "Space Name": "Kirk",
  "More Space": "Spock",
  "NoSpace": "USS Enterprise"
};

myObj["Space Name"];
myObj['More Space'];
myObj["NoSpace"];
```

`myObj["Space Name"]` would be the string `Kirk`, `myObj['More Space']` would be the string `Spock`, and `myObj["NoSpace"]` would be the string `USS Enterprise`.


## Updating Object Properties

After you've created a JavaScript object, you can update its properties at any time just like you would update any other variable. You can use either dot or bracket notation to update.

For example, let's look at `ourDog`:

```js
const ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};
```
Since he's a particularly happy dog, let's change his name to the string `Happy Camper`. Here's how we update his object's name property: `urDog.name = "Happy Camper"`; or `ourDog["name"] = "Happy Camper";` Now when we evaluate `ourDog.name`, instead of getting `Camper`, we'll get his new name, `Happy Camper`.

## Add New Properties to a JavaScript Object

You can add new properties to existing JavaScript objects the same way you would modify them.

Here's how we would add a `bark` property to `ourDog`:

```js
ourDog.bark = "bow-wow";
```

or

```js
ourDog["bark"] = "bow-wow";
```

Now when we evaluate `ourDog.bark`, we'll get his bark, `bow-wow`.

Example 

```js
const ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};

ourDog.bark = "bow-wow";
```

Output:

```js
  {
    name: 'Camper',
    legs: 4,
    tails: 1,
    friends: [ 'everything!' ],
    bark: 'bow-wow'
  }
```

## Delete Properties from a JavaScript Object

We can also delete properties from objects like this:

```js
delete ourDog.bark;
```

Example

```js
const ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"],
  "bark": "bow-wow"
};

delete ourDog.bark;
```

After the last line shown above, `ourDog` looks like:


```js
{
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
}
```
