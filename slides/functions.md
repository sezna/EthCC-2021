### Functions


```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity >0.7.0 <0.9.0;

contract SimpleAuction {
    function bid() public payable { // Function
        // ...
    }
}

// Helper function defined outside of a contract
function helper(uint x) pure returns (uint) {
    return x * 2;
}

```
Note:
A function in Solidity looks like this. Let's take a look at what this is doing -- we are creating an auction contract with some bid method that is payable. 
We also have a helper pure function which multiplies a number by 2.


```rust
contract;

abi SimpleAuction {
  fn bid();
}

impl SimpleAuction for Contract {
  fn bid() {
    ..
  }
}

fn helper(x: u64) -> u64 {
  x * 2
}

```

Note:
Now, let's take a look at the equivalent Sway code.
There are three examples of functions here. Let's take a look at the function called `helper`. (point out: rust syntax, type annotation, return type, implicit return)

We have replaced the Solidity inheritence/constructor based system with a trait based system.
While in this code snippet, this results in a few more lines of boilerplate for Sway, in general, this is not the case. Less boilerplate and a more predictable system. 
The `abi` keyword denotes what is essentially a trait -- a type class for you Haskellers, an interface for you Java beans. This defines an interface that can be imported 
into other Sway programs to either implement contracts with the same interface, or, to interact with contracts. But we will get to that in a bit. For now, just know that the `abi` 
keyword defines a special kind of trait, typeclass, what-have-you, that can be implemented on contracts themselves.

Functions are pure by default.


```solidity
contract Purchase {
    address public seller;

    modifier onlySeller() { // Modifier
        require(
          msg.sender == seller,
          "Only seller can call this."
        );
        _;
    }

    // Modifier usage
    function abort() public view onlySeller { 
        // ...
    }
}
```

Note:
cover removal of modifiers, assert! macro instead of require


```rust
contract;

let seller: Address = Address(
  0xDEADBEEF...
);

abi Purchase {
  view fn abort_inner();
} 

impl Purchase for Contract {
  view fn abort() {
    assert_eq!(context.caller_id, seller);
    abort_inner()
  }
}
```

Note:
view functions, constant values, deploy-time values, macros, assert_eq, modifiers can be solved with 
function composition and have nothing to do with the blockchain therefore we didn't keep them
