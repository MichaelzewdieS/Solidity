# Value Types in Solidity

These types hold their own data directly.

---

## 1. **uint / int**

- Whole numbers.
    
- `uint` = unsigned (only positive).
    
- `int` = signed (positive + negative).
    

```solidity
uint256 x = 100;
int256 y = -50;
```

---

## 2. **bool**

- True or false.
    

```solidity
bool isActive = true;
```

---

## 3. **address**

- Holds Ethereum wallet or contract address.
    

```solidity
address owner = msg.sender;
```

---

## 4. **bytes1 to bytes32**

- Fixed-size byte arrays.
    

```solidity
bytes32 data = "hello";
```

---

## 5. **enum**

- User-defined list of options.
    

```solidity
enum Status { Pending, Shipped, Delivered }

Status public currentStatus = Status.Pending;
```
