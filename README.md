# AI Coding（Cursor Agent Skill）

**AI Coding 编程规范** — Cursor 个人/团队可安装的 Agent Skill（当前 **v1.31**）。

用于：依赖向内、索引驱动、效果/功能锁、先确认后改、沟通语言层级 L1–L4、量级省耗、固定运维脚本化、事毕复盘等。  
触发：项目编码，或提及「编程规范 / 表述 / 先确认 / @ai-coding」。

| 文件 | 说明 |
|------|------|
| [SKILL.md](SKILL.md) | 主规范（SSOT） |
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
