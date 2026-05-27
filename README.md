# Equity Research Plugin

[English](README.md) | [简体中文](i18n/README.zh-Hans.md) | [繁體中文](i18n/README.zh-Hant.md)

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Status: Active](https://img.shields.io/badge/Status-Active-green.svg)
![Hosts: Claude%20%2B%20Codex](https://img.shields.io/badge/Hosts-Claude%20%2B%20Codex-teal.svg)

Professional equity research and trading analysis for Claude and Codex, designed to produce institutional-style reports with valuation scenarios, catalyst mapping, technical context, and risk-aware position sizing.

## Overview

This repository now supports two integration paths:

- Claude-compatible plugin assets under `commands/trading-ideas/`
- Codex-compatible plugin assets under `.codex-plugin/` and `skills/equity-research/`

Both paths share the same research framework:

- Institutional-style executive summaries with explicit ratings and price targets
- Fundamental analysis with exact metrics, peer context, and forward outlook
- Catalyst mapping across near-term, medium-term, and event-driven scenarios
- Bull, base, and bear valuation cases with probability weighting
- Risk assessment, position sizing guidance, and downside framing
- Technical context, options flow, insider activity, and market positioning

## Compatibility

| Host | Integration | Entry Point |
|------|-------------|-------------|
| Claude | Slash-command plugin | `/trading-ideas:research <TICKER>` |
| Codex | Local plugin skill | `equity-research` skill from this repository |

## Installation

### Claude Plugin Workflow

1. Add the marketplace:

```bash
/plugin marketplace add vortezwohl/codex-equity-research-plugin
```

2. Install the plugin:

```bash
/plugin install trading-ideas@claude-equity-research-marketplace
```

3. Verify the command is available:

```bash
/help
```

### Codex Plugin Workflow

Codex discovers the repository through the root plugin manifest:

- `.codex-plugin/plugin.json`
- `skills/equity-research/SKILL.md`

Once the repository is available as a local plugin, Codex can use the `equity-research` skill when the user asks for:

- an equity research report on a public company or ticker
- a BUY, SELL, or HOLD recommendation with a price target
- bull, base, and bear valuation scenarios
- catalysts, risks, or institutional-style stock commentary

## Usage Examples

### Claude

```bash
/trading-ideas:research AAPL
/trading-ideas:research NVDA --detailed
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
codex-equity-research-plugin/
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

- Keep the Claude command prompt and Codex skill aligned when the research workflow changes.
- Preserve both integration paths unless the project explicitly drops one host.
- Avoid embedding machine-specific local paths in repository files or plugin metadata.
- Keep documentation in English as the source of truth, then sync the two translated README files under `i18n/`.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

## Support

- [Plugin documentation](PLUGIN.md)
- [Command documentation](commands/README.md)
- [Project documentation](docs/)
- [Security policy](SECURITY.md)

This project is for educational and research purposes only and is not financial advice. Always perform independent due diligence before making investment decisions.
