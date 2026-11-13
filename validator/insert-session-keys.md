# Insert Session Keys

This section explains how to insert the six validator session keys generated in the previous step into the PGB validator node keystore.

Each session key must be inserted separately using its corresponding key type and cryptographic scheme.

## 1. Insert GRANDPA Key

```bash
/opt/pgb/bin/pgb-node key insert \
  --base-path /var/lib/pgb \
  --chain /etc/pgb/pgb-testnet.json \
  --scheme Ed25519 \
  --key-type gran \
  --suri "YOUR_GRANDPA_SECRET_PHRASE"
```

## 2. Insert BABE Key

```bash
/opt/pgb/bin/pgb-node key insert \
  --base-path /var/lib/pgb \
  --chain /etc/pgb/pgb-testnet.json \
  --scheme Sr25519 \
  --key-type babe \
  --suri "YOUR_BABE_SECRET_PHRASE"
```

## 3. Insert ImOnline Key

```bash
/opt/pgb/bin/pgb-node key insert \
  --base-path /var/lib/pgb \
  --chain /etc/pgb/pgb-testnet.json \
  --scheme Sr25519 \
  --key-type imon \
  --suri "YOUR_IMONLINE_SECRET_PHRASE"
```

## 4. Insert Authority Discovery Key

```bash
/opt/pgb/bin/pgb-node key insert \
  --base-path /var/lib/pgb \
  --chain /etc/pgb/pgb-testnet.json \
  --scheme Sr25519 \
  --key-type audi \
  --suri "YOUR_AUTHORITY_DISCOVERY_SECRET_PHRASE"
```

## 5. Insert Mixnet Key

```bash
/opt/pgb/bin/pgb-node key insert \
  --base-path /var/lib/pgb \
  --chain /etc/pgb/pgb-testnet.json \
  --scheme Sr25519 \
  --key-type mixn \
  --suri "YOUR_MIXNET_SECRET_PHRASE"
```

## 6. Insert BEEFY Key

```bash
/opt/pgb/bin/pgb-node key insert \
  --base-path /var/lib/pgb \
  --chain /etc/pgb/pgb-testnet.json \
  --scheme Ecdsa \
  --key-type beef \
  --suri "YOUR_BEEFY_SECRET_PHRASE"
```

## Important

Use the corresponding secret phrase generated for each session key in the previous step.

Do not reuse one secret phrase for multiple session key types.

Never share validator secret phrases or private keys with PGB or any third party.

After all six session keys have been inserted successfully, the validator node can proceed to the node startup and synchronization stage.
