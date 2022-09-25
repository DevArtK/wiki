# Command Line Parsing


```rust
// Get command line arguments, skips the first which is not needed
let args: Vec<String> = std::env::args().skip().collect();
```

Either gets the first argument as a string or print usage and exists if an
argument was not supplied to the program
```rust
let mut arg: String = std::env::args().nth(1).unwrap_or_else(|| {
    println!("Please supply an argument to this program");
    std::process::exit(-1);
})
```
