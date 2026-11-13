# Generate Validator Keys

This section explains how to generate the session keys required to operate a validator node on the PGB Public Testnet.

PGB validators use multiple session keys for consensus, finality, validator availability, authority discovery, mixnet operation, and BEEFY.

## Required Validator Session Keys

The following session keys are required:

- BABE — Sr25519
- GRANDPA — Ed25519
- ImOnline — Sr25519
- Mixnet — Sr25519
- Authority Discovery — Sr25519
- BEEFY — ECDSA

## Generate BABE Key

```bash
subkey generate --scheme Sr25519
```

Save the generated secret phrase and public key securely.

## Generate GRANDPA Key

```bash
subkey generate --scheme Ed25519
```

Save the generated secret phrase and public key securely.

## Generate ImOnline Key

```bash
subkey generate --scheme Sr25519
```

Save the generated secret phrase and public key securely.

## Generate Mixnet Key

```bash
subkey generate --scheme Sr25519
```

Save the generated secret phrase and public key securely.

## Generate Authority Discovery Key

```bash
subkey generate --scheme Sr25519
```

Save the generated secret phrase and public key securely.

## Generate BEEFY Key

```bash
subkey generate --scheme Ecdsa
```

Save the generated secret phrase and public key securely.

## Important

Each validator session key must be generated separately.

Do not reuse the same secret phrase for multiple session key roles.

Validator secret phrases and private keys must never be published, uploaded to GitHub, or shared with PGB.

The generated keys will be inserted into the validator node keystore in the next step.
