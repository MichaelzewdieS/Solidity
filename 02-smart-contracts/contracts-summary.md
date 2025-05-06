## Topics Covered

In this section of our Solidity journey, we explored the following foundational concepts:

---

### Understanding Smart Contracts

Smart contracts are **self-executing pieces of code** where the terms of agreement are embedded directly into logic. They live at specific addresses on the **Ethereum blockchain** and execute automatically when called — no middlemen, no funny business.

---

### State Variables and Functions

- **State variables** are used to store data permanently on the blockchain — kind of like global variables with commitment issues (but in a good way).
- **Functions** define the behavior of a contract — what it can do and how it reacts when someone interacts with it.

---

### Visibility and Data Locations

- **Visibility** (like `public`, `private`, `internal`, `external`) determines who can access a variable or function.
- **Data locations** (`storage`, `memory`, `calldata`) define *where* the data lives and *how* it's managed when passed around.
## Example: Counter Contract

This example, it's a simple **Counter** contract that tracks a count and allows it to be incremented.

### Code:

```solidity
pragma solidity ^0.8.20;

contract Counter {
    uint public count = 0;

    function increment() public {
        count += 1;
    }
}



