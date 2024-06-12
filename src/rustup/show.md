# Showing Installed toolchains

```bash
rustup show
```

```bash
rustup show --help
```

Show the active and installed toolchains or profiles

- The general syntax: 

```bash
rustup show [OPTIONS] [COMMAND]
```

```text
Commands:
  active-toolchain  Show the active toolchain
  home              Display the computed value of RUSTUP_HOME
  profile           Show the default profile used for the `rustup install` command
  help              Print this message or the help of the given subcommand(s)

Options:
  -v, --verbose  Enable verbose output with rustc information for all installed toolchains
  -h, --help     Print help

Discussion:
    Shows the name of the active toolchain and the version of `rustc`.

    If the active toolchain has installed support for additional
    compilation targets, then they are listed as well.

    If there are multiple toolchains installed then all installed
    toolchains are listed as well.
```

### Examples

```
rustup show -v home
```
/Users/username/.rustup

```bash
rustup show -v active-toolchain
```
stable-x86_64-apple-darwin (default)

```bash
rustup show -v profile
```

default
