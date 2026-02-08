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

## Features

- **45 blockchain tools** via MCP protocol
- Query balances, transactions, identities, currencies
- Works on mainnet and testnet
- Real-time blockchain data

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

## Links

- [ChainVue Explorer](https://chainvue.io)
- [Verus Blockchain](https://verus.io)
- [OpenClaw](https://openclaw.ai)

## License

MIT
