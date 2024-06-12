# Updating Rust

## The `update` Command

Update Rust toolchains and rustup


```bash
rustup update --help
```

- **The general syntax**:

```bash
rustup update [OPTIONS] [toolchain]...
```


```text
Arguments:
  [toolchain]...  Toolchain name, such as 'stable', 'nightly', or '1.8.0'. For more
                  information see `rustup help toolchain`

Options:
      --no-self-update  Don't perform self update when running the `rustup update` command
      --force           Force an update, even if some components are missing
      --force-non-host  Install toolchains that require an emulator. See
                        https://github.com/rust-lang/rustup/wiki/Non-host-toolchains
  -h, --help            Print help

Discussion:
    With no toolchain specified, the `update` command updates each of
    the installed toolchains from the official release channels, then
    updates rustup itself.

    If given a toolchain argument then `update` updates that
    toolchain, the same as `rustup toolchain install`.
```
