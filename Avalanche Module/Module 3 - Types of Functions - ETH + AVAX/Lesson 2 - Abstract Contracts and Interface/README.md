# Lesson 2: Abstract Contracts and Interface

## Introduction to Abstract contracts

Like any OOPS language, Solidity provides abstract contracts. Abstract contracts are similar to abstract classes in OOPS languages such as Java and Typescript. There is no abstract term in Solidity for establishing an abstract contract. However, if a contract includes unimplemented functions, it becomes abstract.

- Instance of an abstract cannot be created
- Derived contract will implement the abstract function and use them as and when required
- Contracts that have at least one function without its implementation is abstract
- Also in the case when we don’t intend to create a contract directly we can consider the contract to be abstract
- Abstract contracts are used as base contracts so that the child contract can inherit and utilize its functions
- Any derived contract inherited from it should provide an implementation for the incomplete functions, and if the derived contract is also not implementing the incomplete functions then that derived contract will also be marked as abstract.
  
The abstract contract is an abstract (incomplete / hypothetical) design of a contract. The implementation of contract provides the implementation of the abstract function in it. Once the abstract contract is created, you need to extend it by using is keyword.

Here we have abstract contract with name “CalciAbstract” as it has function `getResult()` which is not implemented in CalciAbstract contract. This function is rather inherited and implemented in the child contract “Compute”

Abstract Contract Example

```js
pragma solidity ^0.5.0;

contract CalciAbstract {
   function getResult() public view returns(uint);
}
contract Compute is CalciAbstract {
   function getResult() public view returns(uint) {
      uint a = 1;
      uint b = 2;
      uint result = a + b;
      return result;
   }
}
```

## Introduction to Interface

Interfaces can have only unimplemented functions. Also, they are neither compiled nor deployed. They are also called pure abstract contracts

- Cannot implement any of their functions. All interface functions are implicitly virtual
- Are defined with the keyword interface
- Cannot inherit other contracts or interfaces (after solidity 6.0.0 interfaces can inherit from interfaces) but other contracts can inherit from interfaces
- Function state mutability can be pure , view , payable or default(blank)
- Fallback functions cannot be defined in an Interface
- Interface functions are implicitly "virtual"
- Cannot define a constructor
- Functions can be defined external only
- Cannot have state variables but local variables definition is allowed

## Abstract class and Inheritance Comparison

It's the same as in most other object-oriented programming languages:

- Interface only declares functions, cannot implement them
- Abstract class can declare functions (same as interface) as well as implement them.
- Both cannot be instantiated
- Both need to be implemented/inherited from other contract


## Learning Interfaces

In this example, “MyContract” contract implements the interface “ICounter”. MyContract employs both interface functions “count” and “increment” on it’s own address type variable `_counter`.

Interface Example

```js
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.13;

interface ICounter {
    function count() external view returns (uint);

    function increment() external;
}

contract MyContract {
    function incrementCounter(address _counter) external {
        ICounter(_counter).increment();
    }

    function getCount(address _counter) external view returns (uint) {
        return ICounter(_counter).count();
    }
}
```