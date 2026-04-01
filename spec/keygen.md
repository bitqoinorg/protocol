# Key Generation

## Requirements

- Both keys must be generated independently
- Neither key may be derived from the other
- Each key must be a valid Ed25519 keypair
- Keys should be generated using cryptographically secure randomness (CSPRNG)

## Procedure

1. Generate Key A using `nacl.sign.keyPair()` on device 1
2. Generate Key B using `nacl.sign.keyPair()` on device 2
3. Record the public key of each
4. The vault address is derived from Key A's public key (as the primary account owner)
5. Key B's public key is stored in vault metadata (off-chain, user-controlled)

## Security Considerations

- Keys must never be transmitted over a network in plaintext
- Keys should be stored encrypted at rest (AES-GCM recommended)
- Loss of either key results in permanent loss of vault access
- There is no recovery mechanism by design
