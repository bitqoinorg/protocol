# Qonjoint Protocol Specification

Version: 0.1.0
Status: Draft

## Abstract

Qonjoint is a dual-key authorization protocol built on Solana.
Every transaction requires two independent keys to sign.
No single key, regardless of how it was obtained, can authorize a fund movement.

## Motivation

Classical blockchain wallets rely on a single private key.
If that key is stolen, compromised, or derived via a quantum attack, all funds are lost.
Qonjoint eliminates single-key risk entirely by requiring a second independent key
for every authorization. There is no bypass, no recovery shortcut, and no custodian.

## Key Properties

1. Dual-key requirement: both keys must sign every transaction
2. Non-custodial: keys never leave the user's devices
3. Quantum-aware: designed with post-quantum key derivation in mind
4. Solana-native: leverages Solana's account model and transaction structure
5. Stateless: no on-chain program required for the core protocol

## Terminology

- Vault: a Solana account whose authority is controlled by a Qonjoint keypair set
- Key A: the first independent keypair (device 1)
- Key B: the second independent keypair (device 2)
- Qonjoint session: an authorized signing session requiring both Key A and Key B
- Qoin: a vault instance protected by the Qonjoint protocol
