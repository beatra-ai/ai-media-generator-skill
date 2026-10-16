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

<p align="center"><img src="assets/hero.webp" width="800" alt="Three different image jobs from one agent session: a product shot of a fictional sparkling water can labeled Tidewell, a flat vector blog header about working from home, and a stormy lighthouse at dusk as a cinematic concept frame. AI-generated with Beatra."></p>

*Three different image jobs from one agent session: a product shot of a fictional sparkling water can labeled Tidewell, a flat vector blog header about working from home, and a stormy lighthouse at dusk as a cinematic concept frame. AI-generated with Beatra.*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`beatra`](skills/beatra) | [SKILL.md](skills/beatra/SKILL.md) | 2.9.6 |

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

## Specs

As of 2026-10-16. Live list: https://docs.beatra.ai/en/docs/models

- **Text to image** — 10 models (Qwen Image 2.0 Fast, Qwen Image 3.0, Qwen Image 3.0 Pro, GPT Image 2.5 Flare, GPT Image 2.5 Sunburst, GPT Image 2, Wan Image 2.7 Fast, Qwen Image 2.0 Pro, Wan Image 2.7 Pro, MiniMax Image 01 Live); up to 4 images per request; canvas up to 16777216 pixels
- **Image to image** — 10 models (Qwen Image 2.0 Fast, Qwen Image 3.0, Qwen Image 3.0 Pro, Wan Image 2.7 Fast, Qwen Image 2.0 Pro, Wan Image 2.7 Pro, GPT Image 2.5 Flare, GPT Image 2.5 Sunburst, GPT Image 2, MiniMax Image 01 Live); up to 4 images per request; canvas up to 16777216 pixels
- **Image editing** — 6 models (Qwen Image 2.0 Fast, Qwen Image 3.0, Qwen Image 3.0 Pro, Wan Image 2.7 Fast, Qwen Image 2.0 Pro, Wan Image 2.7 Pro); up to 4 images per request; canvas up to 4194304 pixels
- **Image understanding** — 1 model (MiniMax M3)
- **Text to video** — 9 models (seedance-2-mini, wan2.7-t2v, wan3.0-video, minimax-h3, happyhorse-1.1-t2v, seedance-2-fast, seedance-2, wan3.0-video-prime, seedance-2.5); 480p to 4K; 2–30 s; aspect ratios 16:9, 1:1, 21:9, 3:4, 4:3, 9:16, 4:5, 5:4, 9:21; MOV, MP4; 2 with native audio
- **Image to video** — 9 models (wan2.7-i2v, wan3.0-video, minimax-h3, seedance-2-mini, happyhorse-1.1-i2v, seedance-2-fast, seedance-2, wan3.0-video-prime, seedance-2.5); 480p to 4K; 2–30 s; aspect ratios 16:9, 1:1, 21:9, 3:4, 4:3, 9:16; MOV, MP4; 2 with native audio
- **Reference to video** — 9 models (wan2.7-r2v, minimax-h3, wan3.0-video, happyhorse-1.1-r2v, seedance-2-mini, seedance-2-fast, seedance-2, wan3.0-video-prime, seedance-2.5); 480p to 4K; 2–30 s; aspect ratios 16:9, 1:1, 3:4, 4:3, 9:16, 21:9, 4:5, 5:4, 9:21; MOV, MP4; 2 with native audio
- **First and last frames to video** — 8 models (wan2.7-i2v, wan3.0-video, minimax-h3, seedance-2-mini, seedance-2-fast, seedance-2, wan3.0-video-prime, seedance-2.5); 480p to 4K; 2–30 s; aspect ratios 16:9, 1:1, 21:9, 3:4, 4:3, 9:16; MOV, MP4; 2 with native audio
- **Video editing** — 8 models (wan2.7-videoedit, wan3.0-video, happyhorse-1.0-video-edit, seedance-2-mini, seedance-2-fast, seedance-2, wan3.0-video-prime, seedance-2.5); 480p to 4K; 2–30 s; aspect ratios 16:9, 1:1, 3:4, 4:3, 9:16, 21:9; MOV, MP4
- **Video extension** — 7 models (wan2.7-i2v, wan3.0-video, seedance-2-mini, seedance-2-fast, seedance-2, wan3.0-video-prime, seedance-2.5); 480p to 4K; 2–30 s; aspect ratios 16:9, 1:1, 21:9, 3:4, 4:3, 9:16; MOV, MP4; 1 with native audio
- **Video understanding** — 1 model (MiniMax M3)
- **Text to music** — 2 models (Suno 6, MiniMax Music 3.0); lyrics up to 5000 characters
- **Reference audio to music** — 2 models (Suno 6, MiniMax Music 3.0); lyrics up to 5000 characters
- **Text to speech** — 2 models (MiniMax Speech 2.8 HD, MiniMax Speech 2.8 Turbo); FLAC, MP3, OPUS, PCM, WAV; 40 languages; up to 44.1 kHz; up to 50000 characters per request
- **Voice cloning** — 1 model (MiniMax Voice Clone)

## Why use Beatra instead of calling model APIs directly

- **One account for every model this skill uses** — Text to image 10; Image to image 10; Image editing 6; Image understanding 1; Text to video 9; Image to video 9; Reference to video 9; First and last frames to video 8; Video editing 8; Video extension 7; Video understanding 1; Text to music 2; Reference audio to music 2; Text to speech 2; Voice cloning 1 (as of 2026-10-16), behind one Beatra sign-in; no keys from individual model providers to manage.
- **You decide what gets paid for** — Paid renders run only when you ask for that exact render or approve its card, which shows the live credit estimate.
- **Direction before rendering** — the skill plans, directs, and reviews the work, then renders it on Beatra.
- **Files you can verify** — every file under `skills/` matches the release archive on cdn.beatra.ai byte for byte, checked by SHA-256 before each push.
- **Updates you control** — no self-updater; update with the tool you installed it with.
- **Runs in your agent** — Claude Code, Codex, OpenClaw.

## How it compares

| | Beatra (this skill) | [scenario-labs/skills](https://github.com/scenario-labs/skills) | [vargHQ/skills](https://github.com/vargHQ/skills) |
| --- | --- | --- | --- |
| Account or key needed | A Beatra account; no model provider keys | A Scenario account (OAuth) or a Scenario API key ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L105)) | A VARG_API_KEY, required for all skills ([source](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/README.md#L70)) |
| Models | Text to image 10; Image to image 10; Image editing 6; Image understanding 1; Text to video 9; Image to video 9; Reference to video 9; First and last frames to video 8; Video editing 8; Video extension 7; Video understanding 1; Text to music 2; Reference audio to music 2; Text to speech 2; Voice cloning 1 | Image, video, audio and 3D models on Scenario, e.g. GPT Image, Seedream, Veo, Kling, Seedance, ElevenLabs, MiniMax music ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L247-L299)) | Kling, Flux, ElevenLabs, Sora and more through the varg platform ([source](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/README.md#L3)) |
| Before spending | Paid renders run only when you ask for that exact render or approve its card, which shows the live credit estimate | Dry-run price estimates in its quality-gate and model-comparison skills ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L208-L210)) | A free `--preview` render before the full render ([source](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/README.md#L158-L160)) |
| Agents | Claude Code, Codex, OpenClaw | Claude Code, Cursor, Codex, Copilot and 70+ others ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L30)) | Claude Code, Cursor, Windsurf, OpenCode, ClawHub and any Agent Skills tool ([source](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/README.md#L10)) |
| Install | `npx skills add beatra-ai/ai-media-generator-skill` | `npx skills add scenario-labs/skills`, then connect the Scenario MCP server (https://mcp.scenario.com/mcp) ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L89-L105)) | `npx skills add vargHQ/skills` ([source](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/README.md#L59)) |
| License | MIT-0 | MIT ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/LICENSE)) | MIT ([source](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/LICENSE)) |
| Last updated | Updated with every release (v2.9.6) | 2026-10-15 ([source](https://github.com/scenario-labs/skills/commit/49dd26e47371163ae0020c7f5627d0993626bfc2)) | 2026-10-01 ([source](https://github.com/vargHQ/skills/commit/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d)) |

Facts checked on 2026-10-16. Corrections: open an issue in [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/issues).


## Updates and security

Since the 2026-10 release, this skill contains no self-updater: it runs only the
files you installed and never replaces them on its own. Update it with the tool
you installed it with — `npx skills update beatra` or `gh skill update beatra`.
Details: `references/updates-and-security.md` inside the skill.

## License

[MIT-0](LICENSE) — free to use, modify, and redistribute, including
commercially. No attribution required. Same terms as these skills carry on
ClawHub.

## Links

- Website — https://beatra.ai
- Docs — https://docs.beatra.ai
- Console — https://console.beatra.ai
- For AI agents — https://beatra.ai/llms.txt (index) · https://beatra.ai/llms-full.txt (every skill in one file)
