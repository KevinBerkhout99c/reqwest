# Report for Assignment 1 resit

## Reqwest
Name: Kevin Berkhout

URL: https://github.com/KevinBerkhout99c/reqwest

Number of lines of code and the tool used to count it: 
nloc: 15938, counted by lizard

Programming language: rust

## Coverage measurement with existing tool
the tool i used to measure coverage is tarpaulin
tarpaulin is a command line tool, the command used to run the tool is cargo tarpaulin –ignore-tests  –out Lcov. Ignore tests causes the tool to not use the test files in the coverage % calcalculations , the out Lcov argument is used to create a coverage log of the result. this is then used by  coverage gutters vscode to display the coverage of individual functions and lines of code.




the change mentioned is some inconsistency in the proxy tests, I did not touch those.


## Coverage improvement

### Individual tests

<Fast_random()>

https://github.com/KevinBerkhout99c/reqwest/commit/e26f521565ec09c7ee8105ad586a9a4a4dbc10d8

https://github.com/KevinBerkhout99c/reqwest/commit/eae9aed2ae23fd6e67a6933fa02e78de3a4f945d

the second link is to the uncommenting of the function, since i committed as a commend the first time by accident.




the coverage is increased by 100, as the function goes from untested to tested. that said a part of the tests were already enforced by debug asserts. so it's not fully accurate to say the function started at 0.




<is end stream>

<Show a patch (diff) or a link to a commit made in your forked repository that shows the new/enhanced tests for function 1>

<Provide a screenshot of the old coverage results for such function>

<Provide a screenshot of the new coverage results for such function>

<State the coverage improvement with a number and elaborate on why the coverage is improved>

### Overall



















































# reqwest

[![crates.io](https://img.shields.io/crates/v/reqwest.svg)](https://crates.io/crates/reqwest)
[![Documentation](https://docs.rs/reqwest/badge.svg)](https://docs.rs/reqwest)
[![MIT/Apache-2 licensed](https://img.shields.io/crates/l/reqwest.svg)](./LICENSE-APACHE)
[![CI](https://github.com/seanmonstar/reqwest/workflows/CI/badge.svg)](https://github.com/seanmonstar/reqwest/actions?query=workflow%3ACI)

An ergonomic, batteries-included HTTP Client for Rust.

- Async and blocking `Client`s
- Plain bodies, JSON, urlencoded, multipart
- Customizable redirect policy
- HTTP Proxies
- HTTPS via system-native TLS (or optionally, rustls)
- Cookie Store
- WASM


## Example

This asynchronous example uses [Tokio](https://tokio.rs) and enables some
optional features, so your `Cargo.toml` could look like this:

```toml
[dependencies]
reqwest = { version = "0.12", features = ["json"] }
tokio = { version = "1", features = ["full"] }
```

And then the code:

```rust,no_run
use std::collections::HashMap;

#[tokio::main]
async fn main() -> Result<(), Box<dyn std::error::Error>> {
    let resp = reqwest::get("https://httpbin.org/ip")
        .await?
        .json::<HashMap<String, String>>()
        .await?;
    println!("{resp:#?}");
    Ok(())
}
```

## Commercial Support

For private advice, support, reviews, access to the maintainer, and the like, reach out for [commercial support][sponsor].

## Requirements

On Linux:

- OpenSSL with headers. See https://docs.rs/openssl for supported versions
  and more details. Alternatively you can enable the `native-tls-vendored`
  feature to compile a copy of OpenSSL.

On Windows and macOS:

- Nothing.

Reqwest uses [rust-native-tls](https://github.com/sfackler/rust-native-tls),
which will use the operating system TLS framework if available, meaning Windows
and macOS. On Linux, it will use the available OpenSSL or fail to build if
not found.


## License

Licensed under either of

- Apache License, Version 2.0 ([LICENSE-APACHE](LICENSE-APACHE) or http://apache.org/licenses/LICENSE-2.0)
- MIT license ([LICENSE-MIT](LICENSE-MIT) or http://opensource.org/licenses/MIT)

### Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in the work by you, as defined in the Apache-2.0 license, shall
be dual licensed as above, without any additional terms or conditions.

## Sponsors

Support this project by becoming a [sponsor][].

[sponsor]: https://seanmonstar.com/sponsor
