### Events


```solidity
contract SimpleAuction {
    // Event
    event HighestBidIncreased(address bidder, uint amount); 

    function bid() public payable {
        // ...
        // Triggering event
        emit HighestBidIncreased(msg.sender, msg.value); 
    }
}
```

Note:
Here's an event and event emission from Solidity.


```rust
contract;
use std::chain::Address;

struct HighestBidIncreased {
  bidder: Address,
  amount: u64
}

impl SimpleAuction for Contract {
  fn bid() {
    [ ... ]
    emit(HighestBidIncreased {
      contract.msg_sender, contract.amount
    });
  }
}
```

Note:
There's not really a reason events need to be events and not structs, so we just use structs for this. Emit is not a keyword but a generic function in the standard library.
