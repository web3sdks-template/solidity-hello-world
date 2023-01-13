<!-- Banner Image -->

![web3sdks solidity hardhat get started hero image](hero.png)

<h1 align='center'>Get Started with Solidity!</h1>

<p align='center'>This template showcases a basic Solidity smart contract with a full development and deployment environment set up.</p>

<br />

<b>Tools used in this template: </b>

[Solidity](https://docs.soliditylang.org/en/v0.8.14/) for the development language of our smart contract

[Hardhat](https://hardhat.org/) for the development environment (testing, debugging, etc.)

[web3sdks deploy](https://docs.web3sdks.com/web3sdks-deploy) to deploy the contract to the blockchain without using a private key

<br />

<b>Key Commands: </b>

`npx web3sdks deploy`: Deploy the smart contract

`npx hardhat test`: Run the test suite (unit tests)

<br />

<h2 align='center'>How to use this template</h2>

<h3 align='left'><b>Exploring the Smart Contract</b></h3>

Take a look at the [`Greeter.sol`](./contracts/Greeter.sol) file, you'll find a smart contract!

It's very basic, but it's a great starting point to explain how to build, test, and deploy smart contracts using Solidity.

Firstly, we declare our contract's [License](https://spdx.org/licenses/) and [Solidity Version](https://github.com/ethereum/solidity/releases).

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.4;
```

Then, we define our first `contract`, called `Greeter`!

A `contract` is a smart contract, which is a collection containing:

1. Functions
2. Data / State

That live at a specific address on the blockchain.

```solidity
contract Greeter {

}
```

We define a `variable` (data) called `greeting`, which is a `private` `string`.

This just means it is not publicly accessible by other contracts or users.

```solidity
string private greeting;
```

The `constructor` is what gets called when the contract is first created.

When we deploy the contract, we'll let the contract know what the initial value of the `greeting` variable is, by passing in a `string` as an argument and setting the value of `greeting` to that string.

```
constructor(string memory _greeting) {
    greeting = _greeting;
}
```

Since we made our `greeting` variable `private`, we can write a `view` that reads and returns the value of the `greeting` variable.

Since this is `public`, it can be accessed by other contracts or users. You'll also notice the `view` keyword, which means this function will not modify any state or data in our contract; it simply just returns some data to the caller.

```solidity
function greet() public view returns (string memory) {
    return greeting;
}
```

Finally, we have a `function` called `setGreeting`, which takes in a `string` as an argument and sets the value of `greeting` to that string.

This allows a user to change the value of `greeting` to something else.

```solidity
function setGreeting(string memory _greeting) public {
    greeting = _greeting;
}
```

<h3 align='left'><b>Deploying the smart contract</b></h3>

To deploy the contract to the blockchain, run the below script:

```bash
npx web3sdks deploy
```

This command uses [web3sdks deploy](https://docs.web3sdks.com/web3sdks-deploy) to:

1. Compile your smart contract and detect any errors
2. Upload the contract ABI to IPFS
3. Generate a URL to deploy the contract on the web3sdks dashboard.

<h3 align='left'><b>Testing the Contract</b></h3>

To run the test suite and see if your contract works as you expect, run the below script:

```bash
npx hardhat test
```

## What's Next

To build a web-app application using this smart contract, check out our next template, ["Build a web3 application using web3sdks"](https://replit.com/@web3sdks/Build-a-web3-Application-using-web3sdks)!
