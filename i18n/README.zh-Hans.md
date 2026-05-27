# Equity Research Plugin

[English](../README.md) | [简体中文](README.zh-Hans.md) | [繁體中文](README.zh-Hant.md)

这是主文档 [README.md](../README.md) 的简体中文版。本仓库的唯一正式来源为 `vortezwohl/equity-research`，Claude 插件与 Codex skill 都应从当前仓库安装，不再依赖任何旧仓库地址。

## 项目概览

本仓库同时提供两条集成路径：

- Claude 插件资源：`../.claude-plugin/` 与 `../commands/trading-ideas/`
- Codex 插件资源：`../.codex-plugin/` 与 `../skills/equity-research/`

两侧共享同一套股票研究框架：

- 机构风格的投资摘要、评级与目标价
- 带具体指标的基本面分析、同业对比与前瞻判断
- 近中期催化剂与事件驱动情景分析
- Bull / Base / Bear 三情景估值
- 风险评估、仓位建议与下行情景
- 技术面、期权流、内幕交易与市场定位

## 安装方式

### Claude 插件安装

从当前仓库添加 marketplace 并安装插件：

```bash
/plugin marketplace add vortezwohl/equity-research
/plugin install trading-ideas@equity-research-marketplace
```

安装完成后可用：

```bash
/trading-ideas:research AAPL
```

### Claude 本地命令安装

如果你只想安装命令文件，而不是走插件 marketplace：

```bash
curl -o ~/.claude/commands/trading-ideas.md https://raw.githubusercontent.com/vortezwohl/equity-research/main/commands/trading-ideas/commands/research.md
```

这种方式安装后使用：

```bash
/trading-ideas AAPL
```

### Codex 安装

先克隆当前仓库：

```bash
git clone https://github.com/vortezwohl/equity-research.git
cd equity-research
```

然后将仓库根目录作为本地插件加入 Codex。Codex 会通过以下文件发现插件与 skill：

- `../.codex-plugin/plugin.json`
- `../skills/equity-research/SKILL.md`

安装后，可通过下列请求触发 `equity-research` skill：

- `Generate an institutional-grade equity research report for AAPL.`
- `Analyze NVDA with bull, base, and bear valuation scenarios.`
- `Compare TSLA fundamentals, catalysts, and risks.`

## 文档约定

- 英文版 `../README.md` 为主文档
- 简体与繁體版本位于 `../i18n/`
- 修改主文档后，应同步更新两个中文版本

## 目录提示

- Claude marketplace：`../.claude-plugin/marketplace.json`
- Codex 插件清单：`../.codex-plugin/plugin.json`
- Codex skill：`../skills/equity-research/SKILL.md`
- Claude 命令说明：`../commands/README.md`

本项目仅用于教育和研究，不构成金融建议。
