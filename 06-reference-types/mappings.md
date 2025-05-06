# Mappings

- Like hash tables or dictionaries.
    
- Store key-value pairs.
    

---

## Basic Mapping

```solidity
mapping(address => uint) public balances;
```

---

## Set Value

```solidity
function setBalance(uint amount) public {
    balances[msg.sender] = amount;
}
```

---

## Get Value

```solidity
function getBalance() public view returns (uint) {
    return balances[msg.sender];
}
```

---

## Nested Mapping

```solidity
mapping(address => mapping(uint => bool)) public votes;
```
