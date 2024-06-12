# Overview of Rustup

- Rustup is the official Rust toolchain installer, and it allows you to manage multiple versions of Rust and associated components.

## Getting Help

```bash
rustup --help
```

- Here is the output from the previous command:

```text
The Rust toolchain installer

Usage: rustup [OPTIONS] [+toolchain] [COMMAND]

Commands:
  show         Show the active and installed toolchains or profiles
  update       Update Rust toolchains and rustup
  check        Check for updates to Rust toolchains and rustup
  default      Set the default toolchain
  toolchain    Modify or query the installed toolchains
  target       Modify a toolchain's supported targets
  component    Modify a toolchain's installed components
  override     Modify toolchain overrides for directories
  run          Run a command with an environment configured for a given toolchain
  which        Display which binary will be run for a given command
  doc          Open the documentation for the current toolchain
  man          View the man page for a given command
  self         Modify the rustup installation
  set          Alter rustup settings
  completions  Generate tab-completion scripts for your shell
  help         Print this message or the help of the given subcommand(s)

Arguments:
  [+toolchain]  release channel (e.g. +stable) or custom toolchain to set override

Options:
  -v, --verbose  Enable verbose output
  -q, --quiet    Disable progress output
  -h, --help     Print help
  -V, --version  Print version
```



## Getting Rustup Version

```bash
rustup --version
```

## General Syntax


```text
rustup <COMMAND> [OPTIONS] <ARGUMENTS>
```


## Rustup toolchain

- **The general Syntax is**:

```text
rustup toolchain <COMMAND>
```

```bash 
rustup toolchain help
```

- Here is some output from the previous command:


```text
Modify or query the installed toolchains

Usage: rustup toolchain <COMMAND>

Commands:
  list       List installed toolchains
  install    Install or update a given toolchain
  uninstall  Uninstall a toolchain
  link       Create a custom toolchain by symlinking to a directory
  help       Print this message or the help of the given subcommand(s)

Options:
  -h, --help  Print help
```

## Getting Help for `rustup toolchain` Subcommands


```
rustup toolchain <SUB-COMMAND> HELP
```

for example, if you needed to get help for the `list` subcommand, you would have typed this command:

```bash
rustup toolchain list --help
```

## Rustup Toolchain list

This command lists the installed toolchains

```bash
rustup toolchain list
```

you can print more information by using the `-v` or `--verbose` option.

## Rustup toolchain
