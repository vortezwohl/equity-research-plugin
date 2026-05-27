# Equity Research Plugin

[English](../README.md) | [简体中文](README.zh-Hans.md) | [繁體中文](README.zh-Hant.md)

這是主文件 [README.md](../README.md) 的繁體中文版。本倉庫的唯一正式來源為 `vortezwohl/equity-research`，Claude 外掛與 Codex skill 都應從目前倉庫安裝，不再依賴任何舊倉庫位址。

## 專案概覽

本倉庫同時提供兩條整合路徑：

- Claude 外掛資源：`../.claude-plugin/` 與 `../commands/trading-ideas/`
- Codex 外掛資源：`../.codex-plugin/` 與 `../skills/equity-research/`

兩側共用同一套股票研究框架：

- 機構風格的投資摘要、評級與目標價
- 含具體指標的基本面分析、同業比較與前瞻判斷
- 近中期催化劑與事件驅動情境分析
- Bull / Base / Bear 三情境估值
- 風險評估、部位建議與下行情境
- 技術面、期權流、內幕交易與市場定位

## 安裝方式

### Claude 外掛安裝

從目前倉庫加入 marketplace 並安裝外掛：

```bash
/plugin marketplace add vortezwohl/equity-research
/plugin install trading-ideas@equity-research-marketplace
```

安裝完成後可使用：

```bash
/trading-ideas:research AAPL
```

### Claude 本地命令安裝

如果你只想安裝命令檔，而不是透過外掛 marketplace：

```bash
curl -o ~/.claude/commands/trading-ideas.md https://raw.githubusercontent.com/vortezwohl/equity-research/main/commands/trading-ideas/commands/research.md
```

此方式安裝後使用：

```bash
/trading-ideas AAPL
```

### Codex 安裝

先 clone 目前倉庫：

```bash
git clone https://github.com/vortezwohl/equity-research.git
cd equity-research
```

接著將倉庫根目錄加入 Codex 作為本地外掛。Codex 會透過以下檔案發現外掛與 skill：

- `../.codex-plugin/plugin.json`
- `../skills/equity-research/SKILL.md`

安裝後，可透過下列請求觸發 `equity-research` skill：

- `Generate an institutional-grade equity research report for AAPL.`
- `Analyze NVDA with bull, base, and bear valuation scenarios.`
- `Compare TSLA fundamentals, catalysts, and risks.`

## 文件約定

- 英文版 `../README.md` 為主文件
- 簡體與繁體版本位於 `../i18n/`
- 修改主文件後，應同步更新兩個中文版本

## 目錄提示

- Claude marketplace：`../.claude-plugin/marketplace.json`
- Codex 外掛清單：`../.codex-plugin/plugin.json`
- Codex skill：`../skills/equity-research/SKILL.md`
- Claude 命令說明：`../commands/README.md`

本專案僅用於教育與研究，不構成金融建議。
