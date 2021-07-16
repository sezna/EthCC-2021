#### Inline Assembly

Note: Both Solidity and Sway support writing inline assembly, and indeed, Sway's standard library is mostly implemented with this construct.

----
```solidity
assembly {
    let size := extcodesize(_addr)
    o_code := mload(0x40)
    mstore(0x40, add(o_code, and(add(add(size, 0x20), 0x1f), not(0x1f))))
    mstore(o_code, size)
    extcodecopy(_addr, add(o_code, 0x20), 0, size)
}
```

Note: Here's an assembly example from Solidity's documentation. We target our own bytecode, which then is transpiled. Therefore,
our assembly notion looks a bit different as you are actually targeting Fuel Labs' opcodes. Let's take a look:

----

```rust
fn adds_in_asm(a: u64, b: u64) -> u64 {
  asm(r1: a, r2: b, r3) {
    add r3 r2 r1; 
    r3
  }
}
```

Note: initialization of registers, add opcode, implicit return value

----

```rust
fn or(a: bool, b: bool) -> bool {
  asm(r1: a, r2: b, r3) {
    or r3 r2 r1; 
    r3: bool
  }
}
```

Note: register type, type annotation

----

```rust
fn complex_things(a: bool) -> bool {
  asm(r1: foo(a) + baz()) {
     [ ... ]
  }
}
```

Note: any expressions in asm init


---

```rust
let x = if predicate { 
    asm(r1: foo(), r2: bar()) {
      [ ... ]
  } else {
    asm(r1: bar(), r2: baz()) {
      [ ... ]
  }
};
```
Note: Solidity offers control flow inside of assembly blocks. In Sway, we instead make assembly blocks expressions,
so control flow can be handled in normal Sway without a separate syntax.