# AI Media Generator Skill

English | [简体中文](./README.zh-CN.md)

Create AI images, videos, music, and voice-over from one Agent Skill for Claude Code, Codex, and OpenClaw.

> [!IMPORTANT]
> Rendering needs a [Beatra](https://beatra.ai) account and uses credits. The skill itself is free to install.

| Question | Answer |
| --- | --- |
| **What it does** | Create AI images, videos, music, and voice, look up public social data, edit supported visual results, and keep returned files and credit use easy to track through one shared connection. |
| **Requirements** | Python 3.10+ and an agent that loads `SKILL.md` |
| **Cost** | Free to install. Each render uses credits on your Beatra account, and paid steps run only when you ask for that exact render or approve its card. |
| **Works with** | Claude Code, Codex, OpenClaw |

| Skill | Entry point | Version |
| --- | --- | --- |
| [`beatra`](skills/beatra) | [SKILL.md](skills/beatra/SKILL.md) | 2.8.8 |

This repository is published automatically from [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/beatra). Report issues there.

## Install

With the [`skills`](https://skills.sh) CLI:

```bash
npx skills add beatra-ai/ai-media-generator-skill
```

With the GitHub CLI:

```bash
gh skill install beatra-ai/ai-media-generator-skill beatra
```

Or clone this repository and copy `skills/beatra` into `~/.claude/skills/` for Claude Code,
`~/.agents/skills/` for Codex, or `~/.openclaw/skills/` for OpenClaw.

Or paste this into your agent:

```text
Install the beatra skill from https://github.com/beatra-ai/ai-media-generator-skill (folder skills/beatra), then follow its SKILL.md to connect my Beatra account.
```


## Updates

Each installed skill checks for a new version at most once a day, verifies the
official archive before replacing itself, and leaves your installation untouched
if anything fails. Turn it off at any time — see
`references/automatic-updates-and-safety.md` inside the skill.

## License

[MIT-0](LICENSE) — free to use, modify, and redistribute, including
commercially. No attribution required. Same terms as these skills carry on
ClawHub.
