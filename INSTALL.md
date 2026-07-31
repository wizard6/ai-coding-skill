# 安装 AI Coding Skill

目标：让 Cursor Agent 能读到 `SKILL.md`（目录名建议为 `ai-coding`）。

## 方式 A — Git 克隆到个人技能目录（推荐）

个人技能路径：`~/.cursor/skills/<name>/SKILL.md`  
（Windows：`%USERPROFILE%\.cursor\skills\`）

### 首次安装

```powershell
# Windows PowerShell
$dir = Join-Path $env:USERPROFILE ".cursor\skills"
New-Item -ItemType Directory -Force -Path $dir | Out-Null
git clone https://github.com/wizard6/ai-coding.git (Join-Path $dir "ai-coding")
```

```bash
# macOS / Linux
mkdir -p ~/.cursor/skills
git clone https://github.com/wizard6/ai-coding.git ~/.cursor/skills/ai-coding
```

若目标目录已存在且不是本仓库，请先备份再删/改名，或改用方式 B。

### 更新

```powershell
Set-Location (Join-Path $env:USERPROFILE ".cursor\skills\ai-coding")
git pull
```

```bash
cd ~/.cursor/skills/ai-coding && git pull
```

## 方式 B — 下载 ZIP 解压

1. 打开仓库页面 → **Code** → **Download ZIP**
2. 解压后得到文件夹（可能带 `-main` / `-master` 后缀）
3. 将**内含 `SKILL.md` 的那一层**重命名为 `ai-coding`
4. 整夹移到：
   - 个人：`~/.cursor/skills/ai-coding/`
   - 或项目：`<repo>/.cursor/skills/ai-coding/`

目录内至少应有：`SKILL.md`、`reference.md`、`templates.md`、`CHANGELOG.md`。

## 方式 C — 项目级技能（随仓库共享）

适合团队统一规范、不污染本机全局技能：

```text
your-project/
  .cursor/
    skills/
      ai-coding/
        SKILL.md
        reference.md
        templates.md
        CHANGELOG.md
```

可用 submodule / subtree，或直接拷贝本仓库内容到上述路径后提交。

## 方式 D — 本机已有副本时用链接（开发者）

若你在别处维护源码（例如 `Documents\ai-coding`），可链到技能目录，改一处全局生效：

```powershell
# 需管理员或开发者模式时，Junction 通常无需额外权限
$src  = "C:\Users\ssgs\Documents\ai-coding"   # 改成你的源码路径
$dest = Join-Path $env:USERPROFILE ".cursor\skills\ai-coding"
if (Test-Path $dest) { throw "目标已存在: $dest" }
cmd /c mklink /J "$dest" "$src"
```

```bash
# macOS / Linux
ln -s /path/to/ai-coding ~/.cursor/skills/ai-coding
```

注意：不要链到 `~/.cursor/skills-cursor/`（Cursor 内置目录，勿改）。

## 启用与验证

1. **重启 Cursor**，或至少新开一条 Agent 对话（技能索引常在会话开始时加载）。
2. 在对话中写：`@ai-coding` 或「按编程规范做」。
3. 可选：用本机技能管理扫描（若已装 `skill-manager`）：

```powershell
$sm = Join-Path $env:USERPROFILE ".cursor\skills\skill-manager\scripts"
& "$sm\scan.ps1"
& "$sm\list.ps1"
```

应能看到启用中的 `ai-coding`。

## 停用

```powershell
# 使用 skill-manager（若已装）
& "$env:USERPROFILE\.cursor\skills\skill-manager\scripts\disable.ps1" ai-coding

# 或手动：移出 skills 目录
Move-Item "$env:USERPROFILE\.cursor\skills\ai-coding" "$env:USERPROFILE\.cursor\skills-disabled\ai-coding"
```

## 常见问题

| 现象 | 处理 |
|------|------|
| Agent 不读技能 | 确认路径是 `.../skills/ai-coding/SKILL.md`；新开对话；检查 frontmatter 的 `name`/`description` |
| 与 vibe-coding 冲突 | 分工见 `SKILL.md`「与其它技能」；一般可并存 |
| 克隆失败 | 检查网络与仓库是否公开；私有库需先 `gh auth login` 或配 SSH/HTTPS 凭据 |

## 对齐本机「活」技能

导出仓库与 `%USERPROFILE%\.cursor\skills\ai-coding` 若是两份拷贝，更新后请 `git pull` 或重新拷贝，避免版本漂移。开发推荐方式 D（Junction/symlink）。
