# Function & Variable Visibility

Controls who can access functions or variables.

---

## 1. **public**

- Can be called from anywhere.
    

```solidity
uint public count;

function getCount() public view returns (uint) {
    return count;
}
```

---

## 2. **private**

- Only inside the same contract.
    

```solidity
uint private secret;

function setSecret(uint _x) private {
    secret = _x;
}
```

---

## 3. **internal**

- Only inside this contract and children (inherited contracts).
    

```solidity
uint internal value;
```

---

## 4. **external**

- Only callable from outside the contract.
    

```solidity
function externalFunc() external {
    // can't call this inside the contract
}
```
# State Variables

- Stored on the blockchain.
    
- Keep data between function calls.
    

---

## Declare

```solidity
string public name = "Danny";
uint public count = 0;
```

---

## Access & Change

```solidity
function updateCount() public {
    count += 1;
}
```

---

## Types

- You can use any type: `uint`, `bool`, `address`, `mapping`, `struct`, etc.
    

---

## Storage Cost

- State variables cost **gas**.
    
- Use them wisely!

 
# Events

- Let smart contracts **communicate with frontend** (e.g., React).
    
- Saved in transaction logs.
    

---

## Define an Event

```solidity
event Sent(address from, address to, uint amount);
```

---

## Emit an Event

```solidity
function send(address _to, uint _amount) public {
    emit Sent(msg.sender, _to, _amount);
}
```

---

## Use in Frontend

- You can **listen for events** using web3.js or ethers.js in a UI.

# Error Handling

Make sure your contract behaves safely when things go wrong.

---

## require()

Checks conditions before running.

```solidity
require(msg.sender == owner, "Not the owner");
```

---

## revert()

Manual error.

```solidity
if (x < 1) {
    revert("x is too small");
}
```

---

## assert()

Used to check for bugs or internal errors.

```solidity
assert(balance >= 0);
```

---

## Custom Errors (Gas Efficient)

```solidity
error NotOwner();

function onlyOwner() public {
    if (msg.sender != owner) {
        revert NotOwner();
    }
}
```
