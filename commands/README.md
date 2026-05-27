# Claude Command Guide

This directory contains the `/trading-ideas` local command for Claude Code.

## Installation

### Quick Install

Download the command directly from the current repository:

```bash
curl -o ~/.claude/commands/trading-ideas.md https://raw.githubusercontent.com/vortezwohl/equity-research/main/commands/trading-ideas/commands/research.md
```

### Manual Install

```bash
git clone https://github.com/vortezwohl/equity-research.git
cd equity-research
cp commands/trading-ideas/commands/research.md ~/.claude/commands/trading-ideas.md
```

## Usage

When installed as a local command file, invoke it as:

```bash
/trading-ideas AAPL
/trading-ideas NVDA --detailed
```

If you install through Claude's plugin marketplace instead, the namespaced command is:

```bash
/trading-ideas:research AAPL
```

## What This Command Produces

- Executive summary with BUY / SELL / HOLD framing
- Fundamental analysis with concrete metrics
- Catalyst analysis across multiple time horizons
- Bull, base, and bear valuation scenarios
- Risk assessment with position sizing guidance
- Technical context, options flow, and insider activity

## Updating

Refresh the local command from the canonical repository:

```bash
curl -o ~/.claude/commands/trading-ideas.md https://raw.githubusercontent.com/vortezwohl/equity-research/main/commands/trading-ideas/commands/research.md
```

## Support

- Repository: [vortezwohl/equity-research](https://github.com/vortezwohl/equity-research)
- Issues: [GitHub Issues](https://github.com/vortezwohl/equity-research/issues)
- Documentation: [docs](../docs/)

This command is for educational and research purposes only and is not financial advice.
