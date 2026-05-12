---
name: image2-seedance-control
version: 1.1.0
description: Transform vague AI video ideas, scripts, AI live-action drama episodes, webtoon episodes, creative shorts, product ads, MV concepts, reference images, or reference videos into a single deliverable file containing GPT Image 2 prompts for Seedance 2.0 control boards. Use when the user wants to produce AI video by first generating Image2 visual control charts/assets/storyboards/continuity bibles, then uploading those images to Seedance 2.0. Also use for industrialized AIGC video production requiring project continuity bibles, asset locking, shot seam review, multi-segment consistency, or Seedance repair SOP. Trigger on requests such as "做成 image2 提示词", "拿图去 Seedance 出视频", "设计 Seedance 能看懂的图", "真人剧/漫剧按集生产", "模糊想法转分镜图", "工业化生产", "镜头接缝审核", "Seedance 返修", or "只给我 image2 的提示词文件".
---

# Image2 Seedance Control

## Goal

Create one final file only: an Image2 prompt file that the user can use to generate visual control board images, then upload those images to Seedance 2.0 for video generation.

The skill must behave like a director + production designer + storyboard supervisor. The final deliverable is not an explanation — it is one file containing Image2 prompts.

## Modular Prompt Library

This skill has a growing prompt reference library. **Always read `references/prompt-library-index.md` first** — it contains the Loading Decision Table that maps project conditions to the exact reference files to load.

Four branches:

- `references/asset-prompts/` — character, scene, prop, style boards
- `references/storyboard-prompts/` — shot/timing boards for Seedance
- `references/seedance-prompts/` — Seedance 2.0 text prompt templates (dual-control pairs)
- `references/production-sop/` — continuity bibles, seam review, repair SOP, self-review checklist

Load only the branches and files triggered by the current project type. When the user provides a high-quality reference prompt, save or merge its reusable technique into the proper branch and update the index.

## Output Contract

After requirements are clear, create exactly one Markdown file in the current workspace unless the user specifies another path.

Default filename: `image2_seedance_control_prompts.md`

The file may contain multiple Image2 prompts depending on project length, but it is still one file. Prompts are grouped into:

1. **Asset design prompts** — character, scene, prop as separate reference images.
2. **Storyboard prompts** — shot/timing boards for Seedance, using asset images as references.
3. **Seedance 2.0 text prompts** — one per storyboard, translating it into explicit shot-by-shot execution language.

**Critical rules:**
- Never force asset design and storyboard into one image.
- Never use vague Seedance wording like "请参考此图". The Image2 board + Seedance text prompt form a **dual-control pair** — board controls visual reference, text controls execution.
- Before finalizing, self-review every prompt against `references/production-sop/prompt-self-review-checklist.md` (10-point check).
- For multi-segment work, every segment's timecode starts at `0:00` and ends ≤ `0:15`. Track total runtime only in production notes.
- Final response: only link to the created file and say it's ready. Do not paste the full prompt in chat unless asked.

Output file skeleton:

```markdown
# Image2 Seedance Control Prompts

## Project Settings
- 片名 / 类型 / 画幅 / 总时长 / 风格 / 生产策略

## Usage
(中文使用说明：资产板→故事板→Seedance双重控制流程)

## Production Control
- 项目圣经 / 角色状态 / 场景空间 / 道具状态 / 风格光线 / 声音VFX / 情绪递进 / 镜头接缝 / 禁止漂移

## Asset Design Prompts
### Prompt A01 - Character Asset Board - CHAR_A
### Prompt A02 - Scene Asset Board - SCENE_01
...

## Storyboard Prompts
### Prompt S01 - Scene 01 Segment 01 Storyboard
(时间码从 0:00 开始，≤0:15)

### Seedance Prompt S01 - Scene 01 Segment 01 Video
(@[AssetRef] 职责声明 → 逐镜头时间线 S01/S02... → 起始终结状态 → 连续性 → 禁止项)
```

Do not include long production essays. Include only what helps the user generate boards.

## Input Routing

Classify the user input before producing prompts:

| Type | Description |
|---|---|
| `IDEA_ONLY` | Vague idea, e.g. "金刚大战哥斯拉" |
| `SHORT_SCRIPT` | Short script, outline, ad concept, MV concept, creative short |
| `LIVE_ACTION_DRAMA_EPISODE` | AI 真人剧, 仿真人剧, 1-3 min episode |
| `WEBTOON_EPISODE` | 漫剧 / 短剧单集 |
| `ASSETS_OR_REFERENCE_READY` | User provides character/scene/prop images, screenshots, or reference video |

## Requirement Clarification

For `IDEA_ONLY`: ask concise questions first. Collect only production-critical info — duration, aspect ratio, style (suggest 2-3), type, characters, conflict, target platform, existing assets. If the user is unsure, recommend a direction instead of asking endless questions.

For `SHORT_SCRIPT` / `LIVE_ACTION_DRAMA_EPISODE` / `WEBTOON_EPISODE`: give a short director recommendation (what to keep, simplify, where the hook is, where to split into Seedance-friendly segments), then create the prompt file.

## Existing Asset Handling

When the user provides existing assets, treat them as the primary source of truth. Do not skip asset design — first formalize the assets into prompts, then storyboard.

Workflow:
1. Label assets: `CHAR_A`, `CHAR_B`, `SCENE_01`, `PROP_PHONE`, `STYLE_REF_01`, etc.
2. Extract visible invariants (face, body, hair, wardrobe, scene geography, light, prop shape/material).
3. Create formal asset design prompts that preserve user assets.
4. Only then create storyboard prompts that strictly bind to asset codes.
5. Every storyboard prompt must state: the uploaded assets are the highest-priority reference.

Use strong binding language:

```text
以用户上传的资产图为最高优先级参考。故事板中的人物、场景、道具必须严格继承资产图的身份、比例、造型、服装、材质、颜色、位置逻辑和视觉气质。不得重新设计，不得随机替换，不得脸漂移、服装漂移、场景漂移或道具漂移。
```

If the asset is incomplete, extend conservatively — fill only what's necessary, never redesign.

## Prompt Group Planning Rules

Always split into **asset prompts** and **storyboard prompts**.

**Asset prompts** create stable references. For user-provided assets, normalize them into Seedance-readable continuity boards (not invent new designs). Each prompt must include: asset code, what must be preserved, what may be clarified, what must never change, how it will be referenced in storyboards.

**Storyboard prompts** are director execution boards, not character design boards. They must not redesign faces, wardrobe, or identity when separate asset boards exist. They control shot order, timing, staging, action, camera, dialogue, sound, edit points, and continuity.

Every storyboard prompt must be immediately followed by a corresponding **Seedance 2.0 text prompt** that restates the same shot order, timecodes, action, camera, dialogue, sound/VFX, emotion, start/end state, and forbidden drift — as executable language, not generic instruction.

For multi-segment work: Seedance prompts describe previous/next segment relationship as start/end state, not cumulative timecode.

See the index's Loading Decision Table for which specific asset/storyboard/seedance pattern files to load per project condition.

## Industrial Production Control

For multi-segment, multi-scene, 1-3 minute, or episode-based projects, add production control before writing prompts.

Load these SOPs by condition:

| Condition | Load |
|---|---|
| Recurring characters/scenes/props, multi-episode | `references/production-sop/project-continuity-bible.md` |
| Multiple shots or segments | `references/production-sop/shot-seam-review.md` |
| Seedance output has drift/motion/continuity failure | `references/production-sop/seedance-repair-sop.md` |
| Before delivering any prompt file | `references/production-sop/prompt-self-review-checklist.md` |

Pipeline for long productions:

```text
project bible → asset boards → scene geography → storyboard segments → seam review → Seedance generation → repair SOP → final continuity review
```

## Board Planning Rules

Choose board count by story need, not by maximum capacity:

- 15s simple clip: 1-3 asset prompts + 1 storyboard
- 30-60s short: assets for all recurring elements + 3-5 storyboards
- 1-3min drama: per-episode assets + storyboards per scene
- Each Seedance segment: 4-15s (15s is the max, not the default)
- Panel counts: 4 for emotional moments, 5-6 for hooks, 8 for turns, 12 for standard 10-15s, 16-25 for planning overview only

## Image2 Board Design Standard

Every Image2 prompt must ask for a visual control chart Seedance can read from the image:

- Clean production-board layout, not a decorative poster.
- Large, legible printed labels. Bilingual short labels where helpful: `S01 / 0-2s / CLOSE-UP / 近景`.
- Clear panel numbers and arrows for order. Color-coded zones.
- One consistent visual style across all boards in the same project.
- Visuals carry identity, action, staging, camera, and continuity — do not rely on long in-image text.

## Image2 Prompt Writing Rules

Write Image2 prompts in Chinese by default. Use English only for short visual labels: CLOSE-UP, WIDE SHOT, OVER-THE-SHOULDER, TRACKING, MATCH CUT, DO NOT CHANGE FACE.

Each prompt must specify: canvas ratio, visual style, board title, panel count, region contents, label readability, continuity constraints, negative constraints.

Storyboard prompts additionally require: shot number, timecode, shot size, visual content, action, dialogue/line, camera method, camera parameters, edit note, asset references.

## Seedance Compatibility Rules

Design boards and Seedance text prompts as dual-control pairs — the board is readable as an image; the matching prompt executes the same storyboard even if Seedance misses part of the visual intent.

- **Asset boards** visually encode: stable references, drift prohibitions, exact identity, source-of-truth when based on user assets.
- **Storyboard boards** visually encode: who appears, where, what changes over time, camera movement, shot size, dialogue intention, start/end state, next-shot handoff.
- **Seedance prompts** textually encode: same shot order/timecodes as storyboard, same character/scene/prop/VFX/dialogue/sound/emotion, same camera logic, explicit continuity and forbidden drift.

Avoid: tiny text labels, abstract mood boards, random decorative UI, 25+ panel boards for single Seedance clips, incompatible costume/face options, asking Image2 to generate exact long paragraphs in-image.

## Final Response Rule

After creating the file, reply briefly:

```text
已做好：[filename](absolute/path)
```

Mention any unresolved assumption only if it materially affects production.
