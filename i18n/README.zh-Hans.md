# Equity Research Plugin

[English](../README.md) | [简体中文](README.zh-Hans.md) | [繁體中文](README.zh-Hant.md)

这是英文主文档 `[README.md](../README.md)` 的简体中文版本。仓库同时兼容 Claude 与 Codex，两种宿主共享同一套股票研究框架。

## 项目概览

该项目提供两条集成路径：

- Claude 侧插件资源位于 `commands/trading-ideas/`
- Codex 侧插件资源位于 `.codex-plugin/` 与 `skills/equity-research/`

共同能力包括：

- 机构风格的投资摘要、评级与目标价
- 基本面分析、同业对比与前瞻判断
- 近中期催化剂与事件驱动分析
- Bull / Base / Bear 三情景估值
- 风险评估、仓位建议与下行情景
- 技术面、期权流、内幕交易与市场定位

## 使用方式

### Claude

安装后使用：

```bash
/trading-ideas:research AAPL
```

### Codex

将仓库作为本地插件提供给 Codex 后，可通过 `equity-research` skill 触发，例如：

- `Generate an institutional-grade equity research report for AAPL.`
- `Analyze NVDA with bull, base, and bear valuation scenarios.`

## 文档约定

- 英文版 `README.md` 作为主文档与事实来源
- 简体与繁体版本位于 `i18n/`
- 修改英文主文档后，应同步更新两个中文版本

## 目录提示

- Claude 插件市场清单：`../.claude-plugin/marketplace.json`
- Codex 插件清单：`../.codex-plugin/plugin.json`
- Codex skill：`../skills/equity-research/SKILL.md`

本项目仅用于教育和研究，不构成金融建议。
