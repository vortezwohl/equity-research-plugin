# Equity Research Plugin

[English](README.md) | [简体中文](i18n/README.zh-Hans.md) | [繁體中文](i18n/README.zh-Hant.md)

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Status: Active](https://img.shields.io/badge/Status-Active-green.svg)
![Hosts: Claude%20%2B%20Codex](https://img.shields.io/badge/Hosts-Claude%20%2B%20Codex-teal.svg)

Institutional-style equity research workflows for Claude and Codex, focused on valuation scenarios, catalyst mapping, technical context, and risk-aware position sizing.

## Overview

This repository is the canonical source for the Equity Research plugin and skill:

- GitHub repository: `https://github.com/vortezwohl/equity-research`
- Claude assets: `.claude-plugin/` and `commands/trading-ideas/`
- Codex assets: `.codex-plugin/` and `skills/equity-research/`

Both integration paths share the same research framework:

- Executive summaries with explicit ratings and price targets
- Fundamental analysis with exact metrics, peer context, and forward outlook
- Catalyst mapping across near-term, medium-term, and event-driven scenarios
- Bull, base, and bear valuation cases with probability weighting
- Risk assessment, position sizing guidance, and downside framing
- Technical context, options flow, insider activity, and market positioning

## Compatibility

| Host | Integration | Entry Point |
|------|-------------|-------------|
| Claude | Marketplace plugin | `/trading-ideas:research <TICKER>` |
| Claude | Local command file | `/trading-ideas <TICKER>` |
| Codex | Local plugin skill | `equity-research` skill from this repository |

## Installation

### Claude Plugin Workflow

Install the Claude plugin from this repository:

```bash
/plugin marketplace add vortezwohl/equity-research
/plugin install trading-ideas@equity-research-marketplace
```

Verify the command is available:

```bash
/help
```

When installed through the plugin system, use:

```bash
/trading-ideas:research AAPL
```

### Claude Local Command Workflow

If you prefer a plain command file instead of the plugin marketplace flow:

```bash
curl -o ~/.claude/commands/trading-ideas.md https://raw.githubusercontent.com/vortezwohl/equity-research/main/commands/trading-ideas/commands/research.md
```

After this manual installation, use:

```bash
/trading-ideas AAPL
```

### Codex Plugin Workflow

Codex discovers this repository through the root plugin manifest and local skill:

- `.codex-plugin/plugin.json`
- `skills/equity-research/SKILL.md`

Install from this repository:

```bash
git clone https://github.com/vortezwohl/equity-research.git
cd equity-research
```

Then add the repository root to Codex as a local plugin. Once the repository is available locally, Codex can trigger the `equity-research` skill for prompts such as:

- `Generate an institutional-grade equity research report for AAPL.`
- `Analyze NVDA with bull, base, and bear valuation scenarios.`
- `Compare TSLA fundamentals, catalysts, and risks.`

## Usage Examples

### Claude Plugin

```bash
/trading-ideas:research AAPL
/trading-ideas:research NVDA --detailed
```

### Claude Local Command

```bash
/trading-ideas AAPL
/trading-ideas NVDA --detailed
```

### Codex

Example prompts:

- `Generate an institutional-grade equity research report for AAPL.`
- `Analyze NVDA with bull, base, and bear valuation scenarios.`
- `Compare TSLA fundamentals, catalysts, and risks.`

## Sample Output Shape

```markdown
# APPLE INC. (AAPL) - ENHANCED EQUITY RESEARCH

## EXECUTIVE SUMMARY
BUY with a defined price target, timeframe, core thesis, and risk-reward framing.

## FUNDAMENTAL ANALYSIS
Recent financial metrics, peer comparison, and forward outlook.

## CATALYST ANALYSIS
Near-term, medium-term, and event-driven catalysts.

## VALUATION & PRICE TARGETS
Bull, base, and bear cases with probability weighting.

## RISK ASSESSMENT
Company risks, macro risks, ESG context, and position sizing.

## TECHNICAL CONTEXT & OPTIONS INTELLIGENCE
Price context, support/resistance, momentum, and options flow.

## MARKET POSITIONING
Sector and benchmark relative strength.

## INSIDER SIGNALS
Insider transactions, buybacks, and ownership changes.
```

## Repository Structure

```text
equity-research/
├── .claude-plugin/
│   └── marketplace.json
├── .codex-plugin/
│   └── plugin.json
├── commands/
│   ├── README.md
│   └── trading-ideas/
│       ├── .claude-plugin/
│       │   └── plugin.json
│       └── commands/
│           └── research.md
├── config/
│   └── config.example.json
├── docs/
├── examples/
├── i18n/
│   ├── README.zh-Hans.md
│   └── README.zh-Hant.md
├── skills/
│   └── equity-research/
│       └── SKILL.md
├── LICENSE
├── PLUGIN.md
├── README.md
└── SECURITY.md
```

## Notes for Maintainers

- Keep Claude command prompts and Codex skill instructions aligned when the research workflow changes.
- Treat `vortezwohl/equity-research` as the only public source of installation and documentation.
- Avoid embedding machine-specific local paths in repository files or plugin metadata.
- Keep the two translated README files under `i18n/` in sync with this document.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

This project is for educational and research purposes only and is not financial advice. Always perform independent due diligence before making investment decisions.
