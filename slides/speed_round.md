### Speed round


#### Ifs are expressions
```rust
let civilian_time = if time.hours &gt; 12 {
    Time { 
      hours: time.hours - 12, 
      minutes: time.minutes 
    }
  } else {
    time
  };
```


#### Unchecked Arithmetic

```rust
arithmetic: wrapping {
   0xff_fff_fffu32 + 1 == 0
}
```

Note: we use the canonical names of the arithmetic types instead of the more vague "unchecked" term. Math will panic if it overflows by default. 


#### Sweet underscore syntax
```rust
arithmetic: wrapping {
   0xff_fff_fffu32 + 1 == 0
}
```
