# Solidity Function Modifiers

__Category: Blockchain__

Function modifiers can be used to change the behaviour of Solidity functions in a declarative way, such as checking a condition before a function executes.

For example, you might want to check that someone selling an item is the owner of it using a modifier called `onlyOwner`.

```javascript
pragma solidity >0.7.2 <0.8.13;

contract Marketplace {
    address owner;

    constructor() public {
        owner = msg.sender;
    }

    modifier onlyOwner() {
        require(
            msg.sender == owner,
            "Only the owner of an item can sell it."
        );
        _;
    }

    function sellItem(address seller, address purchaser) public view onlyOwner {
        // ...
    }
    
}
```

In the above example, the symbol `_;` is used to indicate where the function body gets inserted. The additional `view` modifier means the function can access, but not modify state.

Other function modifiers that can be used include:

* `pure` - does not allow state to be accessed or modified
* `payable` - allows the function to receive Ether

Modifiers are inheritable properties of contracts and can be overridden in derived contracts but only if they are marked `virtual`.
