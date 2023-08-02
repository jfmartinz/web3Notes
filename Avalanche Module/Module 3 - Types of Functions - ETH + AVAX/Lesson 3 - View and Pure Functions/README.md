# Lesson 3: View and Pure Functions

## Introduction

**Introduction to view functions**

View function has the following features:

- Display the data.
- Do not modify the state variable,
- Are good for reading data operations
- Only reads but doesn’t modify the variables of the state.

**Introduction to pure functions**

Pure functions have the following features:

- Do not access data from the blockchain
- Do not allow to read or write operations
- No access to state data or transaction data
- Return type based on the data from a function


## Learning View and Pure Functions

View and Pure Example:

In the below example, “sumX” is a view function and it can read values from the blockchain whereas the function “sumI” is a pure function which is just used for smart contract level calculations and it neither reads nor writes data to the blockchain

```js
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.13;

contract ViewPure {
    uint public x = 1;

    // Promise not to modify the state.
    function sumX(uint y) public view returns (uint) {
        return x + y;
    }

    // Promise not to modify or read from the state.
    function sumI(uint i, uint j) public pure returns (uint) {
        return i + j;
    }
}
```