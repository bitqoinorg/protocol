# Transaction Signing

## Overview

A Qonjoint transaction is a standard Solana transaction that has been signed
by both Key A and Key B before broadcast.

## Procedure

1. Construct the Solana transaction (transfer, token transfer, etc.)
2. Serialize the transaction to bytes
3. Sign the serialized transaction with Key A
4. Sign the same serialized transaction with Key B
5. Attach both signatures to the transaction
6. Broadcast to the Solana network

## Signature Verification

Any observer can verify a Qonjoint transaction by:
1. Extracting both signatures from the transaction
2. Verifying Signature A against Key A's public key
3. Verifying Signature B against Key B's public key
4. Confirming both verifications pass

## Invalid States

- Transaction with only Signature A: rejected
- Transaction with only Signature B: rejected
- Transaction with neither signature: rejected
- Transaction where either signature is invalid: rejected
