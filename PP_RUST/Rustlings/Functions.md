# Functions
[->ref](https://doc.rust-lang.org/stable/book/ch03-03-how-functions-work.html)
```Rust
fn function_name(parameters) {}
```
- `fn` keyword
- doesn't matter where you define functions
	- can call functions inside others
	- definition order irrelevant

## main-function
```Rust
fn main() {}
```
- special -> always the first code that runs in every executable Rust program

## Naming
- *snake case* for function/variable names
	- conventional style
	- lowecase and undescores

## Parameters/Arguments
- special variables that are part of function's signature
- type must be declared 
### Example
```Rust
fn main() {
    another_function(5, 6);
}
   
fn another_function(x: i32, y: i64) {
    println!("The value of x is: {}", x);
	println!("The value of y is: {}", y);
}
```

## Function Bodies
[->ref](https://doc.rust-lang.org/stable/book/ch03-03-how-functions-work.html#function-bodies-contain-statements-and-expressions)
- made up of series of **statements** optionally ending in **expression**
### statements
- instructions that perform some action
- do not return value
- function definitions also statements
- can't assign `let` statement to another variable
	- different in other languages C / Ruby
#### Example
```Rust
fn main() {
    let y = 6;
}
```
### expressions
- evaluate to resulting value
- return value based on its operand
- do not include ending semicolons
#### Examples
- math operation
- calling a function/macro
- the block to create new scopes, `{}`
```Rust
fn main() {
    let x = 5;
    
    let y = {
        let x = 3;
        x + 1                            //no semicolon
    };
    
    println!("The value of y is: {}", y);
}
```

## Return Values
[->ref](https://doc.rust-lang.org/stable/book/ch03-03-how-functions-work.html#functions-with-return-values)
- functions can return values to code that calls them
- value is synonymous with the value of the final expression in the block of the body of a function
- don't name them
- declare their type after `->`
- can return early from function by using `return` and specifying a value
### Examples
```Rust
fn five() -> i32 {               //valid function
    5                            //expression
}

fn main() {
    let x = five();
    
    println!("The value of x is: {}", x);
}
```

```Rust
fn main() {
    let x = plus_one(5);
    
    println!("The value of x is: {}", x);
}

fn plus_one(x: i32) -> i32 {
    x + 1;                           //semicolon makes it a statement
}
```
- will produce error
	- statements don't evaluate to a value, which is expressed by `()` (behaves like `void`)
	- nothing is returned -> error