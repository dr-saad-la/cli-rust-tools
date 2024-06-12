# The Rustup Default Command

The `rustup default` command is used to set or query the default Rust toolchain for the current user. 

## Getting Help

```bash
rustup default --help
```

- The general syntax 

```bash
rustup default [toolchain]
```

```text
Usage: rustup default [toolchain]

Arguments:
  [toolchain]  'none', a toolchain name, such as 'stable', 'nightly', '1.8.0', or a custom toolchain name.
               For more information see `rustup help toolchain`

Options:
  -h, --help  Print help

Discussion:
    Sets the default toolchain to the one specified. If the toolchain
    is not already installed then it is installed first.
```

## Basic Usage

- Query the Default Toolchain: Running the command without any arguments will display the current default toolchain.
- Set the Default Toolchain: You can set a specific toolchain as the default by providing the toolchain name as an argument.

### Querying the Default Toolchain

- To see which toolchain is currently set as the default, you can simply run:

```bash
rustup default
```

This command will output the name of the default toolchain, for example, here is an output from my machine:

```text
stable-x86_64-apple-darwin (default)
```

## Setting the Default Toolchain

- Before you set a default toolchain, you may want to list the installed toolchains in your machine. For more details on listing installed toolchains, refer to the [Custom Toolchains](custom-toolchains.md#listing-installed-toolchains) section.
- To set a specific Rust toolchain as the default, you can specify the toolchain name. For example, if you want to set the stable toolchain as the default, you would use:

```bash
rustup default stable
```

If you want to set the `nightly` toolchain as the default, you would use:

```bash
rustup default nightly
```

### Example: Setting the Default Toolchain to Stable

- Set the Default Toolchain:

```bash
rustup default stable
```

- Verify the Default Toolchain:

```bash
rustup default
```

```bash
stable-x86_64-unknown-linux-gnu (default)
```

### Setting the Default Toolchain to Nightly
- Set the Default Toolchain:

```bash
rustup default nightly
```

- Verify the Default Toolchain:

```bash
rustup default
```

```bash
nightly-x86_64-unknown-linux-gnu (default)
```

## Use Case: Creating Rust Application with Rust Edition 2024

On my current version of Rust installed on my machine `1.78`, using Rust edition 2024 is not allowed, thus we need to set the default toolchain to `nightly`

1. Setting the nightly toolchain

If the toolchain is not installed, then rustup will install it first and then set it to be the default for our projects. 


```bash
rustup default nightly
```


2. Check the default now

```bash
rustup default
```

3. Create the rust application with Rust edition 2024

```bash
cargo new test_app --edition 2024 --name test-application
```

4. Check the application

```bash
cd test_app
cargo check
```

- Here is the Cargo.toml file

```toml
[package]
name = "test-application"
version = "0.1.0"
edition = "2024"

[dependencies]
```

- Checking the application

```bash
cargo check
```

This command issued an error like this:

```text
error: failed to parse manifest at `~/test_app/Cargo.toml`

Caused by:
  feature `edition2024` is required

  The package requires the Cargo feature called `edition2024`, but that feature is not stabilized in this version of Cargo (1.81.0-nightly (b1feb75d0 2024-06-07)).
  Consider adding `cargo-features = ["edition2024"]` to the top of Cargo.toml (above the [package] table) to tell Cargo you are opting in to use this unstable feature.
  See https://doc.rust-lang.org/nightly/cargo/reference/unstable.html#edition-2024 for more information about the status of this feature.
```

So I need to add `cargo-features = ["edition2024"]` to the `Cargo.toml` as suggested by the compiler

- Here is the updated file:

```toml
cargo-features = ["edition2024"]
[package]
name = "test-application"
version = "0.1.0"
edition = "2024"

[dependencies]
```

- Now checking the application again using `cargo check` command. 
- The application passed and it is working fine.

```text
Checking test-application v0.1.0 (~/test_app)
Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.36s
```

- If you need to set the stable version for other projects, it suffices to use the next command:

```bash
rustup default stable
```

- Check to make sure

```bash
rustup default
```

- Overall, you will be familiar with commands and they will become natural to you as you work with different types of Rust applications.


The rustup default command streamlines the management of the default Rust toolchain on your system. It allows for convenient switching between different Rust versions to meet your development requirements, such as:
  -  stable.
  -  beta.
  -  nightly. 

Setting the correct default toolchain guarantees that your development environment is configured accurately for your projects.
