## **Array**

### Fixed-size:

```solidity
uint[3] numbers = [1, 2, 3];
```

### Dynamic:

```solidity
uint[] public list;

function add(uint x) public {
    list.push(x);
}
```
