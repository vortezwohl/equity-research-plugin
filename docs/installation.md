# Installation Guide

Complete setup instructions for installing the Equity Research plugin and command from `vortezwohl/equity-research`.

## Installation Paths

This repository supports three installation paths:

1. Claude marketplace plugin
2. Claude local command file
3. Codex local plugin skill

## Claude Marketplace Plugin

Recommended when you want the command managed by Claude's plugin system.

```bash
/plugin marketplace add vortezwohl/equity-research
/plugin install trading-ideas@equity-research-marketplace
```

Verification:

```bash
/help
/trading-ideas:research AAPL
```

## Claude Local Command File

Recommended when you only need a standalone local command.

### Direct Download

```bash
curl -o ~/.claude/commands/trading-ideas.md https://raw.githubusercontent.com/vortezwohl/equity-research/main/commands/trading-ideas/commands/research.md
```

### Repository Clone

```bash
git clone https://github.com/vortezwohl/equity-research.git
cd equity-research
cp commands/trading-ideas/commands/research.md ~/.claude/commands/trading-ideas.md
```

Verification:

```bash
/trading-ideas AAPL
```

## Codex Local Plugin Skill

Codex discovers the plugin through the repository root:

- `.codex-plugin/plugin.json`
- `skills/equity-research/SKILL.md`

Install locally:

```bash
git clone https://github.com/vortezwohl/equity-research.git
cd equity-research
```

Then add the repository root to Codex as a local plugin and test with a prompt such as:

- `Generate an institutional-grade equity research report for AAPL.`
- `Analyze NVDA with bull, base, and bear valuation scenarios.`

## Prerequisites

### Required

- Claude Code or Codex
- Internet access for market and company research
- Git if you plan to clone the repository

### Optional

- A text editor if you want to customize the local command file

## Troubleshooting

### Claude Plugin Command Not Found

- Run `/help` to confirm the plugin is registered
- Reinstall with `/plugin install trading-ideas@equity-research-marketplace`
- Restart the Claude session if the command list does not refresh

### Claude Local Command Not Found

- Check that `~/.claude/commands/trading-ideas.md` exists
- Re-download the file from `vortezwohl/equity-research`
- Start a new Claude session after replacing the command file

### Codex Skill Not Triggering

- Confirm the repository root was added, not only a subdirectory
- Check that `.codex-plugin/plugin.json` and `skills/equity-research/SKILL.md` are both present
- Retry with an explicit stock research request instead of a vague finance prompt

## Related Documents

- [Main README](../README.md)
- [Claude command guide](../commands/README.md)
- [Customization guide](customization.md)

This project is for educational and research purposes only and is not financial advice.
