# ChainVue - Verus Blockchain Assistant

A skill for OpenClaw that provides access to the Verus blockchain via the ChainVue API.

## Description

ChainVue gives you real-time access to the Verus blockchain. Query balances, track transactions, monitor identities, and explore currencies - all through natural conversation.

## Capabilities

- **Address Balances**: Check VRSC and token balances for any address
- **Transaction History**: View transaction history for addresses
- **VerusID Lookup**: Search and inspect Verus identities
- **Currency Info**: Get prices, reserves, and holder counts for currencies
- **Block Explorer**: Query blocks, transactions, and chain statistics
- **Whale Alerts**: Find large UTXO movements
- **Rich Lists**: See top holders for any currency

## Example Prompts

- "What's the VRSC balance for RAddress...?"
- "Show me the transaction history for my address"
- "Look up the identity mike@"
- "What's the current price of Bridge.vETH?"
- "Show me the top 10 VRSC holders"
- "What was the block reward for block 1000000?"
- "How many blocks are synced on mainnet?"

## Configuration

This skill connects to the ChainVue MCP Gateway. By default it uses the public endpoint.

### Environment Variables (Optional)

```bash
CHAINVUE_MCP_URL=https://mcp.chainvue.io/sse  # Default public endpoint
```

### Chain IDs

| Network | Chain ID |
|---------|----------|
| Verus Mainnet | `i5w5MuNik5NtLcYmNzcvaoixooEebB6MGV` |
| Verus Testnet | `iJhCezBExJHvtyH3fGhNnt2NhU4Ztkf2yq` |

## Available Tools (45)

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
- `send_raw_transaction` - Broadcast signed transaction
- `decode_raw_transaction` - Decode raw tx hex

## Links

- [ChainVue](https://chainvue.io) - Blockchain Explorer
- [Verus](https://verus.io) - Verus Blockchain
- [API Docs](https://chainvue.io/docs) - GraphQL API Documentation

## Author

ChainVue Team
