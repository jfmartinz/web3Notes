# Lesson 4: Smart Contract Frontend Integration

## Integrating Smart Contract

### Application flow
1. Firstly, connect your wallet by clicking on connect wallet button.
2.  Your balance will be updated automatically after each transaction.
3. You can deposit the balance into your account by clicking the deposit button.
4. You can withdraw funds using Withdraw button.

### Set Up Locally

Checkout the code on [Github](https://github.com/MetacrafterChris/SCM-Starter)<br>

After cloning the github, you will want to do the following to get the code running on your computer.

- Inside the project directory, in the terminal type: npm i
- Open two additional terminals in your VS code
- In the second terminal type: npx hardhat node
- In the third terminal, type: npx hardhat run --network localhost scripts/deploy.js
- Back in the first terminal, type npm run dev to launch the front-end.
After this, the project will be running on your localhost. Typically at http://localhost:3000/

You can find [here](https://www.youtube.com/watch?v=e_4-Q77XJkw) the demo 