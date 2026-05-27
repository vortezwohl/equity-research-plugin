# Equity Research Plugin

[English](../README.md) | [简体中文](README.zh-Hans.md) | [繁體中文](README.zh-Hant.md)

這是英文主文件 `[README.md](../README.md)` 的繁體中文版本。倉庫同時相容 Claude 與 Codex，兩種宿主共用同一套股票研究框架。

## 專案概覽

此專案提供兩條整合路徑：

- Claude 側插件資產位於 `commands/trading-ideas/`
- Codex 側插件資產位於 `.codex-plugin/` 與 `skills/equity-research/`

共同能力包括：

- 機構風格的投資摘要、評級與目標價
- 基本面分析、同業比較與前瞻判斷
- 近中期催化劑與事件驅動分析
- Bull / Base / Bear 三情境估值
- 風險評估、倉位建議與下行情境
- 技術面、期權流、內線交易與市場定位

## 使用方式

### Claude

安裝後使用：

```bash
/trading-ideas:research AAPL
```

### Codex

將倉庫作為本地插件提供給 Codex 後，可透過 `equity-research` skill 觸發，例如：

- `Generate an institutional-grade equity research report for AAPL.`
- `Analyze NVDA with bull, base, and bear valuation scenarios.`

## 文件約定

- 英文版 `README.md` 作為主文件與事實來源
- 簡體與繁體版本位於 `i18n/`
- 修改英文主文件後，應同步更新兩個中文版本

## 目錄提示

- Claude 插件市場清單：`../.claude-plugin/marketplace.json`
- Codex 插件清單：`../.codex-plugin/plugin.json`
- Codex skill：`../skills/equity-research/SKILL.md`

本專案僅用於教育和研究，不構成金融建議。
