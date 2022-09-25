# Structs
In other languages there are classes in Rust there are Structs

Structs can have :
- Data fields,
- Methods
- Associated Functions

[Traits](Traits)

### Declaring a Struct

```rust
// syntax :
struct StructName {
    fieldName: type,
    fieldName: type
}

example :
struct RedFox {
    enemy: bool,
    life: i32
};
```

###  Instantiating a Struct

```rust
let fox = RedFox {
    enemy: true,,
    life: 70
};
```

### Implement a constructor function (Associated Functions)
Implement an associated function to use as a constructor

Implementation blocks are seperate from a struct definition

**Associated Functions** : do not take self as a function parameter, also called
class methods
- Often used as constructors or static methods in other languages

```rust
impl RedFox {
    fn new() -> Self {
        Self {
            enemy: true,
            life: 70,
        }
    }

    // Associated function
    fn function() {
    // ...
    }

}

```

**Calling an Associated Function (Static Function)**
```rust
let fox = RedFox::new(); // Notice the call
```

## Methods

```rust
impl RedFox {

    // Methods - always take some form of self as their first argument
    fn move(self) {
    // ...
    }

    fn borrow(&self) {
    // ...
    }

    fn mut_borrow(&mut self) {
    // ...
    }
}
```
let life_left = fox.life;
fox.enemy = false;
fox.some_method();
```


There is no struct inheritance in Rust, it uses Traits instead
