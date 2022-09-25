# Attributes

Attributes are metadata applied to some module, crate or item

This metadata can be used for :
- Conditional compilation of code
- set crate name, version and type (binary or library)
- disable lints(warnings)
- enable compiler features (macros, glob imports, etc)
- link to a foreign libary
- mark functions as unit tests
- mark functions that will be part of a bench mark


**Applying Attributes to Whole Crate**
When attributes apply to a whole crate, their syntax is :
```rust
#![crate_attribute]     // Notice '!'

```

**Applying Attributes to a Module or Item**
When attributes apply to a module or item, the syntax is :
```rust
#[item_attribute]       // Notice no '!'
```

Attributes can take arguments with different syntaxes :
```rust
#[attribute = "value"]
```

```rust
#[attribute(key = "value")]
```

```rust
#[attribute(value)]
```


## Useful Attributes

```rust
// Hide warnings for unused code
#![allow(unused_variables)]
```

```rust
// Hide warnings for unused code
#![allow(dead_code)]
```


```rust
// Pretty print
#![derive(Debug)]
```
