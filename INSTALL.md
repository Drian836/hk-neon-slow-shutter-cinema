# Installation and downloads / 安装与下载

Repository: <https://github.com/Drian836/hk-neon-slow-shutter-cinema>

## Recommended download / 推荐下载

Open [GitHub Releases](https://github.com/Drian836/hk-neon-slow-shutter-cinema/releases) and download `hk-neon-slow-shutter-cinema-v0.3.0.zip`. The archive contains the Skill directory itself; extract that directory directly under your Codex skills folder.

进入 [GitHub Releases](https://github.com/Drian836/hk-neon-slow-shutter-cinema/releases)，下载 `hk-neon-slow-shutter-cinema-v0.3.0.zip`。压缩包内部已经是 Skill 目录；将它直接解压到 Codex Skills 目录即可。

## Install on Windows / Windows 安装

PowerShell:

```powershell
$source = "C:\path\to\hk-neon-slow-shutter-cinema"
$destination = Join-Path $env:USERPROFILE ".codex\skills\hk-neon-slow-shutter-cinema"
Copy-Item -LiteralPath $source -Destination $destination -Recurse
```

The installed file below must exist:

```text
%USERPROFILE%\.codex\skills\hk-neon-slow-shutter-cinema\SKILL.md
```

## Install on macOS or Linux / macOS 或 Linux 安装

```bash
mkdir -p ~/.codex/skills
cp -R /path/to/hk-neon-slow-shutter-cinema ~/.codex/skills/
```

The installed file below must exist:

```text
~/.codex/skills/hk-neon-slow-shutter-cinema/SKILL.md
```

## Install with Git / 使用 Git 安装

```bash
git clone https://github.com/Drian836/hk-neon-slow-shutter-cinema.git ~/.codex/skills/hk-neon-slow-shutter-cinema
```

For an existing clone:

```bash
cd ~/.codex/skills/hk-neon-slow-shutter-cinema
git pull --ff-only
```

Windows PowerShell equivalent:

```powershell
git clone https://github.com/Drian836/hk-neon-slow-shutter-cinema.git "$env:USERPROFILE\.codex\skills\hk-neon-slow-shutter-cinema"
```

## Verify / 验证

Open a new Codex task and use:

```text
Use $hk-neon-slow-shutter-cinema to analyze why this Hong Kong night photograph feels cinematic. Do not generate an image.
```

Or generate:

```text
使用 $hk-neon-slow-shutter-cinema 生成一个凌晨站在香港街角等人的女人；人物保持清楚，周围人流具有两个不同的表观时钟。
```

If the Skill is not listed, confirm that `SKILL.md` sits directly inside the expected directory, then restart Codex or open a new task.

如果 Skill 没有出现，请先确认 `SKILL.md` 正好位于上述目录，然后重启 Codex 或新建任务。

## Update / 更新

For a Git installation, use `git pull --ff-only`. For a ZIP installation, download a newer Release and replace the existing Skill directory after backing up personal changes.

Git 安装使用 `git pull --ff-only`。ZIP 安装请下载新 Release；若本地改过文件，先备份，再替换原 Skill 目录。

## Uninstall / 卸载

Remove only the exact `hk-neon-slow-shutter-cinema` directory from `.codex/skills`. Do not delete the whole `.codex/skills` directory.

只删除 `.codex/skills` 下准确命名为 `hk-neon-slow-shutter-cinema` 的目录，不要删除整个 `.codex/skills`。

## Package contents / 文件内容

- `SKILL.md`: router, workflows, input roles, output contracts;
- `references/`: visual families, motion, scene, light, composition, prompt compiler, poster system, QA;
- `examples/`: three complete prompt and inspection examples;
- `evals/evals.json`: 17 behavioral evaluations;
- `agents/openai.yaml`: Codex interface metadata;
- `README.md` and `README.zh-CN.md`: English and Chinese usage guides.

