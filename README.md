# Vess — Cuckatoo27 PoW-mintable ERC-20 (Arbitrum Stylus)

Rust [Stylus](https://docs.arbitrum.io/stylus/stylus-quickstart) contract for the
Vess token on Arbitrum One.

- **Chain**: Arbitrum One (mainnet)
- **Deployed contract**: `0x00609432cb4ad6a72d7b07e279c27ddcb4682ba4`
- **Compiler**: cargo-stylus `0.10.7` / stylus:0.10.7, Rust `1.97.1`
- **Verification layout**: this repository's root IS the contract project (the
  same layout used by the reproducible Docker build at `/source`), so the
  on-chain `project_hash` matches.

## Minting

VESS is minted by solving a Cuckatoo27 proof-of-work graph against the contract's
chain-bound difficulty. The miner lives in the main
[ohmictech/vess](https://github.com/ohmictech/vess) repo and reads `miner.toml`.

## Layout

- `src/lib.rs` — contract entrypoint (`Vess`), ERC-20 + PoW mint
- `vess-crypto/` — vendored Cuckatoo27 verification crate (path dependency)
- `Stylus.toml` — cargo-stylus workspace/contract manifest
- `rust-toolchain.toml` — pins Rust 1.97.1 for reproducible builds
