# ChainVue Skill for OpenClaw

Access the Verus blockchain through natural conversation with [OpenClaw](https://openclaw.ai).

## Installation

### Via ClawHub (Coming Soon)
```bash
npx clawhub@latest install chainvue
```

### Manual Installation
1. Clone this repo to your OpenClaw skills directory:
```bash
git clone https://github.com/chainvue/openclaw-chainvue-skill ~/.openclaw/skills/chainvue
```

2. Or paste this GitHub link directly into your OpenClaw chat.

## Usage

Once installed, just ask your OpenClaw assistant about Verus:

> "What's my VRSC balance at RXxx...?"

> "Look up the identity mike@"

> "Show me the top 10 VRSC holders"

> "What's the sync progress on mainnet?"

## Wallet Features (Optional)

Send transactions through natural conversation:

> "Create a new wallet called 'savings'"

> "Send 10 VRSC from my main wallet to RYzxxx..."

> "What's the address of my savings wallet?"

### How It Works

```
You: "Send 10 VRSC to mike@"
        │
        ▼
┌─────────────────────────────────────────────────┐
│  ChainVue API (remote)                          │
│  • Builds unsigned transaction                  │
│  • Fetches UTXOs                                │
└─────────────────────────────────────────────────┘
        │
        ▼
┌─────────────────────────────────────────────────┐
│  @chainvue/signer (local)                       │
│  • Signs with your private key                  │
│  • Keys never leave your machine                │
└─────────────────────────────────────────────────┘
        │
        ▼
┌─────────────────────────────────────────────────┐
│  ChainVue API (remote)                          │
│  • Broadcasts signed transaction                │
└─────────────────────────────────────────────────┘
        │
        ▼
Agent: "Sent! Transaction: abc123..."
```

**Your private keys never leave your machine.**

## Features

- **46 blockchain tools** via MCP protocol
- Query balances, transactions, identities, currencies
- Works on mainnet and testnet
- Real-time blockchain data
- **Local wallet signing** (keys stored in OS keychain)

## Configuration

By default, connects to the public ChainVue MCP endpoint.

For self-hosted or custom endpoints:
```bash
export CHAINVUE_MCP_URL=https://your-endpoint.com/sse
```

## Chain IDs

| Network | Chain ID |
|---------|----------|
| Mainnet | `i5w5MuNik5NtLcYmNzcvaoixooEebB6MGV` |
| Testnet | `iJhCezBExJHvtyH3fGhNnt2NhU4Ztkf2yq` |

## Wallet Tools

| Tool | Description |
|------|-------------|
| `list_wallets` | List all stored wallets |
| `create_wallet` | Create new wallet with generated key |
| `import_key` | Import existing private key (WIF) |
| `get_address` | Get wallet address |
| `sign_transaction` | Sign a transaction locally |
| `delete_wallet` | Remove a wallet |

## Links

- [ChainVue Explorer](https://chainvue.io)
- [ChainVue Signer](https://github.com/chainvue/chainvue-signer)
- [Verus Blockchain](https://verus.io)
- [OpenClaw](https://openclaw.ai)

## License

MIT
