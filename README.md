# Hearthstone Sim

Hearthstone Sim is a **Hearthstone simulator** you add to Claude, ChatGPT, Cursor, or VS Code. Paste a deck code and ask: Is this a legal Standard list? How often do I keep this card after mulligan? Goldfish this curve.

Operated by **FMF Tools**.

- Live site: https://hearthstone-sim.fmf-x402.workers.dev/
- MCP endpoint (Streamable HTTP): https://hearthstone-sim.fmf-x402.workers.dev/mcp
- Install page: https://hearthstone-sim.fmf-x402.workers.dev/install
- Tools and prices: https://hearthstone-sim.fmf-x402.workers.dev/docs

No account is required. `tools/list`, deck check, and opening-hand odds are free. Paid sims are charged per successful call through MPP on Tempo or x402 on Base (USDC). Bad input is refused and is not charged.

## Install

MCP server URL: `https://hearthstone-sim.fmf-x402.workers.dev/mcp`

### Claude Desktop

Settings → Connectors → Add custom connector → URL: `https://hearthstone-sim.fmf-x402.workers.dev/mcp`

Or add this to `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "hearthstone-sim": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://hearthstone-sim.fmf-x402.workers.dev/mcp"]
    }
  }
}
```

### Claude Code

```bash
claude mcp add --transport http hearthstone-sim https://hearthstone-sim.fmf-x402.workers.dev/mcp
```

### Cursor

`~/.cursor/mcp.json` (or `.cursor/mcp.json` in a project):

```json
{
  "mcpServers": {
    "hearthstone-sim": {
      "url": "https://hearthstone-sim.fmf-x402.workers.dev/mcp"
    }
  }
}
```

### VS Code (Copilot agent mode)

```bash
code --add-mcp '{"name":"hearthstone-sim","type":"http","url":"https://hearthstone-sim.fmf-x402.workers.dev/mcp"}'
```

### ChatGPT

Settings → Apps & Connectors → Advanced settings → turn on Developer mode → Create connector. Name: Hearthstone Sim. MCP server URL: `https://hearthstone-sim.fmf-x402.workers.dev/mcp`. Authentication: none.

## Tools

| MCP tool | Price |
|---|---|
| hs_deck_check | free |
| hs_opening_hand_odds | free |
| hs_draw_odds | $0.001 |
| hs_mulligan_odds | $0.001 |
| hs_curve_goldfish | $0.003 |

## Licence and fan notice

This repository is MIT licensed. Hearthstone Sim is an unofficial fan tool, not affiliated with or endorsed by Blizzard Entertainment. Hearthstone and card names are trademarks of Blizzard Entertainment. Card data comes from HearthstoneJSON. Card data tools are free. Paid tools sell only our own computation and return no card data.

Contact: fmf-tools@agentmail.to
