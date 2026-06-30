## Chainflip Broker as a Service

A remote MCP server that enables AI agents to perform cross-chain cryptocurrency swaps through the [Chainflip](https://chainflip.io) decentralized exchange. No API key required to get started.

### Tools

| Tool | Description |
|---|---|
| `list_assets` | Discover all available assets with tickers, networks, decimals, minimum amounts, and live USD prices |
| `get_quotes` | Get swap quotes using human-readable amounts (e.g., 1.5 BTC) |
| `get_native_quotes` | Get swap quotes using native unit amounts (e.g., 150000000 satoshis) |
| `start_swap` | Execute a cross-chain swap and receive a deposit address |
| `start_dca_swap` | Execute a DCA swap that splits into multiple sub-swaps to reduce price impact on large trades |
| `check_status` | Track swap progress through its stages: Waiting, Receiving, Swapping, Sending, Sent, Completed |

### Prompts

| Prompt | Description |
|---|---|
| `swap-assistant` | Guided workflow that walks through asset discovery, quoting, swap execution, and status monitoring |

### Supported Assets

Assets are identified as `ticker.network`, for example `btc.btc`, `eth.eth`, `usdc.eth`, `sol.sol`, or `usdt.tron`. Call `list_assets` to see the full list of supported assets and their current prices.

### Configuration

Connect to the remote MCP server at:

```
https://chainflip-broker.io/mcp
```

Transport: Streamable HTTP

No authentication is required. An optional API key can be provided for partner attribution.

### Documentation

For detailed human-readable documentation, visit [docs.chainflip-broker.io/resources/ai-documentation](https://docs.chainflip-broker.io/resources/ai-documentation/).

### Usage Example

1. Call `list_assets` to see available assets
2. Call `get_quotes` with source asset, destination asset, and amount to preview the swap
3. Call `start_swap` with the destination and refund addresses to get a deposit address
4. Send funds to the deposit address
5. Call `check_status` with the returned swap ID to monitor progress
