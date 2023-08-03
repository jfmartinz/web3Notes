# Lesson 4: Override Extend ERC20 contracts

## Introduction

1. The ERC-20 introduces a standard for Fungible Tokens, in other words they have a property that makes each Token be exactly the same (in type and value) as another Token. 
2. For example, an ERC-20 Token acts just like ETH, meaning that 1 Token is and will always be equal to all the other Tokens.
3. Example functionalities ERC-20 provide are to:

- transfer tokens from one account to another
- get the current token balance of an account
- get the total supply of the token available on the network
- approve whether an amount of token from an account can be spent by a third-party account


## ERC20 Contracts

ERC20 standard interface has following functions and events:

**Total Supply:** The total number of tokens that will ever be issued

**Balance Of:** The account balance of a token owner's account

**Transfer:** Automatically executes transfers of a specified number of tokens to a specified address for transactions using the token

**Transfer From:** Automatically executes transfers of a specified number of tokens from a specified address using the token

**Approve:** Allows a spender to withdraw a set number of tokens from a specified account, up to a specific amount

**Allowance:** Returns a set number of tokens from a spender to the owner

**Transfer:** An event triggered when a transfer is successful (an event)

**Approval:** A log of an approved event (an event)

## ERC20 Standard interface functions

The ERC20 standard defines a set of functions to be implemented by all ERC20 tokens so as to allow integration with other contracts, wallets, or marketplaces.

```js
function totalSupply() public view returns (uint256);
function balanceOf(address tokenOwner) public view returns (uint);
function allowance(address tokenOwner, address spender)
public view returns (uint);
function transfer(address to, uint tokens) public returns (bool);
function approve(address spender, uint tokens)  public returns (bool);
function transferFrom(address from, address to, uint tokens) public returns (bool);

```

ERC20 Standard events

```js
event Approval(address indexed tokenOwner, address indexed spender,
 uint tokens);
event Transfer(address indexed from, address indexed to,
 uint tokens);
```

Overriding ERC20 contract

Override: You can change some behavior of parent contract function by using the “override” keyword and overriding the parent function in child contract. Below the example, you can see that we have overriden “decimals” function of ERC20 contract to have just 8 digits for our custom token

```js
function decimals() public view virtual override returns (uint8) {
        return 8;
    }
```
super: The super keyword will let you call functions defined in a parent contract in their original form. They can be used in child contract using “super” keyword exactly as they are defined in parent contract even if they are overriden.

```js
super.revokeRole(role, account);
```

Hooks: Hooks are just simple functions that are called before or after some action takes place. They provide a centralized point to hook into and extend the original behavior.

In the below example “_beforeTokenTransfer” is a hook that will check whether the “to” recipient is valid or not based on the criteria we define in “_validRecipient” function

```js
pragma solidity ^0.6.0;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract ERC20WithSafeTransfer is ERC20 {
    function _beforeTokenTransfer(address from, address to, uint256 amount)
        internal virtual override
    {
        super._beforeTokenTransfer(from, to, amount);

        require(_validRecipient(to), "ERC20WithSafeTransfer: invalid recipient");
    }

    function _validRecipient(address to) private view returns (bool) {
        ...
    }

    ...
}
```

## Creating Custom Tokens

Creating an ERC20 token is quite simple since templates for all different types of tokens are available on the [OpenZeppelin](https://www.openzeppelin.com/) allowing us to create tokens effortlessly.

In order to create an ERC20 token, you need the following:

- The Token’s Name
- The Token’s Symbol
- The Token’s Decimal Places
- The Total Number of Tokens in Circulation

Please set the below variables in your contract with relevant values


```java
string public constant name;
string public constant symbol;
uint8 public constant decimals;
```

```java
uint256 totalSupply_;
constructor(uint256 total) public {
   totalSupply_ = total;
   balances[msg.sender] = _totalSupply;
}
```

Let us extend the standard ERC20 contract from the Openzeppelin library to create our own custom token. You can customize your token by giving its name, symbol, decimals, etc.

```java
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.13;

import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/v4.0.0/contracts/token/ERC20/ERC20.sol";

contract Mtoken is ERC20 {
    constructor(string memory name, string memory symbol) ERC20(name, symbol) {
        // Mint 100 tokens to msg.sender
        // Similar to how
        // 1 dollar = 100 cents
        // 1 token = 1 * (10 ** decimals)
        
        _mint(msg.sender, 100 * 10**uint(decimals()));
    }

}
```