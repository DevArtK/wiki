# Variables & Constants
Declaring variables and constants, immutablity, mutablility and the differences between the two


## Variables

Variables are immutable by default

Example of Error on re-assigment of an immutable error

Code:
```rust
fn main() {
    let x = 5;
    println!("The value of x is: {}", x);
    x = 6;
    println!("The value of x is: {}", x);
}
```

Error Output:
```bash
$ cargo run
   Compiling variables v0.1.0 (file:///projects/variables)
   error[E0384]: cannot assign twice to immutable variable `x`
    --> src/main.rs:4:5
  |
2 |     let x = 5;
  |         -
  | first assignment to `x`
  | help: consider making this binding mutable: `mut x`
3 | I h println!("The value of x is: {}", x);
4 | x = 6;
  | ^^^^^ cannot assign twice to immutable variable

  For more information about this error, try `rustc --explain E0384`.
  error: could not compile `variables` due to previous error
```

Code Fix:
```rust
fn main() {
    let mut x = 5;
    println!("The value of x is : {}", x);
    x = 6;
    println!("The new value of x is : {}", x);
}
```

## Constants

Constants are variables that are bound to a name that are not allowed to change
- Not allowed to use mut on a Constant
- Declared with the const keyword instead of let
- Value type must me annotated
- Can be delcared in any scope, including global
- Can only be set to a constant expression, not the result of a value that could only be computed at runtime
