# How to Deploy a Smart Contract

I used **Hardhat** to deploy a contract. Here’s how I did it step by step:

---

### 1. Make Your Contract

```solidity
// contracts/Hello.sol
pragma solidity ^0.8.0;

contract Hello {
    string public greet = "Hi!";
}
```

---

### 2. Write a Deploy Script

```js
// scripts/deploy.js
async function main() {
    const Hello = await ethers.getContractFactory("Hello");
    const hello = await Hello.deploy();
    await hello.deployed();
    console.log("Contract deployed to:", hello.address);
}
main();
```

---

### 3. Compile the Contract

```bash
npx hardhat compile
```

---

### 4. Run it on Local Network

```bash
npx hardhat run scripts/deploy.js --network localhost
```

---

### 5. (Optional) Deploy to a Testnet
# Talking to Deployed Contracts

---

### With JavaScript (ethers.js)

```js
const Hello = await ethers.getContractAt("Hello", "0x...address");
const greeting = await Hello.greet();
console.log(greeting);
```

---

### Changing a Value

```js
await Hello.setGreeting("Yo!");
```

---

### With Remix (Easier Way)

1. Paste contract code into Remix.
    
2. Compile it.
    
3. Use the “Deploy and Run” tab.
    
4. Paste contract address and ABI to interact with a deployed contract.

# Some Basic Security Tips

---

### 1. Use `require` to check stuff

```solidity
require(msg.sender == owner, "You can't do this");
```

---

### 2. Stop Reentrancy (Attack)

```solidity
bool locked;

modifier noReentry() {
    require(!locked, "Wait!");
    locked = true;
    _;
    locked = false;
}
```

---

### 3. Add Limits

Don’t let users send crazy values.

```solidity
require(amount < 100, "Too high!");
```

---

### 4. Use a `constructor` to set things once

```solidity
constructor() {
    owner = msg.sender;
}
```

# Tips to follow

---

- Always check user input with `require()`  
- Never use `tx.origin`, just use `msg.sender`
- No need for SafeMath in Solidity 0.8+  
- Use `constant` and `immutable` to save gas 
- If upgrading contracts, use proxies (a bit advanced)
