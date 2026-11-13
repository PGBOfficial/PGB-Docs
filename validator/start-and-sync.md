# Start and Sync Validator Node

After inserting all six session keys, the validator node can be started and synchronized with the PGB Public Testnet.

The validator will run continuously on the server and does not require your local computer or SSH connection to remain active.

## 1. Set Your Validator Name

Choose a name for your validator.

Replace `YOURNAME` with your preferred validator name:

```bash
VALIDATOR_NAME="PGB-Validator-YOURNAME"
```

Example:

```bash
VALIDATOR_NAME="PGB-Validator-Alice"
```

## 2. Create the Validator Service

Copy and run the following command:

```bash
sudo tee /etc/systemd/system/pgb-validator.service > /dev/null <<EOF
[Unit]
Description=PGB Validator
After=network-online.target
Wants=network-online.target

[Service]
Type=simple
User=root
ExecStart=/opt/pgb/bin/pgb-node --chain /etc/pgb/pgb-testnet.json --base-path /var/lib/pgb --validator --force-authoring --name ${VALIDATOR_NAME} --port 30333
Restart=always
RestartSec=5
LimitNOFILE=65536

[Install]
WantedBy=multi-user.target
EOF
```

## 3. Start the Validator Node

Reload systemd, enable the validator service, and start the node:

```bash
sudo systemctl daemon-reload && sudo systemctl enable --now pgb-validator.service
```

The validator node is now running as a background service on the server.

The service will also start automatically after a server reboot.

## 4. Check Validator Status

Run:

```bash
sudo systemctl status pgb-validator.service --no-pager
```

The service should show:

```text
active (running)
```

If `active (running)` is displayed, the validator node has started successfully.

## 5. Monitor Synchronization

Open the live validator logs:

```bash
journalctl -u pgb-validator.service -f
```

During the initial synchronization, the logs may show output similar to:

```text
Syncing, target=#490053 (3 peers), best: #1536, finalized #1024
```

`Syncing` means that the validator is still downloading and synchronizing blockchain data.

The `best` and `finalized` block numbers should continue increasing as synchronization progresses.

Keep the logs open until synchronization is complete.

When the validator has synchronized with the PGB Public Testnet, the logs may show output similar to:

```text
Idle (3 peers), best: #490563, finalized #490561
```

`Idle` with connected peers and `best` / `finalized` block numbers at the current network height indicates that the node is synchronized and following the network.

The exact block numbers and number of peers will be different and will change over time.

## 6. Exit the Live Logs

After confirming synchronization, press:

```text
Ctrl+C
```

This only closes the live log view.

It does **not** stop the validator node.

The validator continues running on the server in the background.

## 7. Confirm the Validator Is Still Running

Run:

```bash
sudo systemctl status pgb-validator.service --no-pager
```

The service should still show:

```text
active (running)
```

You can now close the SSH connection or turn off your local computer.

The validator will continue running on the server.

## Important

Do not proceed to bonding or validator registration until the validator node is fully synchronized with the PGB Public Testnet.

The validator server should remain online continuously.

Closing SSH or turning off your local computer will not stop the validator.

If the server is rebooted, the validator service will start automatically.
