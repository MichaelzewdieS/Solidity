## Solidity: Functions, Modifiers, and Control Flow

###  Function Types in Solidity

Functions in Solidity come in different flavors depending on what they can do and where they can be called from. Understanding the distinctions is critical for writing secure and efficient contracts.

---

#### View Functions

- View functions are used to **read state variables** from the blockchain without modifying them.
- Since they don’t alter data, they don’t cost gas when called externally.

```solidity
function getUserAge() public view returns (uint256) {
    return userAge;
}
```

---

#### Pure Functions

- These functions **do not access** or modify the contract's storage.
- Ideal for performing **stateless computations**.

```solidity
function computeSquare(uint256 number) public pure returns (uint256) {
    return number * number;
}
```

---

#### Payable Functions

- Marked with the `payable` keyword, these functions **allow the contract to receive Ether**.
- They are essential for creating donation, crowdfunding, or sale contracts.

```solidity
function fundProject() external payable {
    contributions[msg.sender] += msg.value;
}
```

---

#### Internal Functions

- **Accessible only** from within the contract itself or from derived contracts.
- Commonly used to abstract repeated logic inside a contract’s architecture.

```solidity
function applyFee(uint256 amount) internal returns (uint256) {
    return amount - (amount / 100);
}
```

---

#### External Functions

- Can only be called **from outside the contract**, not from within other functions in the same contract.
- Useful for interfaces and API-like contract interactions.

```solidity
function registerUser(string calldata name) external {
    users[msg.sender] = name;
}
```

---

#### Private Functions

- **Restricted to the contract** in which they are defined.
- Not visible to derived contracts.

```solidity
function resetState() private {
    internalCounter = 0;
}
```

---

###  Function Modifiers

Modifiers provide a clean way to enforce conditions or access rules on functions without repeating code.

---

#### Defining a Modifier

Modifiers wrap around function execution. They can perform pre-checks before the actual function runs.

```solidity
modifier onlyManager() {
    require(msg.sender == manager, "Access restricted to manager");
    _;
}
```

- The `_` indicates where the body of the function will be inserted during execution.

---

#### Applying a Modifier

Use modifiers to enforce restrictions like ownership, timing, or conditions.

```solidity
function releaseFunds() public onlyManager {
    payable(recipient).transfer(address(this).balance);
}
```

---

#### Common Modifier Patterns

- `onlyOwner` — Limits function access to the contract owner.
- `nonReentrant` — Prevents nested (re-entrant) calls, protecting against a common exploit.
- `whenNotPaused` — Ensures the contract is not paused during execution.

---

###  Control Flow in Solidity

Solidity supports traditional programming control structures, but with attention to gas costs and on-chain behavior.

---

#### Conditional Statements (`if / else`)

Used to branch logic based on conditions.

```solidity
if (bidAmount > highestBid) {
    highestBid = bidAmount;
} else {
    revert("Bid too low");
}
```

---

#### `require`

- Terminates execution if the condition fails.
- Used for input validation and access control.

```solidity
require(balance[msg.sender] >= amount, "Insufficient balance");
```

---

#### `revert`

- Aborts execution and reverts any state changes made during the transaction.
- Often used with custom error messages.

```solidity
if (userVotes[msg.sender] == true) {
    revert("Already voted");
}
```

---

#### `assert`

- Intended for checking **internal invariants**.
- Should not be used for user-facing conditions.

```solidity
assert(totalSupply <= maxSupply);
```

---

###  Loops in Solidity

Loops are available in Solidity but should be used sparingly due to gas limitations.

---

#### For Loops

```solidity
for (uint256 i = 0; i < participantList.length; i++) {
    distributeReward(participantList[i]);
}
```

---

#### While Loops

```solidity
uint256 index = 0;
while (index < 3) {
    emit Log(index);
    index++;
}
```

---

#### Best Practices with Loops

- Avoid writing **unbounded loops**, especially in public/external functions.
- Always ensure that the loop has a clear and predictable termination to prevent gas exhaustion.

---

##  Summary

In this section, we've covered the foundational mechanics of Solidity functions, from various function types to critical control and access structures like modifiers and loops. Mastering these elements is key to writing robust, secure smart contracts that behave as expected on-chain.
