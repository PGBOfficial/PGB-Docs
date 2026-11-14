# Validator Operations and Security

This document defines the general operational and security requirements for validators participating in the **PGB Public Testnet**.

The purpose of the Public Testnet is to evaluate validator participation, network stability, staking behavior, rewards, security, and economic parameters under real network conditions.

The policies described here apply specifically to the Public Testnet and may be updated as testing progresses.

## 1. Validator Responsibilities

PGB Public Testnet Validators are expected to:

- Keep their Validator Node online and synchronized with the network.
- Maintain a stable internet connection and sufficient server resources.
- Monitor their node and validator status regularly.
- Follow important PGB network and Runtime upgrade announcements.
- Maintain the security of their validator infrastructure.
- Report significant technical or security issues discovered during testing.

## 2. Validator Bond

The current required Bond for an approved external Validator on the PGB Public Testnet is:

**100,000 PGC**

Testnet PGC has no monetary value and is provided solely for testing and network participation.

The Testnet Bond requirement may be adjusted based on network conditions, testing results, and validator feedback.

## 3. Validator Key Security

Validators are fully responsible for protecting their account credentials and Validator Session Keys.

Validators must never share:

- Recovery phrases
- Private keys
- Account passwords
- Validator Session Key secret phrases
- Server credentials

PGB will never request these private credentials.

Only the required **public Session Keys Hex** is registered on-chain.

## 4. Validator Node Security

Validators should maintain appropriate security practices for their server and node.

This includes:

- Restricting unnecessary server access.
- Keeping the operating system and required software updated.
- Protecting SSH access.
- Avoiding unnecessary public exposure of sensitive RPC methods.
- Monitoring server resources and node logs.
- Maintaining sufficient disk space, memory, CPU, and network connectivity.

## 5. Session Keys and Validator Operation

The same active Validator Session Keys must not be used simultaneously on multiple active Validator Nodes.

Running the same validator identity or Session Keys on multiple active instances may cause conflicting consensus behavior, including equivocation.

Validators migrating to a new server should ensure that the previous Validator instance is no longer actively validating before using the same keys on the replacement server.

## 6. Availability and Network Participation

Validators should maintain reliable uptime and remain synchronized with the PGB network.

Temporary downtime caused by maintenance or technical issues may occur.

However, extended downtime, repeated instability, serious misconfiguration, consensus offences, or behavior that affects network stability may result in temporary deactivation or removal from the active Validator set during the Public Testnet.

## 7. Rewards, Slashing and Economic Parameters

Validator rewards, staking behavior, offences, and slashing mechanisms operate according to the current PGB Testnet Runtime configuration.

During the Public Testnet, these mechanisms will be monitored and evaluated under real validator participation.

At this stage, PGB does not define the current Testnet parameters as the final economic policy of the network.

Parameters including:

- Validator rewards
- Validator commission policy
- Bond requirements
- Uptime requirements
- Slashing policy
- Staking parameters
- Validator participation requirements

may be adjusted during or after the Public Testnet based on actual network results and validator feedback.

## 8. Public Testnet Policy

The PGB Public Testnet is an evaluation and testing environment before the final network policies are established.

Validators participating in the Public Testnet contribute directly to evaluating network stability, security, staking, validator operations, and economic behavior.

**After completion of the PGB Public Testnet, the collected network data, validator performance, security results, staking behavior, economic tests, and validator feedback will be reviewed. Based on these results, PGB will establish and publish the final validator rules, reward policies, staking parameters, security requirements, and network economic policies applicable to the next stages of the network.**

Public Testnet participation does not automatically establish or guarantee the same validator conditions, rewards, Bond requirements, or economic parameters for Mainnet.
