# Threat Model

## In Scope

### Single Key Compromise
An attacker obtains Key A or Key B (but not both) via:
- Malware or keylogger on one device
- Physical device theft
- Quantum computing attack on one public key
- Social engineering or phishing targeting one key

Qonjoint mitigation: the attacker cannot sign transactions without the second key.
Both keys are always required. There is no workaround.

### Network Interception
An attacker intercepts a partially-signed transaction.
Qonjoint mitigation: a partially-signed transaction is invalid and cannot be broadcast.

## Out of Scope

### Both Keys Compromised Simultaneously
If an attacker obtains both Key A and Key B, the vault can be drained.
Mitigation is at the operational security level (keep devices separate and air-gapped).

### Solana Network Failure
Protocol-level failures (validator bugs, consensus issues) are outside this spec.

### Smart Contract Bugs
Qonjoint core does not rely on on-chain programs. Token program bugs are out of scope.
