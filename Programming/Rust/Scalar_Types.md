# Rust : Scalar Types

There are 4 Scalar :
- Integers
- Floats
- Booleans
- Characters (Chars)



### Integer Types

| Unsigned | Signed |
| ---      | ---    |
| u8       | i8     |
| u16      | i16    |
| u32      | i32    |
| u64      | i64    |
| u128     | i128   |
| usize    | isize  |


**Unsigned** : Are consistent across all platforms

- Except for usize, which is the size of the platforms pointer type and can represent every memory address in the process
- Usize is also usually the type used to index into an array and vector


**Signed** : Are consisten across all platorms

- isize also has the same number of bits as the platforms pointer type
- Maximum isize value is the upper bound of object and array size, ensures that isize can be used to caluclate differences between pointers and be able to address every byte in a value like a struct
- i32 is generally the fastest across platforms evenin 64 bit architecture



### Integer Literals

| Type    | Value          |
|---------|----------------|
| Decimal | 1000000        |
| Hex     | **ox**deadbeef     |
| Octal   |                |
