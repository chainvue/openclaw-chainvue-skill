# ChainVue - Verus Blockchain Assistant

A skill for OpenClaw that provides access to the Verus blockchain via the ChainVue API.

## Description

ChainVue gives you real-time access to the Verus blockchain. Query balances, track transactions, monitor identities, explore currencies, and send transactions - all through natural conversation.

## Capabilities

- **Address Balances**: Check VRSC and token balances for any address
- **Transaction History**: View transaction history for addresses
- **VerusID Lookup**: Search and inspect Verus identities
- **Currency Info**: Get prices, reserves, and holder counts for currencies
- **Block Explorer**: Query blocks, transactions, and chain statistics
- **Whale Alerts**: Find large UTXO movements
- **Rich Lists**: See top holders for any currency
- **Wallet Management**: Create wallets, import keys, send transactions

## Example Prompts

### Reading Blockchain Data
- "What's the VRSC balance for RAddress...?"
- "Show me the transaction history for my address"
- "Look up the identity mike@"
- "What's the current price of Bridge.vETH?"
- "Show me the top 10 VRSC holders"
- "What was the block reward for block 1000000?"
- "How many blocks are synced on mainnet?"

### Wallet & Transactions
- "Create a new wallet called 'savings'"
- "What wallets do I have?"
- "What's the address of my main wallet?"
- "Send 10 VRSC from my main wallet to RYzxxx..."
- "Import this private key as 'trading'"

## Configuration

This skill connects to:
1. **ChainVue MCP Gateway** (remote) - blockchain data and transaction broadcasting
2. **ChainVue Signer** (local) - secure key storage and transaction signing

### Environment Variables (Optional)

```bash
CHAINVUE_MCP_URL=https://mcp.chainvue.io/sse  # Default public endpoint
```

### Chain IDs

| Network | Chain ID |
|---------|----------|
| Verus Mainnet | `i5w5MuNik5NtLcYmNzcvaoixooEebB6MGV` |
| Verus Testnet | `iJhCezBExJHvtyH3fGhNnt2NhU4Ztkf2yq` |

## Available Tools (52)

### Network & Blocks
- `get_networks` - List all active Verus networks
- `get_block` - Get block by height or hash
- `get_recent_blocks` - Get recent blocks
- `get_top_blocks` - Blocks sorted by tx count, size, or difficulty
- `get_block_range_stats` - Aggregate stats for block range
- `search_blocks` - Filter blocks by criteria
- `get_coinbase_reward` - Block reward details
- `get_sync_progress` - Sync status with percentage

### Addresses & Balances
- `get_address_balance` - All currency balances for address
- `get_address_info` - Detailed address statistics
- `get_address_transactions` - Transaction history
- `get_utxos` - UTXOs for an address
- `get_rich_list` - Top holders for currency
- `get_whale_movements` - Large transfers

### Identities (VerusID)
- `get_identity` - Get identity by name or i-address
- `search_identities` - Search identities
- `get_identity_history` - Version history
- `get_new_identities` - Recently created
- `get_revoked_identities` - Revoked identities

### Currencies
- `get_currencies` - List all currencies
- `get_currency` - Currency details
- `get_currency_state` - Current price and reserves
- `get_currency_price_history` - Historical prices
- `get_basket_currencies` - Reserve currencies

### Transactions
- `get_transaction` - Transaction by txid
- `get_transaction_details` - Full tx with inputs/outputs/fee
- `build_unsigned_tx` - Build transaction for signing
- `send_raw_transaction` - Broadcast signed transaction
- `decode_raw_transaction` - Decode raw tx hex

### Wallet (Local Signer)
- `list_wallets` - List all stored wallets
- `create_wallet` - Create new wallet with generated key
- `import_key` - Import existing private key (WIF format)
- `get_address` - Get wallet address
- `sign_transaction` - Sign a transaction locally
- `delete_wallet` - Remove a wallet from storage

## Security

**Your private keys never leave your machine.**

The skill uses two MCP servers:
- **ChainVue API** (remote): Handles blockchain queries and broadcasting
- **ChainVue Signer** (local): Stores keys in OS keychain, signs locally

```
Transaction Flow:
1. Agent calls ChainVue API to build unsigned tx
2. Agent calls local Signer to sign (key never sent)
3. Agent calls ChainVue API to broadcast signed tx
```

## Links

- [ChainVue](https://chainvue.io) - Blockchain Explorer
- [ChainVue Signer](https://github.com/chainvue/chainvue-signer) - Local Signing
- [Verus](https://verus.io) - Verus Blockchain
- [API Docs](https://chainvue.io/docs) - GraphQL API Documentation

## Author

ChainVue Team
