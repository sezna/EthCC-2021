### Example Contracts

```rust
contract;
let mut balance = 0;
abi UnauthenticatedMoneyHole {
   fn deposit();
   fn get_balance();
}

impl UnauthenticatedMoneyHole for Contract {
  fn deposit() {
    contract.balance += msg.value;
  }
  fn get_balance() {
    contract.balance
  }
}
```
