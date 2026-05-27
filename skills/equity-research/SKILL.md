---
name: equity-research
description: Use when the user wants institutional-grade stock research, valuation scenarios, catalyst analysis, or risk-aware investment commentary for a public equity ticker, especially US-listed stocks and ADRs.
---

# Equity Research

This skill provides an institutional-style equity research workflow for Codex. It is designed for users who want a structured report with explicit valuation scenarios, risk assessment, technical context, and market positioning.

## When to Use This Skill

Use this skill when the user:

- Asks for an equity research report on a public company or ticker
- Wants a BUY, SELL, or HOLD style recommendation with a price target
- Needs bull, base, and bear cases with probability weighting
- Wants a structured view of catalysts, risks, valuation, and positioning
- Asks for insider activity, options flow, or analyst target context
- Requests a professional investment memo or institutional-style stock write-up

This skill is optimized for US-listed equities and ADRs. It can still be used for other publicly traded securities when enough public information is available, but coverage quality may be lower.

## Core Workflow

### 1. Confirm the Target Security

- Resolve the company name and ticker if the user provides only one of them
- Prefer the US-listed ticker when multiple listings exist
- If the ticker is ambiguous, state the ambiguity explicitly before proceeding

### 2. Gather Evidence in Parallel

Collect information across these buckets:

1. Financial performance:
   Recent earnings, revenue growth, margins, cash flow, business KPIs, and management guidance.
2. Market positioning:
   Peer comparisons, sector performance, competitive dynamics, market share, and strategic positioning.
3. Advanced intelligence:
   Technical setup, options flow, insider activity, institutional ownership, and regulatory concerns.

### 3. Maintain Evidence Quality

- Use specific numbers and percentages whenever available
- Include explicit timeframes such as YoY, QoQ, trailing twelve months, or next twelve months
- Prefer named analyst firms when citing price targets or rating changes
- Distinguish confirmed facts from inference
- If important data is missing, say so directly instead of filling gaps with confident speculation

### 4. Produce a Structured Report

Always organize the output using the report shape below unless the user explicitly asks for a shorter format.

## Output Contract

Use this structure:

```markdown
# <COMPANY NAME> (<TICKER>) - ENHANCED EQUITY RESEARCH

## EXECUTIVE SUMMARY
<BUY / SELL / HOLD> with $<target> price target (<upside/downside>%) over <timeframe>. Summarize the core investment thesis, key catalyst, and overall risk-reward balance in 1-3 sentences.

## FUNDAMENTAL ANALYSIS
**Recent Financial Metrics**: Include revenue growth, margins, EPS, cash flow, and important business KPIs with exact figures and timeframes.

**Peer Comparison**: Compare valuation multiples and operating profile versus relevant peers.

**Forward Outlook**: Summarize guidance, consensus expectations, and major operating assumptions.

## CATALYST ANALYSIS
**Near-term (0-6 months)**: Earnings dates, launches, approvals, macro events, or specific triggers.
**Medium-term (6-24 months)**: Strategic initiatives, market expansion, competitive repositioning, margin expansion, or structural themes.
**Event-driven**: M&A potential, index changes, buybacks, spin-offs, or special situations.

## VALUATION & PRICE TARGETS
State current consensus, then give bull, base, and bear cases with assumptions and probability weighting.

## RISK ASSESSMENT
**Company risks**: Company-specific execution, competition, leverage, governance, or regulatory risks.
**Macro risks**: Rates, economic cycle, commodity exposure, sector rotation, or broader market sensitivity.
**Position sizing**: Provide a risk-aware allocation range.
**ESG considerations**: Include only when material.

## TECHNICAL CONTEXT & OPTIONS INTELLIGENCE
Describe current price context versus the recent trading range, important support and resistance levels, volume and momentum context, and options flow or implied volatility where available.

## MARKET POSITIONING
Compare the stock's performance versus sector and market benchmarks and summarize relative strength or weakness.

## INSIDER SIGNALS
Summarize notable insider buying or selling, buyback context, and institutional ownership trends when available.

## RECOMMENDATION SUMMARY

| Metric | Value |
|--------|-------|
| **Rating** | <BUY / SELL / HOLD> |
| **Conviction** | <High / Medium / Low> |
| **Price Target** | $<target> |
| **Timeframe** | <timeframe> |
| **Upside/Downside** | <value>% |
| **Position Size** | <range> |
```

## Quality Standards

The report should:

- Use professional financial terminology where appropriate
- Include concrete valuation assumptions, not just qualitative labels
- Present both upside and downside views
- Include explicit position sizing guidance
- Include a disclaimer that the content is educational and not financial advice
- Avoid pretending to have certainty when evidence is thin or stale

## Important Constraints

- Do not present the analysis as personalized financial advice
- Do not omit downside scenarios
- Do not skip the risk section
- Do not use vague wording when exact numbers or date ranges are available
- If data freshness matters, state the relevant date explicitly

## Recommended Closing Disclaimer

Use a short disclaimer equivalent to:

`This analysis is for educational and research purposes only and is not financial advice.`

Expand it when the user asks for a full professional-style memo.
