# Inheritance in Solidity

- Inheritance allows one contract to inherit the functionality of another.
- It promotes code reuse, reduces redundancy, and improves contract organization.

---

## Simple Inheritance

```solidity
contract Animal {
    function sound() public pure returns (string memory) {
        return "Some sound";
    }
}

contract Dog is Animal {
    // Inherits sound()
}
```
## Overriding Functions
```solidity
contract Animal {
    function makeSound() public virtual pure returns (string memory) {
        return "Some generic sound";
    }
}

contract Dog is Animal {
    function makeSound() public override pure returns (string memory) {
        return "Bark!";
    }
}
```


