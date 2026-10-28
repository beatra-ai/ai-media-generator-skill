# AI Media Generator Skill

[English](./README.md) | [简体中文](./README.zh-CN.md) | 日本語

> 👉 こちらもどうぞ [AI Image Generator Skill](https://github.com/beatra-ai/ai-image-generator-skill)

AI 画像・動画・音楽・ナレーションを 1 つのエージェントスキルから作成。Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw のどれからでもそのまま使えます。

> [!IMPORTANT]
> 生成には [Beatra](https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-media-generator-skill) アカウントが必要で、クレジットを消費します。スキル自体のインストールは無料です。

| 項目 | 内容 |
| --- | --- |
| **できること** | 同じ接続でAI画像、動画、音楽、音声を作成し、公開ソーシャルデータを調べ、対応する画像や動画を編集しながら、返されたファイルと実際のクレジット使用量を確認できます。 |
| **モデル** | Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro、MiniMax Image 01 Live、MiniMax M3、Seedance 2.0 Mini、Wan 2.7、Wan 3.0 Video、MiniMax H3、HappyHorse 1.1、Seedance 2.0 Fast、Seedance 2.0、Wan 3.0 Video Prime、Seedance 2.5、Wan 2.7 Video Edit、HappyHorse 1.0 Video Edit、Suno 6、MiniMax Music 3.0、MiniMax Speech 2.8 HD、MiniMax Speech 2.8 Turbo、MiniMax Voice Clone |
| **動作要件** | Python 3.10 以上と、`SKILL.md` を読み込めるエージェント |
| **費用** | インストールは無料。生成のたびに Beatra アカウントのクレジットを消費しますが、課金されるのは、その生成を明示的に依頼したとき、または確認カードを承認したときだけです。 |
| **対応エージェント** | Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw |

<p align="center"><img src="assets/hero.webp" width="800" alt="1 つのエージェントセッションで作った 3 種類の画像：架空の炭酸水缶 Tidewell の商品写真、在宅勤務をテーマにしたフラットなベクター調ブログヘッダー、夕暮れの嵐の中の灯台を描いたシネマティックなコンセプトフレーム。Beatra AI で生成。"></p>

*1 つのエージェントセッションで作った 3 種類の画像：架空の炭酸水缶 Tidewell の商品写真、在宅勤務をテーマにしたフラットなベクター調ブログヘッダー、夕暮れの嵐の中の灯台を描いたシネマティックなコンセプトフレーム。Beatra AI で生成。*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`beatra`](skills/beatra) | [SKILL.md](skills/beatra/SKILL.md) | 2.9.9 |

このリポジトリは [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/beatra) から自動的に公開されています。問題の報告はそちらへお願いします。

## インストール

[`skills`](https://skills.sh) CLI を使う場合：

```bash
npx skills add beatra-ai/ai-media-generator-skill
```

Claude Code プラグインとして：

```bash
claude plugin marketplace add beatra-ai/ai-media-generator-skill
claude plugin install beatra@ai-media-generator-skill
```

Codex プラグインとして：

```bash
codex plugin marketplace add beatra-ai/ai-media-generator-skill
codex plugin add beatra@ai-media-generator-skill
```

GitHub Copilot CLI プラグインとして：

```bash
copilot plugin marketplace add beatra-ai/ai-media-generator-skill
copilot plugin install beatra@ai-media-generator-skill
```

Gemini CLI 拡張機能として：

```bash
gemini extensions install https://github.com/beatra-ai/ai-media-generator-skill
```

GitHub CLI を使う場合：

```bash
gh skill install beatra-ai/ai-media-generator-skill beatra
```

または、このリポジトリをクローンして `skills/beatra` を次の場所にコピーします：Claude Code は `~/.claude/skills/`、Cursor は `~/.cursor/skills/`、Codex は `~/.agents/skills/`、Windsurf は `~/.codeium/windsurf/skills/`、Cline は `~/.cline/skills/`、OpenClaw は `~/.openclaw/skills/`。

または、次の文をエージェントに貼り付けてください：

```text
https://github.com/beatra-ai/ai-media-generator-skill から beatra スキル（フォルダ skills/beatra）をインストールし、その SKILL.md に従って私の Beatra アカウントに接続してください。
```

## 技術仕様と出力上限

2026-10-18 時点。最新の一覧：https://docs.beatra.ai/ja/docs/models

- **アップロード** — 1 ファイルあたり最大 100 MB。下記の各モデルの入力制限も適用されます
- **テキストから画像** — 10 モデル（Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro、MiniMax Image 01 Live）／PNG／1 リクエストあたり最大 4 枚／キャンバス最大 16.8 MP
  - 16.8 MP（4K ティア）：Wan Image 2.7 Pro（1 リクエストあたり最大 4 枚）／GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2（1 リクエストにつき 1 枚）
- **画像から画像** — 10 モデル（Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro、GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2、MiniMax Image 01 Live）／PNG／1 リクエストあたり最大 4 枚／キャンバス最大 16.8 MP
  - 16.8 MP（4K ティア）：GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2（1 リクエストにつき 1 枚）
  - 入力画像：1 リクエストあたり最大 4 枚、各 10〜20 MB／BMP、GIF、JPEG、PNG、TIFF、WEBP
- **画像編集** — 6 モデル（Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro）／PNG／1 リクエストあたり最大 4 枚／キャンバス最大 4.2 MP
  - 4.2 MP（2K ティア）：Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro（1 リクエストあたり最大 4 枚）
  - 入力画像：1 リクエストあたり最大 4 枚、各 10〜20 MB／BMP、GIF、JPEG、PNG、TIFF、WEBP
- **画像理解** — 1 モデル（MiniMax M3）／1 リクエストあたり最大 8 ファイル／各最大 10 MB
- **テキストから動画** — 9 モデル（Seedance 2.0 Mini、Wan 2.7、Wan 3.0 Video、MiniMax H3、HappyHorse 1.1、Seedance 2.0 Fast、Seedance 2.0、Wan 3.0 Video Prime、Seedance 2.5）／480p〜4K／2〜30 秒／アスペクト比 16:9、1:1、21:9、3:4、4:3、9:16、4:5、5:4、9:21／MOV、MP4
  - 4K：Seedance 2.0、最長 15 秒
  - 30 秒：Wan 3.0 Video、Wan 3.0 Video Prime、Seedance 2.5、最高 1080p
  - ネイティブ音声：Wan 2.7、MiniMax H3
- **画像から動画** — 9 モデル（Wan 2.7、Wan 3.0 Video、MiniMax H3、Seedance 2.0 Mini、HappyHorse 1.1、Seedance 2.0 Fast、Seedance 2.0、Wan 3.0 Video Prime、Seedance 2.5）／480p〜4K／2〜30 秒／アスペクト比 16:9、1:1、21:9、3:4、4:3、9:16／MOV、MP4
  - 4K：Seedance 2.0、最長 15 秒
  - 30 秒：Wan 3.0 Video、Wan 3.0 Video Prime、Seedance 2.5、最高 1080p
  - ネイティブ音声：Wan 2.7、MiniMax H3
- **参照素材から動画** — 9 モデル（Wan 2.7、MiniMax H3、Wan 3.0 Video、HappyHorse 1.1、Seedance 2.0 Mini、Seedance 2.0 Fast、Seedance 2.0、Wan 3.0 Video Prime、Seedance 2.5）／480p〜4K／2〜30 秒／アスペクト比 16:9、1:1、3:4、4:3、9:16、21:9、4:5、5:4、9:21／MOV、MP4
  - 4K：Seedance 2.0、最長 15 秒
  - 30 秒：Wan 3.0 Video、Wan 3.0 Video Prime、Seedance 2.5、最高 1080p
  - ネイティブ音声：Wan 2.7、MiniMax H3
- **最初と最後のフレームから動画** — 8 モデル（Wan 2.7、Wan 3.0 Video、MiniMax H3、Seedance 2.0 Mini、Seedance 2.0 Fast、Seedance 2.0、Wan 3.0 Video Prime、Seedance 2.5）／480p〜4K／2〜30 秒／アスペクト比 16:9、1:1、21:9、3:4、4:3、9:16／MOV、MP4
  - 4K：Seedance 2.0、最長 15 秒
  - 30 秒：Wan 3.0 Video、Wan 3.0 Video Prime、Seedance 2.5、最高 1080p
  - ネイティブ音声：Wan 2.7、MiniMax H3
- **動画編集** — 8 モデル（Wan 2.7 Video Edit、Wan 3.0 Video、HappyHorse 1.0 Video Edit、Seedance 2.0 Mini、Seedance 2.0 Fast、Seedance 2.0、Wan 3.0 Video Prime、Seedance 2.5）／480p〜4K／2〜30 秒／アスペクト比 16:9、1:1、3:4、4:3、9:16、21:9／MOV、MP4
  - 4K：Seedance 2.0、最長 15 秒
  - 30 秒：Wan 3.0 Video、Wan 3.0 Video Prime、Seedance 2.5、最高 1080p
- **動画の延長** — 7 モデル（Wan 2.7、Wan 3.0 Video、Seedance 2.0 Mini、Seedance 2.0 Fast、Seedance 2.0、Wan 3.0 Video Prime、Seedance 2.5）／480p〜4K／2〜30 秒／アスペクト比 16:9、1:1、21:9、3:4、4:3、9:16／MOV、MP4
  - 4K：Seedance 2.0、最長 15 秒
  - 30 秒：Wan 3.0 Video、Wan 3.0 Video Prime、Seedance 2.5、最高 1080p
  - ネイティブ音声：Wan 2.7
- **動画理解** — 1 モデル（MiniMax M3）／1 リクエストにつき 1 ファイル／各最大 50 MB／最長 360 秒／1 fps でサンプリング
- **テキストから音楽** — 2 モデル（Suno 6、MiniMax Music 3.0）／MP3
  - Suno 6：プロンプトは最大 500、歌詞は最大 5000、タイトルは最大 80 文字
  - MiniMax Music 3.0：プロンプトは最大 2000、歌詞は最大 3500、タイトルは最大 100 文字
- **参照音声から音楽** — 2 モデル（Suno 6、MiniMax Music 3.0）／MP3
  - Suno 6：プロンプトは最大 500、歌詞は最大 5000、タイトルは最大 80 文字／参照音声 6〜480 秒（FLAC、MP3、WAV）
  - MiniMax Music 3.0：プロンプトは最大 300、歌詞は最大 1000、タイトルは最大 100 文字／参照音声 6〜360 秒、最大 50 MB（FLAC、MP3、WAV）
- **音声合成** — 2 モデル（MiniMax Speech 2.8 HD、MiniMax Speech 2.8 Turbo）／FLAC、MP3、OPUS、PCM、WAV／40 言語／サンプルレート 8、16、22.05、24、32、44.1 kHz／1 リクエストあたり最大 50000 文字
  - 言語（ISO 639 コード）：zh, yue, en, es, fr, ru, de, pt, ar, it, ja, ko, id, vi, tr, nl, uk, th, pl, ro, el, cs, fi, hi, bg, da, he, ms, fa, sk, sv, hr, fil, hu, no, sl, ca, nn, ta, af
- **ボイスクローン** — 1 モデル（MiniMax Voice Clone）／サンプル 10〜300 秒、最大 20 MB／本人の同意確認が必要


## 更新とセキュリティ

2026 年 10 月のリリース以降、このスキルに自動更新機能はありません。インストールしたファイルだけを実行し、
自動的に置き換えることはありません。更新はインストールに使ったツール（`npx skills update beatra` または
`gh skill update beatra`）で行ってください。詳細はスキル内の `references/updates-and-security.md` を参照してください。

## ライセンス

[MIT-0](LICENSE)：商用を含め、自由に使用・改変・再配布できます。クレジット表記は不要です。ClawHub 上のこれらのスキルと同じ条件です。

## リンク

- ウェブサイト — https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-media-generator-skill
- ドキュメント — https://docs.beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-media-generator-skill
- コンソール — https://console.beatra.ai
- AI エージェント向け — https://beatra.ai/llms.txt （インデックス）· https://beatra.ai/llms-full.txt （全スキルを 1 ファイルに）
