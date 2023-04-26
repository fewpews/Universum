# Variables and Mutability
```Rust
let x = 5;
let foo = bar;
```
- `let` statement to create *variables*
- new variable named `foo` bound to the value of the `bar` variable
- Variables **immutable** by default
	- once value is bound to name -> cannot change it
	- safety and easy concurrency

## Compiler
- helps to find errors
- compile-time errors important to avoid bugs
	- if two parts of programm want im/mutability of an value -> bug
- gurantees immutability

## Mutable
```Rust
fn main() {
    let mut x = 5;
    println!("The value of x is: {}", x);
    x = 6;
    println!("The value of x is: {}", x);
}
```
- `mut` keyword makes variable mutable
- indicates that other parts of code will change this variable
### Trade-offs beside bugs
- using large data structures -> mutating instance in place may be faster than copying and returning newly allocated instances
- smaller data structures -> creating new instances and writing in more functional programming style may be easier to think through -> lower performance maybe worth gaining that clarity

## Constants
[->ref](https://doc.rust-lang.org/stable/book/ch03-01-variables-and-mutability.html#constants)
```Rust
const THREE_HOURS_IN_SECONDS: u32 = 60 * 60 * 3;
```
- bound to name and not allowed to change
- cannot use `mut`
	- always immutable
- `const` keyword and type must be annotated
- valid for entire time programm runs within the scope they were declared in
	- can be declared in any scope
	- useful for values many parts of the code need
- naming hardcoded values
	- better understanding
	- one place to update value
- only set to constant expression
	- not result of a value that only could be computed at runtime
	- compiler able to evaluate limited set of operations at compile time ([reference](https://doc.rust-lang.org/stable/reference/const_eval.html))
- long/infinite mathematical constants -> [Rust standard library](https://doc.rust-lang.org/stable/std/f32/consts/index.html)

## Shadowing
```Rust
fn main() {
    let x = 5;

    let x = x + 1;

    let x = x * 2;

    println!("The value of x is: {}", x);
}
```
- declare new variable with same name as previous
	- shadows the previous variable
- second variable's value appears when used
- those transformations -> value still immutable
	- reuse name
	- effectively creating new variable with `let`
	- can also change type (error with `mut`)
```Rust
let spaces = "   ";
let spaces = spaces.len();
```
