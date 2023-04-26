# Control Flow

## if-Expression
[->ref](https://doc.rust-lang.org/stable/book/ch03-05-control-flow.html#if-expressions)
- `if` expression allows to branch code depending on conditions
- optional `else`
- condition must be `bool`
	- will automatically try to convert non-Boolean types to Boolean
- blocks of code associated with conditions in if expressions are called *arms*/cases
	- like *arms* in `match` expressions
### Example
```Rust
fn main() {
    let number = 3;
    
    if number < 5 {
        println!("condition was true");
    } else {
        println!("condition was false");
    }
}
```

## Handling Multiple Conditions
[->ref](https://doc.rust-lang.org/stable/book/ch03-05-control-flow.html#handling-multiple-conditions-with-else-if)
- `else if`-Expression
- executes only the block for the first true condition
	- doesn't check rest after finding
- too many `else if` expression can clutter code
	- might want to refactor [->`match`](https://doc.rust-lang.org/stable/book/ch06-00-enums.html)
### Example
```Rust
fn main() {
    let number = 6;
    
    if number % 4 == 0 {
        println!("number is divisible by 4");
    } else if number % 3 == 0 {
        println!("number is divisible by 3");
    } else if number % 2 == 0 {
        println!("number is divisible by 2");
    } else {
        println!("number is not divisible by 4, 3, or 2");
    }
}
```

## `if` in `let` statement
[->ref](https://doc.rust-lang.org/stable/book/ch03-05-control-flow.html#using-if-in-a-let-statement)
- ``if`` is an expression -> can be used on right side of ``let`` statement
- types of potential values must match
	- compiler detects typemismatch
### Example
```Rust
fn main() {
    let condition = true;
    let number = if condition { 5 } else { 6 };     //will be bound depending on condition
    
    println!("The value of number is: {}", number);
}
```
