# AI Coding（Cursor Agent Skill）

**AI Coding 编程规范** — Cursor 个人/团队可安装的 Agent Skill（当前 **v1.41**）。

用于：确认后改、意图路由（SOLVE/EXPLAIN/EVOLVE）、会话 memory、可扩展点、切片交付、收敛止损、主动召回分析、纪律回复、L1–L4 等。  
**已内化且建议停用独立目录**：vibe-coding、vibe-governance、focus-thinking、grounded-reply、convergent-fix、intent-routing。  
**仍独立**：focus-drive-dev（HTML 蓝图；下游执行层用本技能）。  
触发（点名）：`@ai-coding` / 旧别名 / 「编程规范」/「技能体检」/ SOLVE·EXPLAIN·EVOLVE 等；**勿**因「写代码」泛词主动加载。

| 文件 | 说明 |
|------|------|
| [SKILL.md](SKILL.md) | Agent 摘要（SSOT） |
| [rule-placeholder.mdc.example](rule-placeholder.mdc.example) | 项目 rule 占位样例 |
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
