# AI Coding（Cursor Agent Skill）

**AI Coding 编程规范** — Cursor 个人/团队可安装的 Agent Skill（当前 **v1.36**）。

用于：依赖向内、索引驱动、效果/功能锁、先确认后改、沟通语言层级 L1–L4、纪律化回复（7.29）、会话 memory（7.30）、可扩展点（优先 rule+占位）、量级省耗、事毕复盘等。  
触发：项目编码，或提及「编程规范 / 表述 / 先确认 / @ai-coding / @grounded-reply / rules」。

| 文件 | 说明 |
|------|------|
| [SKILL.md](SKILL.md) | 主规范（Agent 摘要 / SSOT） |
| [rule-placeholder.mdc.example](rule-placeholder.mdc.example) | 项目 rule 占位样例（复制到 `.cursor/rules/`） |
| [reference.md](reference.md) | 细则与编号总表 |
| [templates.md](templates.md) | 可复制模板 |
| [CHANGELOG.md](CHANGELOG.md) | 版本变更 |
| [INSTALL.md](INSTALL.md) | 安装与更新 |

## 快速安装（个人全局）

**Windows（PowerShell）：**

```powershell
$dest = Join-Path $env:USERPROFILE ".cursor\skills\ai-coding"
git clone https://github.com/wizard6/ai-coding-skill.git $dest
```

**macOS / Linux：**

```bash
git clone https://github.com/wizard6/ai-coding-skill.git ~/.cursor/skills/ai-coding
```

装好后新开 Agent 对话，或在对话里 `@ai-coding`。完整步骤与项目级安装见 [INSTALL.md](INSTALL.md)。

## 许可

按仓库用途自用或团队共享；未另附 LICENSE 时默认保留作者权利，使用前请与维护者确认。
