# Abstract Contracts

- Like interfaces, but can have some implemented functions.
    
- Can't be deployed directly.
    

---

## Example

```solidity
abstract contract Animal {
    function makeSound() public virtual view returns (string memory);
    function breathe() public pure returns (string memory) {
        return "Breathing";
    }
}

contract Dog is Animal {
    function makeSound() public pure override returns (string memory) {
        return "Bark";
    }
}
```
# Libraries

- Reusable code that doesn’t need to be a contract.
    
- Can be used without inheritance.
    

---

## Define a Library

```solidity
library Math {
    function add(uint a, uint b) internal pure returns (uint) {
        return a + b;
    }
}
```

---

## Use a Library

```solidity
using Math for uint;

contract Test {
    function addNumbers(uint x, uint y) public pure returns (uint) {
        return x.add(y);
    }
}
```
