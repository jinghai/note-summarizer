# 📝 Note Summarizer - 智能笔记摘要助手

> 一个帮助 AI Agent 智能整理笔记、自动生成摘要并保存到 Obsidian 的技能系统

## 🎯 功能特点

- ✅ **双模式触发**：支持单条消息即时整理和上下文分步整理
- ✅ **智能内容识别**：自动识别链接类型（视频、文章、公众号等）
- ✅ **自动摘要生成**：提取核心知识点，生成3-5个要点
- ✅ **智能标签系统**：自动生成3-5个相关标签
- ✅ **Obsidian 集成**：自动保存到 Obsidian inbox 目录

## ⚡ 核心优势

- **上下文感知**：5分钟内自动关联"整理笔记"指令和转发内容
- **多平台支持**：支持今日头条、微信公众号、知乎、B站、YouTube 等
- **混合内容处理**：支持文字、图片、链接、视频的混合内容
- **隐私保护**：自动识别敏感信息，添加 #private 标签

## 📦 安装

### 方法1：使用 Skills CLI

```bash
npx skills add <your-github-username>/agent-skills/note-summarizer
```

### 方法2：手动安装

1. 下载或克隆本仓库
2. 复制 `note-summarizer/` 目录到你的 skills 目录
3. 重启 Agent

## 🔧 使用方法

### 模式1：单条消息（即时整理）

```
用户：整理笔记 + [转发内容/链接/文字]
→ 立即分析并保存
```

### 模式2：上下文模式（分步整理）

```
方式A：先指令，后内容
  用户：整理笔记
  用户：[转发视频/链接/文字]  ← 自动关联，无需重复指令
  
方式B：先内容，后指令
  用户：[转发视频/链接/文字]
  用户：整理笔记  ← 自动识别上文内容
```

**触发关键词**：整理笔记、笔记摘要、记笔记、保存笔记、归档、总结一下

## 📋 生成的笔记格式

```markdown
---
title: 笔记标题
date: YYYY-MM-DD HH:mm
tags:
  - 标签1
  - 标签2
  - 标签3
source: 来源平台/作者
---

## 一句话总结
（用1句话概括核心价值）

## 核心要点
- 要点1
- 要点2
- 要点3

## Actionable 建议
- [ ] 行动项1
- [ ] 行动项2

## 原文/参考
- 链接：[标题](URL)
- 作者：@用户名
```

## 🏷️ 标签系统

### 主题标签（必选1-2个）
- #AI #产品 #效率 #认知 #商业 #技术 #设计 #投资 #健康 #生活

### 类型标签（必选1个）
- #方法论 #工具 #案例 #观点 #数据 #教程 #资源

### 场景标签（可选）
- #工作 #学习 #生活 #投资 #健康 #娱乐

## 🌐 支持的平台

| 平台 | 链接特征 | 提取内容 |
|------|---------|---------|
| 今日头条 | toutiao.com | 标题、作者、摘要 |
| 微信公众号 | mp.weixin.qq.com | 标题、作者、正文 |
| 知乎 | zhihu.com | 标题、作者、回答摘要 |
| B站 | bilibili.com/b23.tv | 标题、UP主、描述 |
| YouTube | youtube.com | 标题、频道、描述 |
| X/Twitter | x.com/twitter.com | 文本、作者 |
| 抖音 | douyin.com | 标题、作者、描述 |
| 小红书 | xiaohongshu.com | 标题、作者、内容 |

## ⚙️ 配置选项

编辑 `config.yaml` 自定义行为：

```yaml
context_memory:
  window_minutes: 5      # 时间窗口（分钟）
  max_messages: 3        # 最大关联消息数

save_config:
  folder: "inbox"        # 保存目录
  filename_format: "{date}-{中文标题}.md"

tag_library:
  topics: [AI, 产品, 效率, 认知, 商业]
  types: [方法论, 工具, 案例, 观点]
  scenes: [工作, 学习, 生活]
```

## 📝 许可

MIT License

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

## 🔗 相关链接

- [Agent Skills 规范](https://agentskills.io/specification)
- [Obsidian 官方](https://obsidian.md/)
- [self-learning 技能](https://github.com/jinghai/self-learning) - 配套的自学习经验系统
