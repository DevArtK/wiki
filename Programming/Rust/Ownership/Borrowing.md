# Ownership & Borrowing

Ownership - Concept allows the language to be memory-safe without a garbage
collector


## Ownership
**Ownership Rules**
- Every value has a variable which is its owner; Each value has an owner
- The value's ownership can be moved; there only one owner at a time
- When the owner goes out of scope, the value is released

```rust
fn main() {
    let x = String::from("Hello");      // x is the owner of the String
    println("Initially, x is the owner of : {x}")

    let y = x       // The String value is moved to 'y'. 'x' is no longer the owner

    // Trying to access the String value through 'x' is an invalid operation

    println("Now, y is the owner of : {y}")

    // At the end of the function, 'y' goes out of scope and the String is released
}
```

Ownership In Action
```rust
let s1 = String::from("abc");
let s2 = s1; // The value is not copied, it's ownership is moved
println!("{}", s1); // Error; value borrowed here after move
```
1. s1 is created; a pts, a len, and capacity get creaeted onto the stack

        capacity is 3, length is 3 and the pointer points to some newly
        allocated bytes on the Heap (a, b, c)

2. Then s1's value is moved to s2, as we can only have one owner of a value

        The pointer, length and capacity get copied from s1 and pushed as new
        values on the stack as part of s2, and s1 is invalidated (uninitialized)

| Stack                    | Heap                                 |
| ---                      | ---                                  |
| In order                 | Unordered                            |
| Fixed-size               | Variable-size                        |
| LIFO : Last In First Out | Not Dropped in order of when created |
| Fast                     | Slow                                 |


**Copy Instead of Move**
```rust
let s1 = String::from("ABC");
let s2 = s1.clone();
```
Clone performs the same intial copy of the stack, but also copies the heap data
and adjusts s2's pointer to point to the the new values on the Heap

The Stack and Heap data (if Heap data present) together make up a "value"

Copy term is only used when Stack data is being copied

If there is Heap Data and Pointer updates involved then "clone" term is used or
also known as a "deep copy"

When a value is dropped that means :
- The destructor (if there is one) is run
- The Heap memory is freed
- The Stack is poppped
Resulting in no memory leaks, no pointers no errors



## Borrowing

- The value's owner can borrow it through shared references(immutable) or unique
  references(mutable)
- At any moment, there can only be one unique reference or any number of shared
  references
- References are always valid. They can't be used after the value they reference
  is moved or released


**Illustration of Unique and Shared References**

```Rust
struct Book {
    title: String,
}

fn shared(book: &Book){
    println("[Shared] The book's title is {}\n", book.title);
}

fn unique(book: &mut Book) {
    println("[Unique] The book's title was: {}", book.title);
    book.title.push_str(" part 2");
    println("[Unique] Now the title is: {}\n", book.title);
}


fn be_owner(book: Book) {
    println("[be_owner] I'm the owner of the book: {}\n", book.title);
}

fn main() {

    let mut first_owner = Book {
        title: String::from("How to make friends and influence people");
    };

    // Here, we are lending a shared borrow of the book to the variable'first_borrow'
    let first_borrow = &first_owner;

    // We create a second shared reference to pass to the function 'shared'
    shared(&first_owner);

    // It's okay if you lend a mutable borrow
    unique(&mut first owner)

    // But you cannot access 'first_borrow' anymore
    // println("title: {}", first_borrow.title);

    // But there's no problem in creating a new shared reference
    let second_borrow = &first_owner;


    // The idea is that if you have a shared reference,
    // you cannot access it after it could have changed
    // e.g. By a mutable reference,
    // or when the value is moved to a new owner


    // Everything's okay
    shared(second_borrow) // Same as : shared(&first_owner)

    // Ownership moved to another owner
    let second_owner = first_owner;

    // All the preceding references stopped being valid because of the move.
    // The old owner stopped being accessbile too
        // shared(second_owner);
        // unique(&mut first_owner)

    println("[main] second owner: {n}\n", second_owner.title);

    be_owner(second_owner);

    // The book is not accessble here, since its ownership was passed to the 'be_owner' function
    // At this point, the value has been released.
    // 'second_owner' is not accessible as well
        // let invalid_borrow = &second_owner;

}
```
