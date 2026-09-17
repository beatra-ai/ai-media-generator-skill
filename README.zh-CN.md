# AI Media Generator Skill

[English](./README.md) | 简体中文

一个 Agent Skill 生成 AI 图片、视频、音乐和配音，支持 Claude Code、Codex 和 OpenClaw。

> [!IMPORTANT]
> 生成需要 [Beatra](https://beatra.ai) 账号并消耗积分，安装本身不收费。

| 问题 | 回答 |
| --- | --- |
| **能做什么** | 通过同一连接生成AI图片、视频、音乐与语音，查找公开社交数据，编辑受支持的图片和视频，并清晰查看返回文件与实际积分用量。 |
| **运行要求** | Python 3.10+，以及能加载 `SKILL.md` 的 Agent |
| **费用** | 安装免费。每次生成消耗 Beatra 账号积分，只有你明确要求这次生成或批准确认卡后才会付费。 |
| **支持的 Agent** | Claude Code、Codex、OpenClaw |

<p align="center"><img src="assets/hero.webp" width="800" alt="同一个 Agent 会话里的三类图片任务：虚构气泡水品牌 Tidewell 的产品广告图、居家远程办公主题的扁平插画博客头图、暴风雨黄昏中的灯塔电影感概念图。由 Beatra AI 生成。"></p>

*同一个 Agent 会话里的三类图片任务：虚构气泡水品牌 Tidewell 的产品广告图、居家远程办公主题的扁平插画博客头图、暴风雨黄昏中的灯塔电影感概念图。由 Beatra AI 生成。*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`beatra`](skills/beatra) | [SKILL.md](skills/beatra/SKILL.md) | 2.8.8 |

本仓库由 [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/beatra) 自动发布，问题请到那里反馈。

## 安装

使用 [`skills`](https://skills.sh) CLI：

```bash
npx skills add beatra-ai/ai-media-generator-skill
```

使用 GitHub CLI：

```bash
gh skill install beatra-ai/ai-media-generator-skill beatra
```

也可以克隆本仓库，把 `skills/beatra` 复制到 `~/.claude/skills/`（Claude Code）、`~/.agents/skills/`（Codex）或 `~/.openclaw/skills/`（OpenClaw）。

或者把下面这段话发给你的 Agent：

```text
从 https://github.com/beatra-ai/ai-media-generator-skill 安装 beatra skill（目录 skills/beatra），然后按它的 SKILL.md 连接我的 Beatra 账号。
```


## 更新

安装后的 skill 每天最多检查一次新版本，替换前先校验官方归档，任何一步失败都不会动你已安装的版本。
随时可以关闭，见 skill 内的 `references/automatic-updates-and-safety.md`。

## 许可证

[MIT-0](LICENSE)：可自由使用、修改和再分发，包括商用，无需署名；与这些 skill 在 ClawHub 上的条款一致。
