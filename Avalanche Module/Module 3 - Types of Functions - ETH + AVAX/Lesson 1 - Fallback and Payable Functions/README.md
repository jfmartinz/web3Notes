# Lesson 1: Fallback and Payable Functions

## Introduction

**Introduction to Fallback Functions**

Fallback functions have following features:

- Called when a non-existent function is called on the contract
- Required to be marked external
- Has no name, no arguments, no return and cannot be marked payable
- Defined once per contract
- Throws exception if the contract receives plain Ether without data
- Limited to 2300 gas when called by another function

**Introduction to Payable Functions**

Payable functions are used whenever you want your smart contract code to accept Ether from users. So, if your function wants to accept Ether, we need to use payable functions

Payable functions have the following features:

- Allows accepting Ether from a caller
- Fails if the sender has not provided Ether
- Other functions do not accept Ether, only payable functions allow it
- Functions and addresses declared payable can receive Ether in the contract

## Using Fallback and Payable Functions

Fallback Function Example:

```js
pragma solidity ^0.5.12;

// contract with fallback function
contract fall {
  uint n;
  function set(uint value) external {
    n = value;
  }

  function() external payable {
    n = 0;
  }
}

// contract to interact with contract fall
contract Sendeth {
  function callfall(fall a) public returns (bool) {
     // calling a non-existing function
      (bool success,) = address(a).call(abi.encodeWithSignature("setter()"));
      require(success);

      // sending ether to contract fall
      address payable payableA = address(uint160(address(a)));
      return(payableA.send(2 ether));
   }
}
```

**fallback() external payable**

This is a fallback function. It is declared payable, which allows it to accept transfer value.

It is called in the following scenarios:

1. A contract receives only ether and no data
2. No function calls matched even though the account received data

With this statement `(bool success,) = address(a).call(abi.encodeWithSignature("setter()"));` we are calling a function signature in contract fall that does not exist. That’s why this call would go to the fallback function and be handled by the fallback function.


Payable Function Example:

```js
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.13;

contract Payable {
    // Payable address can receive Ether
    address payable public owner;

    // Payable constructor can receive Ether
    constructor() payable {
        owner = payable(msg.sender);
    }

    // Function to deposit Ether into this contract.
    // Call this function along with some Ether.
    // The balance of this contract will be automatically updated.
    function deposit() public payable {}

    // Call this function along with some Ether.
    // The function will throw an error since this function is not payable.
    function notPayable() public {}

   
}
```

In the above contract, we have marked a constructor and function deposit as payable, which means the contract can accept Ether either through a constructor call or a deposit function call. Whenever you call the deposit function, the amount of Ether sent to this function will be deposited into the contract.