# Topics Covered

- Arrays, Structs, and Mappings  
- Storage vs. Memory  
- Dynamic and Fixed-Size Arrays  

---

## Explanation

Reference types allow you to work with more complex data structures in Solidity, like arrays, structs, and mappings. Understanding how and where your data is stored—whether in `storage` or `memory`—is key to writing efficient and bug-free smart contracts.

---

## Example: Reference Types in Action

```solidity
pragma solidity ^0.8.20;

contract ReferenceTypes {
    struct Person {
        string name;
        uint age;
    }

    mapping(address => Person) public people;

    function addPerson(string memory _name, uint _age) public {
        people[msg.sender] = Person(_name, _age);
    }
}

