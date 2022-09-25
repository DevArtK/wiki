# Strings

There are at least 6 types of strings in the rust std library
- We most are about 2 of them


**str slice**
```rust
// Borrowed str slice
let msg = "Hello World";
```
- Will mostly ever see it as a borrowed string slice ```&str```

A literal string is always a borrowed string slice
- The data in a borrowed string slice cannot be modified

A borrowed str slice is made up of :
- A pointer (ptr), to some bytes
- A length (len)


**String**
```rust
let msg = "abc".to_string();
or
let msg = String::from("abc");
```
Data can be modfified

A String is made up of :
- A pointer (ptr), to some bytes
- A length (len)
- Capacity


Both String and str are made up of valid utf-8
