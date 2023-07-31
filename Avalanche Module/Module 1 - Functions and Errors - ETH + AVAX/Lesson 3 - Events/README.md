# Lesson 3: Events

## Introduction

**Event** is an inheritable member of a contract. An **event** is emitted, it stores the arguments passed in transaction logs. These logs are stored on blockchain and are accessible using address of the contract till the contract is present on the blockchain. An event generated is not accessible from within contracts, not even the one which have created and emitted them.

Each transaction has an attached receipt, which contains zero or more log entries. The log entries represent the result of the **events** having been fired from a smart contract. An event in Solidity is defined as:

`event <event_name> (<event_parameters>)`

After you have defined an event, you can call it or trigger it from inside any function you wish. You can call an event using the emit keyword in the following manner:

`emit <event_name> (<event_arguments>)`



## Using Events

An event can be declared using event keyword.

```js
//Declare an Event
event Deposit(address indexed _from, bytes32 indexed _id, uint _value);

//Emit an event
emit Deposit(msg.sender, _id, msg.value);
```

Example:

```js
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.13;

contract Event {
    // Event declaration
    // Up to 3 parameters can be indexed.
    // Indexed parameters helps you filter the logs by the indexed parameter
    event messLog(address indexed sender, string message);
    event messLog2();

    function test() public {
        emit messLog(msg.sender, "Hello World!");
        emit messLog(msg.sender, "Hello EVM!");
        emit messLog2();
    }
}
```

## Indexing Events using Indexed Keyword

DApps, or anything connected to the Ethereum JSON-RPC API, can listen to these events and act accordingly. An event can be indexed, so that the event history is searchable later.

You can use the **indexed** keyword before the parameter when you want an event to be indexed. This is useful in case someone wants to search the history and filter the events on a particular index.

These indexed parameters are stored inside the logs inside a special kind of data structure called 'topics'.

```js
event Transfer(address indexed from, address indexed to, uint amount);
```

> Note: We can add up to 3 indexes in an event

Deposit Event Example:

```js
contract Test {
   event Deposit(address indexed _from, bytes32 indexed _id, uint _value);
   function deposit(bytes32 _id) public payable {      
      emit Deposit(msg.sender, _id, msg.value);
   }
}
```

## Listening to Solidity Events in JavaScript

You can capture the events in your JavaScript code by referring to the web3 object of events using the web3.js library of JavaScript

```js
let contract_abi = abi_json _code_during_contract_compilation;
let EventTest = web3.eth.contract(contract_abi);
let EventTestContract = ClientReceipt.at("0x98...");

EventTestContract.transfer(function(err, data) {
   if (!err)
   console.log(data);
});
```

Smart contract reference is established through ABI code and it’s address. We are setting up the `contract_abi` variable to capture ABI code.

We also connect to the contract through its address reference at ClientReceipt.at in the `EventTestContract` variable. We can then access the transfer event through the `EventTestContract` variable