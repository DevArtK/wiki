# Traits


Traits define required behavior
- Functions and methods that a struct must implement if it wants to have that
  trait


```rust
struct RedFox {
    enemy: bool,
    life: u32,
}

trait Noisy {
    fn get_noise(&self) -> &str;
}


impl Noisy for RedFox {
    fn get_noise(&self) -> &str { "Meow?" }
}
```

### Why Implement Traits for a Struct

Once we have a trait involved, we can start writing generic functions that
accept any value that implement the Trait :
```rust
fn print_noise<T: Noisy>(item: T) {
    println!("{}", item.get_noise());
}
```


## Copy Trait
Special trait, if your type implements Copy, then it will be copied instead of
moved in "move" situations.
- This makes sense for small values that sit entirely in the stack
- If a type uses the Heap at all then it cannot implement copy


## Specify Default Behavior

```rust
trait Run {
    fn run(&self) {
        println!("I'm running");
    }
}

struct Robot {}
impl Run for Robot {} // Don't provide a method definition to use default

fn main() {
    let rb = Robot {};
    robot.run(); // I'm running
}

```
