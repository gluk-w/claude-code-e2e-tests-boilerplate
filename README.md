# Boilerplate for E2E tests with Claude Code
A simple way to get started E2E tests for websites with Claude Code. 
This boilerplate contains
- [package.json](package.json) with basic requirements
- [CLAUDE.md](CLAUDE.md) with instructions
- [.mcp.json](.mcp.json) - list of MCP servers

## Prerequisites
- Node.js 18 or higher
- npm (Node Package Manager)
- Active billing account with Anthropic or Claude Max subscription

### Claude Code
If you haven't already, install Claude Code and complete the one-time OAuth process with
your Claude Max or Anthropic Console account
```bash
npm install -g @anthropic-ai/claude-code
```

## Installation
```bash
claude -p "Setup the project"
```

## Writing tests
Open `claude` and tell it what you want to be tested. The best strategy is to supply 
a numbered list of step. E.g. 
```text
1. Open clutch.co
2. Select a service from the "Search web developers, SEO, UX..." dropdown 
3. Make sure locations are populated in the "Any location"
4. Pick the first location from "Nearby locations" section of the dropdown and note its name
5. Click "Get Started"
6. Make sure you are redirected to the webpage for that service line and location
```

Claude Code will start analyzing the web page using Playwright MCP, guess what elements
it needs to interact with, generate test code and run it until all checks pass. 
Just approve the commands when prompted and review the results after a few minutes.

## Best practices
...

## Contributions
Pull requests are welcome!