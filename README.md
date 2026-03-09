[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/t-SbtQf9)

# bitcoin-core-installation-assignment

Compile and run the integration tests and share the results.

---

# Answer

## Starting Bitcoin Core in Regtest Mode

I navigated to the Bitcoin Core directory and started the node in **regtest mode**.

```bash
cd bitcoin
./build/bin/bitcoind -regtest -daemon
```

Output:

```
Bitcoin Core starting
```

---

# Run Bitcoin Core v30 and use at least 5 RPC commands

## Bitcoin Core RPC Commands

### 1. getblockchaininfo

```bash
./build/bin/bitcoin-cli -regtest getblockchaininfo
```

Output:

```json
{
  "chain": "regtest",
  "blocks": 0,
  "headers": 0,
  "bestblockhash": "0f9188f13cb7b2c71f2a335e3a4fc328bf5beb436012afca590b1a11466e2206",
  "difficulty": 4.656542373906925e-10,
  "verificationprogress": 2.099285193601507e-06,
  "initialblockdownload": true,
  "size_on_disk": 293,
  "pruned": false
}
```

---

### 2. getnetworkinfo

```bash
./build/bin/bitcoin-cli -regtest getnetworkinfo
```

Output:

```json
{
  "version": 309900,
  "subversion": "/Satoshi:30.99.0/",
  "protocolversion": 70016,
  "networkactive": true,
  "connections": 0
}
```

This shows the node is running Bitcoin Core v30 and currently has no connected peers.

---

### 3. getpeerinfo

```bash
./build/bin/bitcoin-cli -regtest getpeerinfo
```

Output:

```json
[]
```

This means there are currently **no connected peers** in the regtest network.

---

### 4. getwalletinfo

```bash
./build/bin/bitcoin-cli -regtest getwalletinfo
```

Output:

```json
{
  "walletname": "testwallet",
  "walletversion": 169900,
  "format": "sqlite",
  "txcount": 0,
  "keypoolsize": 4000,
  "private_keys_enabled": true
}
```

This confirms the wallet **testwallet** is loaded successfully.

---

### 5. Generate blocks and check block count

I generated blocks in **regtest mode**.

Generate blocks:

```bash
./build/bin/bitcoin-cli -regtest -generate 101
```

Check block count:

```bash
./build/bin/bitcoin-cli -regtest getblockcount
```

Output:

```
101
```

This confirms that **101 blocks were successfully generated** on the regtest blockchain.

---

# Conclusion

In this assignment, I successfully:

- Installed and compiled Bitcoin Core v30
- Started a Bitcoin node in regtest mode
- Executed multiple RPC commands
- Generated blocks locally for testing
- Retrieved blockchain, network, peer, and wallet information

This demonstrates basic interaction with Bitcoin Core using the `bitcoin-cli` interface.