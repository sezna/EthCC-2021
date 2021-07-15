            ### Types
Note:
Our type system is essentially the same as Rust's, with a few differences:

----

### Primitive Types
1. Unsigned Integers
1. Booleans
1. Static-length strings
1. 32-byte values
1. Single-byte values
1. The unit type

Note: 
We mainly just support the primitive types that Solidity cares about, and are common in smart contracts.

----

### Generics and Traits

```rust
contract;
trait Foo&lt;T, E&gt;
  where T: Bar + Baz,
        E: Quux {
      [ ... ]
  }
```

Note: 
We do fully support generic types and traits in the same way Rust does.
All of the solidity address, contract, and hash types are wrapper types around byte32 with their own APIs in the standard library.

Bytes and addresses can be declared with literal syntax.

----

```rust
let x: byte32 =
 0xAFAFAFAFAFAFAFAFAFAFAFAFAFAFAFAFAFAFAFAFAFAFAFAFAFAFAFAFAFAFAFAF; 

let y: byte = 0xAF;

let z: byte = 0b10101010;
```