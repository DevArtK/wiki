# Compound Types


### Tuple



**Decalaring**
```rust
// Simple
let info = (1, 2.3, 999);

// Defining types in tuple
let info: (u8, f64, i32) = (1, 2.3, 999);
```

**Accessing**

There are two ways to access a member of a tuple:


```rust
let info = (1, 3.3, 999);

// Dot Syntax
let jets = info.0;
let fuel = info.1;
let ammo = info.2;

// Destructing
let (jets, fuel, ammo) = info;
```


### Arrays

**Declaring**
```rust
// Literal
let buf = [1, 2 ,3];

// Value and size of array
// Value = 0
// Size = 3
let buf = [0; 3];

// Defining Type in array
let buf: [u8; 3] = [1, 2, 3];

```


### Vectors

**Declaring**

```rust
// Long form
let mut vec1 = Vec::new();

// Macro
let mut vec1 = vec![1, 2, 3];

// Declaring with type
let mut vec: Vec<i32> = Vec::new();

// Specify capacity, will still have 0 length
let mut vec: Vec<i32> = Vec::with_capacity(10);


```
