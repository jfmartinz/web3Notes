# Lesson 2: Functions

## Introduction

- A function is a group of reusable code that can be called anywhere in your program
- This eliminates the need to write the same code again and again
- It helps programmers write modular (smaller units) code and separate bigger problems into separate parts


## Functions on the Blockchain

Every operation on the blockchain is a transaction. Transactions involve calling functions that execute code to modify the state of a contract. That means calling functions creates a transaction on the blockchain. Functions can read or write the state of a smart contract.

The function involves two parts:

**Declare functions:** Declare a function and it’s body will state how the function will behave in runtime
**Calling functions:** Call a function by passing optional parameters and actually executing them

## Function Syntax

```js
function <function_name>(<arguments to the function>) <visibility_type> <function_type> <modifiers> returns(<return data type>)
```

Syntax Explanation:

- Function is a keyword in Solidity
- Function-name: Name of the function and valid identifier in Solidity
- visibility_type: How the function is visible to the caller
- Modifiers: Declare the function to change the behavior of contract data. They are optional
- Returns: Explains the type of data returned to the caller (optional).

## Function Visibility
Visibility to a function specifies how the function is visible to the caller internally or externally.

### Public

- Visible from internal and external contracts
- Can be called inside a contract or outside a contract
- Default is public
- Visible to the public, so has security concerns

### Private

- Private functions are visible inside the same contract
- Can be called inside a contract
- Not able to call from an outside contract

### Internal

- Similar to private functions and visible to contract hierarchy
- Can be called inside a contract and contracts that inherit from it

### External

- External functions are visible to public functions
- Can only be called outside the contract

## Function Types
There are four types of functions in Solidity:

1. **View:** The function only reads from the smart contract and will not perform any kind of writing operations. A 'view' function does not consume any amount of gas.

2. **Pure:** The function will neither read nor write anything on the smart contract. They are also called helper functions. For example, you can write any mathematical calculations for your smart contract that neither read data from the blockchain nor writes to the blockchain.

3. **Payable:** These functions have the capability to accept Ether as an input. If you are sending ethers to smart contracts, then you need to make sure that it is only to those functions that are defined as payable.

4. **Fallback:** If an incoming transaction call does not match any of the functions defined in a smart contract, then the call will be directed towards the Fallback function. In other words, if there is a call for a function that doesn't exist, then the call will fall to the Fallback function. The fallback function doesn’t have any arguments and they don’t return any values.


## Using Functions
Here's an example of pure and view functions:

```js
pragma solidity ^0.8.13;

contract ViewAndPure {
    uint public x = 5;

    // Promise not to modify the state.
    function addToX(uint y) public view returns (uint) {
        return x + y;
    }

    // Promise not to modify or read from the state.
    function add(uint i, uint j) public pure returns (uint) {
        return i + j;
    }
}
```


```js
pragma solidity ^0.8.15; 

contract payableContract {

    address payable public owner;

    constructor() {
        owner = payable(msg.sender);
    }

    function deposit () external payable {}

    function getBalance () external view returns (uint) {
        return address(this).balance;
    }
    
}
```