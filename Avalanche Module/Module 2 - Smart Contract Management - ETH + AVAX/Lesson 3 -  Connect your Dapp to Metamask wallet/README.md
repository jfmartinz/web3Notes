# Lesson 3: Connect your Dapp to Metamask wallet

## Introduction

Most of the web3 users interact with dapps through wallet accounts instead of user email and passwords. So, as a web3 developer it’s important to learn how to develop and connect your dapps with Metamask wallet. Then users can login to your dapps through their Metamask accounts.

## About Metamask, Web3.js, and React.js

We are going use Metamask, web3.js and react.js in this lesson so let’s first understand them so we can effectively use them for building web3 applications.

## Metamask

- MetaMask is a cryptocurrency wallet that enables users to store Ether and other ERC-20 tokens along with their public and private keys, keeping your cryptocurrency safe and accessible.
- The wallet can also be used to interact with decentralized applications (dapps)
- It also allows you to send, receive, and spend cryptocurrencies like Ethereum and Tokens.
- Apart from Ethereum it also supports BSC (Binance Smart Chain), Polygon, Avalanche, IOTEX and Fantom
- It is developed by ConsenSys Software Inc. - a blockchain software company founded in 2016 focusing on Ethereum-based tools and infrastructure

## Web3.js

**web3.js** is a collection of Javascript libraries that allow you to interact with a local or remote Ethereum node using HTTP, IPC, or WebSocket. You can imagine web3.js as a script that helps you connect your smart contracts and frontend of an application together.

## React.js

**React** or **React.js** is a free and open-source front-end JavaScript library for building user interfaces based on UI components. You can build UI in react.js just like html. React.js can be used in the development of single-page, mobile, or server-rendered applications. Blockchain developers prefer to use reactjs to build frontend for dapps and smart contracts.

## Getting Started with Metamask

Below are the main functions that allow us to connect to Metamask:

- **connectWalletHandler** - To connect to the Metamask wallet
- **accountChangedHandler** - Changing account from Metamask causes this function work
- **getAccountBalance** - Get the Balance of the token/coin in your metamask wallet
- **chainChangedHandler** - Changing the blockchain network in the Metamask causes this function to work

## Set Up Locally

Check out the [Github Code](https://github.com/blockchaintrainer/Module2_Chapter3)<br>

Run below commands to install and run the script

```js
$ npm install
$ npm start

navigate browser to localhost:3000
```


```js
import React, {useState} from 'react'
import {ethers} from 'ethers'
import './WalletCard.css'

const WalletCard = () => {

	const [errorMessage, setErrorMessage] = useState(null);
	const [defaultAccount, setDefaultAccount] = useState(null);
	const [userBalance, setUserBalance] = useState(null);
	const [connButtonText, setConnButtonText] = useState('Connect Wallet');

	const connectWalletHandler = () => {
		if (window.ethereum && window.ethereum.isMetaMask) {
			console.log('MetaMask Here!');

			window.ethereum.request({ method: 'eth_requestAccounts'})
			.then(result => {
				accountChangedHandler(result[0]);
				setConnButtonText('Wallet Connected');
				getAccountBalance(result[0]);
			})
			.catch(error => {
				setErrorMessage(error.message);
			
			});

		} else {
			console.log('Need to install MetaMask');
			setErrorMessage('Please install MetaMask browser extension to interact');
		}
	}

	// update account, will cause component re-render
	const accountChangedHandler = (newAccount) => {
		setDefaultAccount(newAccount);
		getAccountBalance(newAccount.toString());
	}

	const getAccountBalance = (account) => {
		window.ethereum.request({method: 'eth_getBalance', params: [account, 'latest']})
		.then(balance => {
			setUserBalance(ethers.utils.formatEther(balance));
		})
		.catch(error => {
			setErrorMessage(error.message);
		});
	};

	const chainChangedHandler = () => {
		// reload the page to avoid any errors with chain change mid use of application
		window.location.reload();
	}


	// listen for account changes
	window.ethereum.on('accountsChanged', accountChangedHandler);

	window.ethereum.on('chainChanged', chainChangedHandler);
	
	return (
		<div className='walletCard'>
		<h4> {"Connect Metamask"} </h4>
			<button onClick={connectWalletHandler}>{connButtonText}</button>
			<div className='accountDisplay'>
				<h3>Address: {defaultAccount}</h3>
			</div>
			<div className='balanceDisplay'>
				<h3>Balance: {userBalance}</h3>
			</div>
			{errorMessage}
		</div>
	);
}

export default WalletCard;
```

Output:

<img src="output.png" alt="React Output">
