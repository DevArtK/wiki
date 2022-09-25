# Control Flow

**If Expression**

Statements don't return values, expressions do, so the following code :
```rust
if num == 5 {
    msg = "Five";

} else if num == 4 {
    msg = "Four";

} else {
    msg = "Other";
}
```

Can be written like so :
```rust
// Msg is assigned the value of the if expression
msg = if num == 5 {
    "Five"

} else if num == 4 {
    "Four"

} else {
    "Other"
};
```
Note:
1. There are no semi colons after the branch values, so the values get
returned from the blocks as tail expressions
2. Cannot use return statement, because return only applies to blocks that are
   function bodies
3. All blocks return the same type
4. There is a semi colon at the end of the if expression


```rust
// Ternary Operator :
num = a ? b : c;

// Rust Equivalent :
num = if a { b } else { c };

// Nested Ternary
num = a ? x ? y : z : c;
or
num = a
      ? x ? y : z
      : c;

// Rust Equivalent to Nested Ternary :
num = if a {
    if x { y } else { z }
} else {
    c
};
```


**Unconditional Loop**
``` rust
loop{
    break;
}
```


** Nested Unconditional Loop**
Can annotate a loop with label :
```rust
// When code hits the break statement of inner loop it will break out up to the
// labeled outter loop, this works for continue statement as well

'bob: loop {
    loop {
        loop {
            break 'bob';
        }

    }
}'
```


**While Loops**
```rust
while dizzy() {

}
```



**For Loops**
```rust
for num in [7, 8, 9].iter() {
    // do stuff with num
}
```

```rust
let array = [(1, 2), (3, 4)];

for (x, y) in array.iter() {
    // do stuff with x and y
}
```

**Ranged For Loop**

- The start is inclusive, start = 0
- The end is exlusive, end is 49
- To specify the end to be inclusive as well use 0..=50 as range

```rust
for num in 0..50 {
    // do stuff with num
}
```
