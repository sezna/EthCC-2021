
### State Variables


```solidity
pragma solidity >=0.4.0 <0.9.0;
contract SimpleStorage {
    uint storedData; // State variable
    // ...
}
```

Note:
Let's dive right in. Solidity begins its documentation by introducing us to some basic contract storage. 
This pragma is handled in our toml file, similarly to how Rust configures via Cargo.toml.


```solidity
pragma solidity >=0.4.0 <0.9.0;
contract SimpleStorage {
    uint storedData; // State variable
    // ...
}
```
```rust
contract;
let mut stored_data = 0;

fn contract_function() { 
  contract.stored_data += 1;
}
```

Note:
We have a few reasons behind this design decision. For one, remember that tweet? Have you ever prefixed a variable with something to denote that it is indeed a state variable?
We see no reason why that shouldn't be a language pattern, so, to access state variables, we use the `contract` keyword.
