# Lesson 1: Introduction to Solidity

## Welcome to Solidity

This module will introduce you to the developer environment that we will be using for the remainder of the course as well as teach you the fundamental building blocks necessary to write your first smart contracts in Solidity!

We will initially work with a browser-based editor called [Remix](https://remix.ethereum.org/#lang=en&optimize=false&runs=200&evmVersion=null&version=soljson-v0.8.18+commit.87f61d96.js). This is a great way to build in Solidity without having to download a bunch of files to your computer. Think of this as VS Code in the cloud.

## A Solidity Overview
### What is Solidity?

Let's get started by providing some context around Solidity. This quick 100 second [video](https://www.youtube.com/watch?v=kdvVwGrV7ec) gives a great overview of what Solidity is and how it works.

## Remix Editor - A Quick Walkthrough
### Remix Editor

We will use Remix for the rest of this lesson. This is similar to VS Code in the cloud as it is also an IDE (integrated developer environment). This will help you write and execute Solidity code quickly and easily.

If you want a sneak peek, you can check it out by [clicking here to open Remix](https://remix.ethereum.org/#lang=en&optimize=false&runs=200&evmVersion=null&version=soljson-v0.8.18+commit.87f61d96.js). In the meantime, Julian from EatTheBlocks will give us a quick introduction to answer the question, [“What even is Remix?”](https://youtu.be/vH8T3In6ZkE)<br>

## Smart Contract Layout
### Solidity Contract Layout

You've learned a lot so far. Now it's time to crack your knuckles and get into the code! 🤓

In this video, you will create your very first smart contract! We will do this work in Remix, so [click here to open Remix in your browser](https://remix.ethereum.org/#lang=en&optimize=false&runs=200&evmVersion=null&version=soljson-v0.8.18+commit.87f61d96.js).

Follow along to learn how [Solidity](https://youtu.be/g_t0Td4Kr6M) contracts are structured and create your very first contract!

## Introduction to Variables in Solidity
### Introduction

A variable is a value that can change, depending on conditions or information passed to the program.

There are numerous types of variables, such as:

- [State variables](https://www.youtube.com/watch?v=hl692-xJPUQ)<br>
- [Local variables](https://www.youtube.com/watch?v=5Gxzwn0SQDU)<br>
- [Global variables](https://www.youtube.com/watch?v=ryA86ZiSD-w)<br>

## Demonstration on Reading and Writing a State Variable

### Variable Types
So now that we know about state variables and local variables, let's dig a little deeper and learn a bit about the different types of variables you will encounter as well as their default values.

<table>
        <tr>
            <th>Types</th>
            <th>Description</th>
            <th>Default Value</th>
        </tr>
        <tr>
            <td>Signed Integer (INT)</td>
            <td>Holds both negative and positive whole numbers</td>
            <td>0</td>
        </tr>
        <tr>
            <td>Unsigned Integer (UINT)</td>
            <td>Holds only positive whole numbers</td>
            <td>0</td>
        </tr>
        <tr>
            <td>Boolean (BOOL)</td>
            <td>Holds a value of True or False</td>
            <td>false</td>
        </tr>
        <tr>
            <td>Address</td>
            <td>Holds an address but also has some built in functions (transfer & send)</td>
            <td>0x0</td>
        </tr>
        <tr>
            <td>Address Payable</td>
            <td>Holds an address but also has some built in functions (transfer & send)</td>
            <td>0x0</td>
        </tr>
        <tr>
            <td>String</td>
            <td>Holds text values (i.e. "Hello world!")</td>
            <td>Empty String ""</td>
        </tr>
    </table>


### Reading and Writing a State Variable

You have learned what variables are, so let's explore how to use them! In the code below, you can see an example of what’s called a get function and a set function. Put simply, a get function returns the value of a state variable. A set function, on the other hand, assigns a value to a state variable.

```js
// SPDX-License-Identifier: MIT
pragma solidity >=0.8.9;

contract Storage {

   uint number;

    // takes a value _number and assigns it to the state variable number
    function setNumber(uint _number) public {
          number = _number;
    }

    // returns the value of the state variable number
    function getNumber() public view {
        return number;
    }
 }
```
