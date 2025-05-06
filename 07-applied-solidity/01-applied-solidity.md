### Explanation

Solidity supports object-oriented programming features, such as inheritance. 

- **Modifiers**: These are used to change the behavior of functions.
- **Events**: These allow for logging actions within the contract.

### Example Code

```solidity
pragma solidity ^0.8.20;

contract Base {
    event Log(string message);

    function emitLog() public {
        emit Log("Base contract");
    }
}

contract Derived is Base {
    function emitLog() public override {
        emit Log("Derived contract");
    }
}
