# LPC Placeholder Crates

There are usually two kinds of Rust crates for a given microcontroller:

- Peripheral Access Crate (PAC): A low-level library, generated from an SVD file by [svd2rust](https://github.com/rust-embedded/svd2rust).
- Hardware Abstraction Layer (HAL): Higher-level library that provides a safer and more convenient API to work with.

Traditionally, the PAC was named after the microcontroller (e.g. `lpc82x`, while the HAL had the same name, but with the `-hal` suffix (e.g. `lpc82x-hal`). This is somewhat problematic, as end users should almost always use the HAL, but when searching for a given microcontroller, the PAC is what comes up first.

For that reason, parts of the community have started adding the `-pac` suffix to the PAC's name, so e.g. `lpc82x` becomes `lpc82x-pac`.

This creates one new problem: What happens to the, now unused, suffix-less name? It's still the first thing that comes up in search results on [crates.io](https://crates.io/), so the user might accidentally be guided towards a deprecated version.

A solution to this problem is to create a placeholder crate that either fails to build, producing an informative compiler error. This repository contains these placeholder crates for the lpc-rs organization.
