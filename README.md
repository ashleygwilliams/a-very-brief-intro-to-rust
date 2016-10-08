# a-very-brief-intro-to-rust

## install rust

The best way to install Rust is with [rustup]. [rustup] is a Rust
version manager. To install it type:

```
curl https://sh.rustup.rs -sSf | sh
```

To keep your rust up-to-date with the latest stable version of rust,
type:

```
rustup update
```

To check which version of Rust you have type:

```
rustc -- version
```

## setting up a project

There are many ways to setup a project in Rust, but this is the simplest.

1. Create a repository on Github
2. Clone the repository
3. `cd` into the repository directory
4. Type `cargo init .`

This will create several files and folders for you automatically:

- `Cargo.toml`: metadata about your project and it's dependencies
- `.gitignore`: ignores compiled files built by Rust
- `src/lib.rs`: where your Rust code goes (change this to `main.rs` if you are not writing a library)

#### `lib.rs` vs `main.rs`

There are 2 main types of projects you can make in Rust. A library and not
a library. 

If you are writing a <strong>library</strong>, it means you intend for your
code to be used in someone else's application as a crate or module.
If you want to do this, you should use a `lib.rs`.

If you are writing a <strong>not library</strong>, it means that you'd like
to write code that compiles into a binary that someone can run. If you 
want to do this, you need to use a `main.rs`. Inside the `main.rs` you 
should have a `main` function that looks like this:

```rust
fn main() {
  /// your app code goes here
}
```

## storing values

To get started using Rust you'll probably want to assign values so that
you can use them. To do this in Rust:

```
let name = "ashley";
let age = 30;
```

If you want to make a constant, you must specify a type:

```
const FAVENUM: u32 = 6;
```

## types

There are a lot of types, but just to get you started:

- `u32`: unsigned 32-bit integer
- `i32`: signed 32-bit integer
- `String` and/or `&str`: more on these below
- `bool`: a boolean

## dealing with strings

String in Rust are a lot more complicated than you might be used to if
you are coming from another language, in particular, interpreted languages
like Ruby or JavaScript. Here's some key points:

#### `&str` and `String`
- "my string" is not a `String`. it's a `str`, which reads as "static string". the difference
  is how it is allocated. don't worry about that right now. pretty much always use `str` with
  an `&`, as `&str`.
- You can turn a `&str` into a `String` by using `to_string()` or `String::from()`. You want
  to do this because String has a ton of awesome convenience methods.

#### concatentation

- add a `&str` to a `String` using `push_str()`

```rust
let realstring = String::from("hello ");
let str1 = "world!"
let message = realstring.push_str(str1);
```

- add `&str`s using `format!`

```rust
let str1 = "hello ";
let str2 = "world!"
let message = format!("{}{}", str1, str2);
```

- add a `char` to a `String` using `push()`

```rust
let realstring = String::from("hello world");
let char1 = '!''
let message = realstring.push(char1);

```

#### characters

- a `char` is a different type than a `str` or `String`. `char` is always single quotes.
- to get a `String`'s `char`s you can call `chars()`
- you might find that instead of `chars()` you really want `as_bytes()` but if you aren't sure
  don't sweat it rn

Example:

```rust
let letters = String::from("ashley").chars();

for l in letters {
  /// do something cool with characters
}
```

## function signatures

## `println!` and `format!`

## the `Option` and `Result` types

## `match` syntax

