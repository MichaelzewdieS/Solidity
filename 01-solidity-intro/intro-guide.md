# Topics Covered

As part of our Solidity learning journey, we covered the following key topics:

---
## What is Blockchain?

A **blockchain** is like a digital ledger that stores data in linked blocks. Here’s the key idea:

- Data is grouped into **blocks**.
- Each block is linked to the one before it — forming a **chain**.
- Once data is added, it’s **immutable** (it can’t be changed).
- The system is **decentralized** — no single person or organization controls it.

---

### Key Features

- **Decentralization** – No single point of control.
- **Transparency** – Everyone on the network can see the data.
- **Immutability** – Data can't be changed after it's added.
- **Consensus** – Rules (algorithms) that help the network agree on valid transactions.

---

### How It Works

1. A user requests a transaction.
2. The request is shared across the network.
3. Nodes (computers) validate it using consensus algorithms (like Proof of Work).
4. If valid, it’s added to a new block.
5. That block joins the blockchain.

---
### Common Uses

- Cryptocurrency (e.g., Bitcoin, Ethereum)
- Supply chain tracking
- Digital voting systems
- Smart contracts and decentralized apps (dApps)

---

## What is Ethereum?

Ethereum is a blockchain that allows **smart contracts** — code that runs exactly as programmed with no downtime or interference.

Unlike Bitcoin (which mainly handles currency), **Ethereum is programmable**, enabling the creation of decentralized applications.

---

### Key Ethereum Terms

- **Ether (ETH)** – Native cryptocurrency used to pay for transactions.
- **Smart Contract** – Code deployed to Ethereum that executes automatically.
- **EVM (Ethereum Virtual Machine)** – Runs smart contracts.
- **Gas** – Fee paid to run operations on Ethereum.

---

## What is Solidity?

Solidity is a statically-typed programming language specifically designed for writing smart contracts on the Ethereum blockchain. It's often compared to JavaScript due to its familiar syntax, but it's tailored to run on the **Ethereum Virtual Machine (EVM)**.

We explored how Solidity serves as the backbone for decentralized applications (dApps), enabling trustless, tamper-proof logic on-chain.

---

## Setting Up the Development Environment

To build and test smart contracts effectively, we set up modern development environments using tools like:

- **[Foundry](https://book.getfoundry.sh/)** – a blazing-fast, Rust-based toolkit for Ethereum development.
- **[Hardhat](https://hardhat.org/)** – a flexible JavaScript-based framework with great support for testing and debugging.

These tools help streamline the workflow for:
- Compiling contracts
- Writing and running tests
- Deploying to local and public test networks

Setting up these environments gave us a solid foundation to experiment and iterate quickly.

---

### Solidity Basic Syntax

---

## Version Declaration

Always add this on top:

```solidity
pragma solidity ^0.8.0;
```

---

## Contract

```solidity
contract MyContract {
    // Code goes here
}
```

---

## Variables

```solidity
uint public myNumber = 10;
string public myText = "Hello";
bool public isActive = true;
```

---

## Functions

```solidity
function getNumber() public view returns (uint) {
    return myNumber;
}
```

---

## Constructor

Runs once when contract is deployed:

```solidity
constructor() {
    myNumber = 100;
}
```

---

## Comments

```solidity
// Single line

/*
Multi-line
comment
*/
```

## Writing Our First Smart Contract

With the environment in place, we jumped into writing our very first smart contract. Starting with simple examples, we began learning how to structure a contract, define functions and variables, and understand basic Solidity syntax.

This initial hands-on experience helped us grasp how smart contracts behave on the blockchain and what best practices to keep in mind.

---
## Example: Hello World in Solidity

One of the first contracts we worked on was the classic **Hello World** smart contract. It's simple, clear, and a great way to get familiar with how Solidity works.

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract HelloWorld {
    string public greet = "Hello, World!";
}



