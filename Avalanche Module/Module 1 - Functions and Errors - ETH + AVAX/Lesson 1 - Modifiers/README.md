# Lesson 1: Modifiers

## Introduction

A modifier is a special kind of function that contains certain user-defined conditions. When a modifier is used in a function definition, all the conditions inside the modifier are checked, and if all the conditions are satisfied or are equal to true, only then does the function execution move forward.

## About Modifiers

The modifier is a special kind of function that contains certain user-defined conditions.

- When a modifier is used in a function definition, all the conditions inside the modifier are checked, and if all the conditions are satisfied or are true, only then the function execution moves forward
- A modifier acts as a pre-check to the function execution
- It always ends with  `'_;'` before the closing parenthesis
- `'_;'` **is replaced with the actual function body when the modifier is used**


## Using Modifiers
The contract below demonstrates how to use a modifier:

```js
contract Owner {
   modifier onlyOwner {
      require(msg.sender == owner);
      _;
   }
   modifier costs(uint price) {
      if (msg.value >= price) {
         _;
      }
   }
}
```

In the example above, the contract has two modifiers: `“onlyOwner”` and `“costs”`.

The first modifier checks that the `msg.sender` is the owner of the contract, and the second modifier checks that the `msg.value` is greater than or equal to a certain price. 

Both of these modifiers can be used on any function in the contract. 


Another example:

```js
pragma solidity >=0.7.0 <0.9.0; //solidity version
contract greatestnum{

    uint a;
    uint b;
    uint c;
    uint d;
    address owner;

    constructor(){
        owner = msg.sender;
    }

    modifier onlyOwner { 
        require (owner == msg.sender, "only owner can access");
        _;
    }

    function set (uint _a, uint _b, uint _c, uint _d) public onlyOwner{
        a = _a;
        b = _b;
        c = _c;
        d = _d;
    }

    function get() public view onlyOwner returns(uint){
        if ((a > b) && (a > c) && (a > d)){
        return(a);
        }
        else if ((b >c ) && (b > d) && (b > a)){
            return(b);
        }
        else if ((c > d) && (c > a) && (c > b)){
            return(c);
        }
        else {
            return(d);
        }
    }
}
```

### Modifier without parameters
Just like functions, we can have modifiers that don’t pass any parameters or arguments. Below is an example:

```js
modifier onlyOwner {
      require(msg.sender == owner);
      _;
}
```

### Modifier with parameters
We can have modifiers that can pass any parameters or arguments. Below is an example:

```js
 modifier costs(uint price) {
      if (msg.value >= price) {
         _;
      }
 }
```

> Best Practices: Place modifier code after state variable declarations and ideally before function declarations for more legible code.