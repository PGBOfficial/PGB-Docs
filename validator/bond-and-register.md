# Bond and Submit Validator Request

After your validator node is running and fully synchronized with the PGB Testnet, the next step is to create your validator account, receive Testnet PGC, bond the required amount, register your Session Keys Hex on-chain, and submit your validator request.

The six validator session keys must already be generated and inserted into your validator node as described in the previous steps.

## 1. Create Your Validator Account

Install the **Polkadot.js Extension** in your browser.

Open the extension and select:

**Create new account**

Create a new account for your PGB Validator.

During account creation:

1. Save your recovery phrase securely and offline.
2. Choose a name for the account.
3. Set a strong password.
4. Complete the account creation.

> Never share your recovery phrase, private key, password, or validator secret phrases with PGB or any third party.

## 2. Add Your Account to PGB Explorer

Open the PGB Explorer:

**https://explorer.persiangulfchain.com**

Make sure the Polkadot.js Extension is enabled.

Navigate to:

**Accounts → My Accounts**

Allow the Explorer to access your extension accounts when requested.

Your validator account should now appear under **My Accounts**.

## 3. Submit Your Account Address to PGB

Copy the public address of your validator account from **My Accounts**.

Send this public address to PGB for validator approval.

Only your public account address is required.

## 4. Receive Testnet PGC

After your validator request is approved, PGB will transfer:

**100,100 PGC**

to your approved account.

Current Testnet allocation:

- **100,000 PGC** — Validator Bond
- **100 PGC** — Available for transaction fees and validator operations

Testnet PGC has no monetary value.

The required Testnet Bond may be adjusted in the future based on Public Testnet results and validator feedback.

## 5. Verify Your Balance

Navigate to:

**Accounts → My Accounts**

Confirm that the Testnet PGC has arrived before continuing.

## 6. Bond Your PGC

Navigate to:

**Network → Staking → Accounts**

Select:

**+ Stash**

Select the validator account that received the Testnet PGC.

Enter:

**100,000 PGC**

as the Bond amount.

For:

**Reward Destination**

select:

**Staked**

Keep the remaining PGC available for transaction fees and validator operations.

Review the information, sign the transaction using your Polkadot.js account, and submit it.

Wait until the Bond transaction is finalized.

## 7. Verify Your Bond

Return to:

**Network → Staking → Accounts**

Confirm that your account shows the bonded amount correctly.

Your validator account is now bonded.

## 8. Register Your Session Keys Hex

Your six Session Keys were already generated and inserted into your validator node during the previous setup steps.

You should also have the **Session Keys Hex** associated with those six keys.

The Hex is a long value beginning with:

`0x...`

Now register this Hex on-chain using your bonded validator account.

In the PGB Explorer navigate to:

**Developer → Extrinsics**

Then:

1. Select your bonded Validator account under **using the selected account**.
2. Under **submit the following extrinsic**, select:

   **`session`**

3. Select the function:

   **`setKeys(keys, proof)`**

4. In the **keys** field, paste your complete Session Keys Hex beginning with:

   **`0x...`**

5. In the **proof** field, enter:

   **`0x`**

6. Carefully verify the account and Session Keys Hex.
7. Select **Submit Transaction**.
8. Sign the transaction using your Polkadot.js Extension.
9. Wait until the transaction is finalized.

> Do not modify, shorten, or separate the Session Keys Hex.

## 9. Submit Your Validator Request

After the Session Keys Hex has been registered successfully, remain in:

**Developer → Extrinsics**

Using the same bonded Validator account:

1. Select:

   **`staking`**

2. Select:

   **`validate(prefs)`**

3. Set your Validator preferences as required by the current PGB Testnet validator policy.
4. Review the transaction.
5. Select **Submit Transaction**.
6. Sign using your Validator account.
7. Wait until the transaction is finalized.

## 10. Final Verification

Confirm that:

- Your Validator Node is online.
- Your node is fully synchronized.
- **100,000 PGC** is bonded.
- Your Session Keys Hex has been registered through `session.setKeys`.
- Your `staking.validate` transaction has been finalized.
- Your Validator account appears correctly in the PGB Staking interface.

Your PGB Testnet Validator registration request is now complete.

PGB will review the validator status before activation in the active validator set.
