# Install PGB Node

This section explains how to prepare the server, install the official PGB node binary, and download the official PGB Public Testnet Chain Spec.

## 1. Connect to the Server

Connect to your Ubuntu server using SSH.

```bash
ssh root@YOUR_SERVER_IP
```

Replace `YOUR_SERVER_IP` with the public IP address of your server.

## 2. Update the Server

```bash
sudo apt update && sudo apt upgrade -y
```

## 3. Create PGB Directories

```bash
sudo mkdir -p /opt/pgb/bin
```

```bash
sudo mkdir -p /etc/pgb
```

```bash
sudo mkdir -p /var/lib/pgb
```

## 4. Download the Official PGB Node Binary

Download the official PGB node binary directly from the PGB GitHub Release:

```bash
sudo wget https://github.com/PGBOfficial/persian-gulf-blockchain/releases/download/testnet-v1.0.0/pgb-node -O /opt/pgb/bin/pgb-node
```

Make the node binary executable:

```bash
sudo chmod +x /opt/pgb/bin/pgb-node
```

## 5. Download the Official PGB Public Testnet Chain Spec

```bash
sudo wget https://github.com/PGBOfficial/persian-gulf-blockchain/releases/download/testnet-v1.0.0/pgb-testnet.json -O /etc/pgb/pgb-testnet.json
```

Only download validator files from official PGB sources.

## 6. Verify the PGB Node Installation

Run:

```bash
/opt/pgb/bin/pgb-node --version
```

If the installation is successful, the installed PGB node version will be displayed without errors.

## 7. Verify File Integrity

Verify the SHA256 checksum of the PGB node binary:

```bash
sha256sum /opt/pgb/bin/pgb-node
```

Expected SHA256:

```text
5ec66aa60ff4df56be96126f0b191bb5b1306d345286fc16b8421fd24595dd4d
```

Verify the SHA256 checksum of the PGB Public Testnet Chain Spec:

```bash
sha256sum /etc/pgb/pgb-testnet.json
```

Expected SHA256:

```text
b7ee39a857d80874d2e0ea86f172fe7edf0fc5c112a4dd9bb023a93dbc80362c
```

If the generated checksums match the expected values above, the downloaded files are authentic and unchanged.
