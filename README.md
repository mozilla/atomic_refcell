# atomic_refcell

A thread-safe analogue of [`RefCell`](https://doc.rust-lang.org/std/cell/struct.RefCell.html) for Rust.

## Overview

[`AtomicRefCell`](https://docs.rs/atomic_refcell/) provides `RefCell`-like borrow semantics (checked at runtime, with immutable and mutable borrows) for values shared across threads. It is designed for use cases where the caller can guarantee that mutable and immutable borrows never overlap concurrently, but still requires a `Sync` type.

The crate is `no_std` compatible.

## Features

| Feature | Description |
|---|---|
| `portable-atomic` | Use [`portable-atomic`](https://crates.io/crates/portable-atomic) instead of `core::sync::atomic`. Enables support for targets without native atomic compare-and-swap instructions (e.g. `thumbv6m-none-eabi`). |
| `serde` | Implement `Serialize` and `Deserialize` for `AtomicRefCell<T>`. |

## Minimum Supported Rust Version (MSRV)

Rust **1.60** or later is required.
