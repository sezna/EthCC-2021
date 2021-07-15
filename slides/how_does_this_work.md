## And, how does this work again?
1. Swappable compiler back end
1. From-scratch implementation, re-using lots of Rust and Solidity design decisions
1. A full team of developers working on tooling in parallel with the compiler.

Note: 
  The swappable back end allows for targeting different chains. We are starting with Ethereum.
  for point 2 -- we found that libraries or extensions of other general purpose languages tend
  to lack the domain specificity that smart contract development requires
  For point 3 -- we believe it invaluable that the tooling developers and the compiler developers are
  working in close communication. This is something that is not often seen with Solidity, and it has led
  to fracturing. Our formatter, testing, deployment, compiler, and more are all written by the same team of people.
