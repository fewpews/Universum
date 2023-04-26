# Data Types
- every value is of certain *data type*
- Rust is *statically typed language* 
	- must know types of all variables at compile-time
	- Compiler can usually infer the type based on value and usage
		- if multiple types possible we must add type annotation
```Rust
let guess: u32 = "42".parse().expect("Not a number!");
```

## Scalar Types
- primitive types
- represent single value
- integers / floating-point numbers / Booleans / characters
### Integer Types
- number without a fraction component
| Length                         | Signed (pos/neg) | Unsigned (pos) |
| ------------------------------ | ---------------- | -------------- |
| 8-bit                          | i8               | u8             |
| 16-bit                         | i16              | u16            |
| 32-bit                         | i32              | u32            |
| 64-bit                         | i64              | u64            |
| 128-bit                        | i128             | u128           |
| arch (32-/64-bit architecture) | isize            | usize          |
-> arch primarily used when indexing some sort of collection
#### Signed
- stored using two's complement representation
- store numbers from $-(2^{n−1})$ to $2^{n−1}-1$ -> $n$ number of bits that variant uses
#### Unsigned
- store numbers from $0$ to $2^n-1$
#### Integer literal forms
- all but byte allow type suffix
	- `57u8`
- and visual seperator
	- `1_000`
| Number literals | Example     |
| --------------- | ----------- |
| Decimal         | 98_222      |
| Hex             | 0xff        |
| Octal           | 0o77        |
| Binary          | 0b1111_0000 |
| Byte (u8 only)  | b'A'        | 
#### Examples
```Rust
fn main() {  
    let _age: u8 = 33;   
    let _celsius_temperature: i16 = 0;  
    let _fahrenheit_degree = 451_i16;   
    let _salary: usize = 1_000_000;   
    let _localhost = 0x7f000001;   
    let _file_mask = 0o755;  
    let _binary_mask = 0b1111_0000;  
}
```

### Floating-Point Types
- `f32` (single precision) and `f64` (double precision)
	- 32-/64-bit in size
- `f64` default 
	- same speed in modern CPU
	- capable of more precision
#### Examples
```Rust
fn main() {
    let x = 2.0; // f64
    let y: f32 = 3.0; // f32
    let z = 4.0f32; // f32
}
```

### Numeric Operations
- supports addition / subtraktion / multiplication / division / remainder
- [list of opperators](https://doc.rust-lang.org/stable/book/appendix-02-operators.html)
#### Examples
```Rust
fn main() {
    // addition
    let sum = 5 + 10;

    // subtraction
    let difference = 95.5 - 4.3;

    // multiplication
    let product = 4 * 30;

    // division
    let quotient = 56.7 / 32.2;

    // remainder
    let remainder = 43 % 5;
}
```

### Boolean Type
- `true / false`
- one byte in size
- main way to use: [[Conditions|Conditionals]]
#### Example 
```Rust
fn main() {
    let t = true;
    let f: bool = false; // with explicit type annotation
}
```

### Character Type
- most primitve alphabetic type
- `char` literals are specified with single quotes
- four bytes in size
- represents Unicode Scalar Value
	- a lot more than just ASCII
		- Accented letters; Chinese, Japanese, and Korean characters; emoji; zero-width spaces
	- values range from `U+0000` to `U+D7FF` and `U+E000` to `U+10FFFF`
#### Examples
```Rust
fn main() {
    let c = 'z';
    let z = 'ℤ';
    let heart = '❤';
}
```

## Compound Types
