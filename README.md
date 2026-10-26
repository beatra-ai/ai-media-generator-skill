# AI Media Generator Skill

English | [简体中文](./README.zh-CN.md) | [日本語](./README.ja.md)

> 👉 See also [AI Image Generator Skill](https://github.com/beatra-ai/ai-image-generator-skill)

Create AI images, videos, music, and voice-over from one Agent Skill for Claude Code, Cursor, Codex, Windsurf, Cline, and OpenClaw.

> [!IMPORTANT]
> Rendering needs a [Beatra](https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-media-generator-skill) account and uses credits. The skill itself is free to install.

| Question | Answer |
| --- | --- |
| **What it does** | Create AI images, videos, music, and voice, look up public social data, edit supported visual results, and keep returned files and credit use easy to track through one shared connection. |
| **Models** | Qwen Image 2.0 Fast, Qwen Image 3.0, Qwen Image 3.0 Pro, GPT Image 2.5 Flare, GPT Image 2.5 Sunburst, GPT Image 2, Wan Image 2.7 Fast, Qwen Image 2.0 Pro, Wan Image 2.7 Pro, MiniMax Image 01 Live, MiniMax M3, Seedance 2.0 Mini, Wan 2.7, Wan 3.0 Video, MiniMax H3, HappyHorse 1.1, Seedance 2.0 Fast, Seedance 2.0, Wan 3.0 Video Prime, Seedance 2.5, Wan 2.7 Video Edit, HappyHorse 1.0 Video Edit, Suno 6, MiniMax Music 3.0, MiniMax Speech 2.8 HD, MiniMax Speech 2.8 Turbo, MiniMax Voice Clone |
| **Requirements** | Python 3.10+ and an agent that loads `SKILL.md` |
| **Cost** | Free to install. Each render uses credits on your Beatra account, and paid steps run only when you ask for that exact render or approve its card. |
| **Works with** | Claude Code, Cursor, Codex, Windsurf, Cline, OpenClaw |

<p align="center"><img src="assets/hero.webp" width="800" alt="Three different image jobs from one agent session: a product shot of a fictional sparkling water can labeled Tidewell, a flat vector blog header about working from home, and a stormy lighthouse at dusk as a cinematic concept frame. AI-generated with Beatra."></p>

*Three different image jobs from one agent session: a product shot of a fictional sparkling water can labeled Tidewell, a flat vector blog header about working from home, and a stormy lighthouse at dusk as a cinematic concept frame. AI-generated with Beatra.*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`beatra`](skills/beatra) | [SKILL.md](skills/beatra/SKILL.md) | 2.9.9 |

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
`~/.cursor/skills/` for Cursor, `~/.agents/skills/` for Codex, `~/.codeium/windsurf/skills/` for Windsurf,
`~/.cline/skills/` for Cline, or `~/.openclaw/skills/` for OpenClaw.

Or paste this into your agent:

```text
Install the beatra skill from https://github.com/beatra-ai/ai-media-generator-skill (folder skills/beatra), then follow its SKILL.md to connect my Beatra account.
```

## Technical Specifications & Output Limits

As of 2026-10-18. Live list: https://docs.beatra.ai/en/docs/models

- **Uploads** — up to 100 MB per file; the per-model input limits below also apply
- **Text to image** — 10 models (Qwen Image 2.0 Fast, Qwen Image 3.0, Qwen Image 3.0 Pro, GPT Image 2.5 Flare, GPT Image 2.5 Sunburst, GPT Image 2, Wan Image 2.7 Fast, Qwen Image 2.0 Pro, Wan Image 2.7 Pro, MiniMax Image 01 Live); PNG; up to 4 images per request; canvas up to 16.8 MP
  - 16.8 MP (4K tier): Wan Image 2.7 Pro (up to 4 images per request); GPT Image 2.5 Flare, GPT Image 2.5 Sunburst, GPT Image 2 (1 image per request)
- **Image to image** — 10 models (Qwen Image 2.0 Fast, Qwen Image 3.0, Qwen Image 3.0 Pro, Wan Image 2.7 Fast, Qwen Image 2.0 Pro, Wan Image 2.7 Pro, GPT Image 2.5 Flare, GPT Image 2.5 Sunburst, GPT Image 2, MiniMax Image 01 Live); PNG; up to 4 images per request; canvas up to 16.8 MP
  - 16.8 MP (4K tier): GPT Image 2.5 Flare, GPT Image 2.5 Sunburst, GPT Image 2 (1 image per request)
  - Input images: up to 4 per request, 10–20 MB each; BMP, GIF, JPEG, PNG, TIFF, WEBP
- **Image editing** — 6 models (Qwen Image 2.0 Fast, Qwen Image 3.0, Qwen Image 3.0 Pro, Wan Image 2.7 Fast, Qwen Image 2.0 Pro, Wan Image 2.7 Pro); PNG; up to 4 images per request; canvas up to 4.2 MP
  - 4.2 MP (2K tier): Qwen Image 2.0 Fast, Qwen Image 3.0, Qwen Image 3.0 Pro, Wan Image 2.7 Fast, Qwen Image 2.0 Pro, Wan Image 2.7 Pro (up to 4 images per request)
  - Input images: up to 4 per request, 10–20 MB each; BMP, GIF, JPEG, PNG, TIFF, WEBP
- **Image understanding** — 1 model (MiniMax M3); up to 8 files per request; up to 10 MB each
- **Text to video** — 9 models (Seedance 2.0 Mini, Wan 2.7, Wan 3.0 Video, MiniMax H3, HappyHorse 1.1, Seedance 2.0 Fast, Seedance 2.0, Wan 3.0 Video Prime, Seedance 2.5); 480p to 4K; 2–30 s; aspect ratios 16:9, 1:1, 21:9, 3:4, 4:3, 9:16, 4:5, 5:4, 9:21; MOV, MP4
  - 4K: Seedance 2.0, up to 15 s
  - 30 s: Wan 3.0 Video, Wan 3.0 Video Prime, Seedance 2.5, up to 1080p
  - Native audio: Wan 2.7, MiniMax H3
- **Image to video** — 9 models (Wan 2.7, Wan 3.0 Video, MiniMax H3, Seedance 2.0 Mini, HappyHorse 1.1, Seedance 2.0 Fast, Seedance 2.0, Wan 3.0 Video Prime, Seedance 2.5); 480p to 4K; 2–30 s; aspect ratios 16:9, 1:1, 21:9, 3:4, 4:3, 9:16; MOV, MP4
  - 4K: Seedance 2.0, up to 15 s
  - 30 s: Wan 3.0 Video, Wan 3.0 Video Prime, Seedance 2.5, up to 1080p
  - Native audio: Wan 2.7, MiniMax H3
- **Reference to video** — 9 models (Wan 2.7, MiniMax H3, Wan 3.0 Video, HappyHorse 1.1, Seedance 2.0 Mini, Seedance 2.0 Fast, Seedance 2.0, Wan 3.0 Video Prime, Seedance 2.5); 480p to 4K; 2–30 s; aspect ratios 16:9, 1:1, 3:4, 4:3, 9:16, 21:9, 4:5, 5:4, 9:21; MOV, MP4
  - 4K: Seedance 2.0, up to 15 s
  - 30 s: Wan 3.0 Video, Wan 3.0 Video Prime, Seedance 2.5, up to 1080p
  - Native audio: Wan 2.7, MiniMax H3
- **First and last frames to video** — 8 models (Wan 2.7, Wan 3.0 Video, MiniMax H3, Seedance 2.0 Mini, Seedance 2.0 Fast, Seedance 2.0, Wan 3.0 Video Prime, Seedance 2.5); 480p to 4K; 2–30 s; aspect ratios 16:9, 1:1, 21:9, 3:4, 4:3, 9:16; MOV, MP4
  - 4K: Seedance 2.0, up to 15 s
  - 30 s: Wan 3.0 Video, Wan 3.0 Video Prime, Seedance 2.5, up to 1080p
  - Native audio: Wan 2.7, MiniMax H3
- **Video editing** — 8 models (Wan 2.7 Video Edit, Wan 3.0 Video, HappyHorse 1.0 Video Edit, Seedance 2.0 Mini, Seedance 2.0 Fast, Seedance 2.0, Wan 3.0 Video Prime, Seedance 2.5); 480p to 4K; 2–30 s; aspect ratios 16:9, 1:1, 3:4, 4:3, 9:16, 21:9; MOV, MP4
  - 4K: Seedance 2.0, up to 15 s
  - 30 s: Wan 3.0 Video, Wan 3.0 Video Prime, Seedance 2.5, up to 1080p
- **Video extension** — 7 models (Wan 2.7, Wan 3.0 Video, Seedance 2.0 Mini, Seedance 2.0 Fast, Seedance 2.0, Wan 3.0 Video Prime, Seedance 2.5); 480p to 4K; 2–30 s; aspect ratios 16:9, 1:1, 21:9, 3:4, 4:3, 9:16; MOV, MP4
  - 4K: Seedance 2.0, up to 15 s
  - 30 s: Wan 3.0 Video, Wan 3.0 Video Prime, Seedance 2.5, up to 1080p
  - Native audio: Wan 2.7
- **Video understanding** — 1 model (MiniMax M3); 1 file per request; up to 50 MB each; up to 360 s; sampled at 1 fps
- **Text to music** — 2 models (Suno 6, MiniMax Music 3.0); MP3
  - Suno 6: prompt up to 500, lyrics up to 5000, title up to 80 characters
  - MiniMax Music 3.0: prompt up to 2000, lyrics up to 3500, title up to 100 characters
- **Reference audio to music** — 2 models (Suno 6, MiniMax Music 3.0); MP3
  - Suno 6: prompt up to 500, lyrics up to 5000, title up to 80 characters; reference audio 6–480 s (FLAC, MP3, WAV)
  - MiniMax Music 3.0: prompt up to 300, lyrics up to 1000, title up to 100 characters; reference audio 6–360 s, up to 50 MB (FLAC, MP3, WAV)
- **Text to speech** — 2 models (MiniMax Speech 2.8 HD, MiniMax Speech 2.8 Turbo); FLAC, MP3, OPUS, PCM, WAV; 40 languages; sample rates 8, 16, 22.05, 24, 32, 44.1 kHz; up to 50000 characters per request
  - Languages (ISO 639 codes): zh, yue, en, es, fr, ru, de, pt, ar, it, ja, ko, id, vi, tr, nl, uk, th, pl, ro, el, cs, fi, hi, bg, da, he, ms, fa, sk, sv, hr, fil, hu, no, sl, ca, nn, ta, af
- **Voice cloning** — 1 model (MiniMax Voice Clone); sample 10–300 s, up to 20 MB; consent attestation required

## Why use Beatra instead of calling model APIs directly

- **One account for every model this skill uses** — Text to image 10; Image to image 10; Image editing 6; Image understanding 1; Text to video 9; Image to video 9; Reference to video 9; First and last frames to video 8; Video editing 8; Video extension 7; Video understanding 1; Text to music 2; Reference audio to music 2; Text to speech 2; Voice cloning 1 (Qwen Image 2.0 Fast, Qwen Image 3.0, Qwen Image 3.0 Pro, GPT Image 2.5 Flare, GPT Image 2.5 Sunburst, GPT Image 2, Wan Image 2.7 Fast, Qwen Image 2.0 Pro, Wan Image 2.7 Pro, MiniMax Image 01 Live, MiniMax M3, Seedance 2.0 Mini, Wan 2.7, Wan 3.0 Video, MiniMax H3, HappyHorse 1.1, Seedance 2.0 Fast, Seedance 2.0, Wan 3.0 Video Prime, Seedance 2.5, Wan 2.7 Video Edit, HappyHorse 1.0 Video Edit, Suno 6, MiniMax Music 3.0, MiniMax Speech 2.8 HD, MiniMax Speech 2.8 Turbo, MiniMax Voice Clone) (as of 2026-10-18), behind one Beatra sign-in; no keys from individual model providers to manage.
- **You decide what gets paid for** — Paid renders run only when you ask for that exact render or approve its card, which shows the live credit estimate.
- **Direction before rendering** — the skill plans, directs, and reviews the work, then renders it on Beatra.
- **Files you can verify** — every file under `skills/` matches the release archive on cdn.beatra.ai byte for byte, checked by SHA-256 before each push.
- **Updates you control** — no self-updater; update with the tool you installed it with.
- **Runs in your agent** — Claude Code, Cursor, Codex, Windsurf, Cline, OpenClaw.

## How it compares

| | Beatra (this skill) | [ZeroLu/Ultimate-AI-Media-Generator-Skill](https://github.com/ZeroLu/Ultimate-AI-Media-Generator-Skill) | [scenario-labs/skills](https://github.com/scenario-labs/skills) | [vargHQ/skills](https://github.com/vargHQ/skills) |
| --- | --- | --- | --- | --- |
| Account or key needed | A Beatra account; no model provider keys | A CyberBara API key, stored in ~/.config/cyberbara/api_key ([source](https://github.com/ZeroLu/Ultimate-AI-Media-Generator-Skill/blob/f28e58f2b9814b2056417377c46f34fd35219702/README.md#L68-L76)) | A Scenario account (OAuth) or a Scenario API key ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L105)) | A VARG_API_KEY, required for all skills ([source](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/README.md#L70)) |
| Models | Text to image 10; Image to image 10; Image editing 6; Image understanding 1; Text to video 9; Image to video 9; Reference to video 9; First and last frames to video 8; Video editing 8; Video extension 7; Video understanding 1; Text to music 2; Reference audio to music 2; Text to speech 2; Voice cloning 1 (Qwen Image 2.0 Fast, Qwen Image 3.0, Qwen Image 3.0 Pro, GPT Image 2.5 Flare, GPT Image 2.5 Sunburst, GPT Image 2, Wan Image 2.7 Fast, Qwen Image 2.0 Pro, Wan Image 2.7 Pro, MiniMax Image 01 Live, MiniMax M3, Seedance 2.0 Mini, Wan 2.7, Wan 3.0 Video, MiniMax H3, HappyHorse 1.1, Seedance 2.0 Fast, Seedance 2.0, Wan 3.0 Video Prime, Seedance 2.5, Wan 2.7 Video Edit, HappyHorse 1.0 Video Edit, Suno 6, MiniMax Music 3.0, MiniMax Speech 2.8 HD, MiniMax Speech 2.8 Turbo, MiniMax Voice Clone) | CyberBara models: Nano Banana 2, GPT Image 2, Midjourney v7, Seedream 5 Pro, Sora 2, Seedance 2.5, Kling, Veo 3.1, MiniMax H3, Suno ([source](https://github.com/ZeroLu/Ultimate-AI-Media-Generator-Skill/blob/f28e58f2b9814b2056417377c46f34fd35219702/README.md#L172-L207)) | Image, video, audio and 3D models on Scenario, e.g. GPT Image, Seedream, Veo, Kling, Seedance, ElevenLabs, MiniMax music ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L247-L299)) | Kling, Flux, ElevenLabs, Sora and more through the varg platform ([source](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/README.md#L3)) |
| Before spending | Paid renders run only when you ask for that exact render or approve its card, which shows the live credit estimate | `quote` CLI command returns `estimated_credits` and `can_afford` before submission ([source](https://github.com/ZeroLu/Ultimate-AI-Media-Generator-Skill/blob/f28e58f2b9814b2056417377c46f34fd35219702/README.md#L105-L115)) | Dry-run price estimates in its quality-gate and model-comparison skills ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L208-L210)) | A free `--preview` render before the full render ([source](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/README.md#L158-L160)) |
| Agents | Claude Code, Cursor, Codex, Windsurf, Cline, OpenClaw | OpenClaw, Claude Code, Codex, Claude Cowork, Cursor, Antigravity ([source](https://github.com/ZeroLu/Ultimate-AI-Media-Generator-Skill/blob/f28e58f2b9814b2056417377c46f34fd35219702/README.md#L31-L36)) | Claude Code, Cursor, Codex, Copilot and 70+ others ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L30)) | Claude Code, Cursor, Windsurf, OpenCode, ClawHub and any Agent Skills tool ([source](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/README.md#L10)) |
| Install | `npx skills add beatra-ai/ai-media-generator-skill` | `npx skills add ZeroLu/Ultimate-AI-Media-Generator-Skill --all` ([source](https://github.com/ZeroLu/Ultimate-AI-Media-Generator-Skill/blob/f28e58f2b9814b2056417377c46f34fd35219702/README.md#L60)) | `npx skills add scenario-labs/skills`, then connect the Scenario MCP server (https://mcp.scenario.com/mcp) ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L89-L105)) | `npx skills add vargHQ/skills` ([source](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/README.md#L59)) |
| License | MIT-0 | MIT ([source](https://github.com/ZeroLu/Ultimate-AI-Media-Generator-Skill/blob/f28e58f2b9814b2056417377c46f34fd35219702/LICENSE)) | MIT ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/LICENSE)) | MIT ([source](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/LICENSE)) |
| Last updated | Updated with every release (v2.9.9) | 2026-09-08 ([source](https://github.com/ZeroLu/Ultimate-AI-Media-Generator-Skill/commit/f28e58f2b9814b2056417377c46f34fd35219702)) | 2026-10-15 ([source](https://github.com/scenario-labs/skills/commit/49dd26e47371163ae0020c7f5627d0993626bfc2)) | 2026-10-01 ([source](https://github.com/vargHQ/skills/commit/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d)) |

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

- Website — https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-media-generator-skill
- Docs — https://docs.beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-media-generator-skill
- Console — https://console.beatra.ai
- For AI agents — https://beatra.ai/llms.txt (index) · https://beatra.ai/llms-full.txt (every skill in one file)
