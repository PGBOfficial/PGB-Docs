# Install PGB Node

This section explains how to prepare the server, install the PGB node binary, and add the official PGB Public Testnet Chain Spec.

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

## 4. Download the Official PGB Files

The following files are required:

**PGB Node Binary**

Download link: Coming soon

**PGB Public Testnet Chain Spec**

Download link: Coming soon

Only download validator files from official PGB sources.

## 5. Install the PGB Node Binary

Place the downloaded `pgb-node` binary in:

```text
/opt/pgb/bin/pgb-node
```

Make the node binary executable:

```bash
sudo chmod +x /opt/pgb/bin/pgb-node
```

## 6. Install the PGB Public Testnet Chain Spec

Place the downloaded Chain Spec file in:

```text
/etc/pgb/pgb-testnet.json
```

## 7. Verify the PGB Node Installation

Run:

```bash
/opt/pgb/bin/pgb-node --version
```

If the installation is successful, the installed PGB node version will be displayed without errors.
