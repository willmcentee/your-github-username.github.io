# your-github-username.github.io

## Alpaca MCP Server Setup

This repository is configured with the [Alpaca MCP server](https://pypi.org/project/alpaca-mcp-server/) as a project-scoped MCP server via [`.mcp.json`](.mcp.json). When you open this project in Claude Code (or another MCP-aware client that reads `.mcp.json`), the Alpaca trading tools become available automatically.

### Prerequisites

- [`uv`](https://docs.astral.sh/uv/) installed (`uvx` is used to run the server without a permanent install)
- An [Alpaca](https://alpaca.markets/) account with API keys (paper trading keys work too)

### Configuration

The config references your API keys through environment variables so no secrets are committed to the repository. Set them in your shell before starting Claude Code:

```sh
export ALPACA_API_KEY="your_alpaca_api_key"
export ALPACA_SECRET_KEY="your_alpaca_secret_key"
```

Add those lines to your shell profile (e.g. `~/.zshrc` or `~/.bashrc`) to make them persistent.

### Verifying

Run `claude` in this directory, approve the project MCP server when prompted, then run `/mcp` to confirm the `alpaca` server is connected and its tools are listed.

> **Note:** Never hardcode real API keys in `.mcp.json` — this file is committed to the repository. Always use the `${VAR}` environment-variable references shown above.
