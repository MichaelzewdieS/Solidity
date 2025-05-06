# Interfaces

- Define **what** a contract should do (not how).
    
- All functions are **external** and **no function body**.
    

---

## Example

```solidity
interface ICounter {
    function get() external view returns (uint);
    function set(uint _x) external;
}
```

## Using Interface

```solidity
contract Counter is ICounter {
    uint public value;

    function get() external view override returns (uint) {
        return value;
    }

    function set(uint _x) external override {
        value = _x;
    }
}
```
