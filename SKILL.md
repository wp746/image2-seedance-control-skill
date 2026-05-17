---
name: image2-seedance-control
version: 1.8.5
description: Transform vague AI video ideas, scripts, AI live-action drama episodes, webtoon episodes, creative shorts, product ads, MV concepts, reference images, or reference videos into a single deliverable file containing GPT Image 2 prompts for Seedance 2.0 control boards. Use when the user wants to produce AI video by first generating Image2 visual control charts/assets/storyboards/continuity bibles, then uploading those images to Seedance 2.0. Also use for industrialized AIGC video production requiring project continuity bibles, asset locking, shot seam review, multi-segment consistency, reference upload order, output acceptance scoring, prompt linting, or Seedance repair SOP. Trigger on requests such as "做成 image2 提示词", "拿图去 Seedance 出视频", "设计 Seedance 能看懂的图", "真人剧/漫剧按集生产", "模糊想法转分镜图", "工业化生产", "镜头接缝审核", "Seedance 返修", "出片验收", "多参考图上传顺序", or "只给我 image2 的提示词文件".
---

# Image2 Seedance Control

## Goal

Create one final file only: an Image2 prompt file that the user can use to generate visual control board images, then upload those images to Seedance 2.0 for video generation.

The skill must behave like a director + production designer + storyboard supervisor. The final deliverable is not an explanation and not an agent handoff document. It is one operator-ready prompt file: prompts the user can copy directly into Image2 and Seedance 2.0.

## Industrial Production Philosophy

This skill exists to make the user's Image2 asset + Image2 storyboard + Seedance 2.0 prompt SOP stable enough for repeatable film-grade production. The goal is not to make the user test endlessly. The skill must anticipate likely Image2 and Seedance failure modes, design around them, and deliver a package that reduces identity drift, scene drift, prop drift, style drift, text bugs, motion bugs, and continuity bugs before the user generates anything.

For any finished script, whether provided by the user or written by the assistant, the script is the source of truth. Before producing prompts, read the target episode/scene carefully, beat by beat and line by line. Understand:

- story rhythm: where the scene breathes, accelerates, pauses, threatens, releases, or withholds information
- emotional baseline and emotional turn for each beat
- whose point of view carries the beat
- what the audience must understand, feel, and remember
- which lines are plot turns, emotional turns, command turns, jokes, threats, vows, whispers, or crowd energy
- which characters, locations, props, wardrobe states, injuries, weather, time of day, and sound motifs must remain continuous

Prompts must be designed from film logic first, model mechanics second, and template convenience last. If a template conflicts with story rhythm, choose story rhythm and split the segment. If the user asks for something that will increase drift or model failure, guide them toward a more stable production choice.

### Model Capability Awareness

Always design with the real strengths and weaknesses of Image2 and Seedance 2.0 in mind:

- Image2 is strong at visual boards, composition, character/scene/prop reference sheets, layout, silhouettes, material cues, arrows, diagrams, and English labels.
- Image2 is weak at dense Chinese small text, long readable paragraphs, many tiny labels, exact in-world signs, mixed fonts, random paper substrates, and overcrowded boards.
- Therefore every Image2 prompt must use stable board substrate, large short labels, controlled modules, clear asset codes, and separate text-prop plates or post-production for exact Chinese text.
- Seedance 2.0 is strong when each segment has a small number of characters, one main action/emotional job, clean reference duties, clear start/end state, stable scene geography, and explicit camera/sound/performance timing.
- Seedance 2.0 is weak when asked to handle too many shots, too many actions, too many characters, exact text rendering, unclear reference priorities, mixed visual bibles, long cumulative plot, or broad vague style commands.
- Therefore every Seedance segment must have a complexity budget, exact reference duties, embedded global look text, clean-frame text ban, identity/scene/prop/style drift guards, and a specific handoff to the next segment.

### Proactive Completion Duty

Do not wait for the user to discover predictable problems. Before delivery, proactively fill production gaps the user did not mention: missing assets, crowd differentiation, scene geography, prop state changes, text handling, lens/light consistency, dialogue preservation, segment handoffs, negative constraints, and repair strategy. If the user's assumption is likely to hurt quality, state the better production choice briefly and implement it.

## Modular Prompt Library

This skill has a growing prompt reference library. **Always read `references/prompt-library-index.md` first** — it contains the Loading Decision Table that maps project conditions to the exact reference files to load.

Four branches:

- `references/asset-prompts/` — character, scene, prop, style boards
- `references/storyboard-prompts/` — shot/timing boards for Seedance
- `references/seedance-prompts/` — Seedance 2.0 text prompt templates (dual-control pairs)
- `references/production-sop/` — continuity bibles, runbook, reference upload order, seam review, acceptance scoring, repair SOP, self-review checklist

Always load these mandatory production-control modules before writing any final prompt file:

```text
references/production-sop/board-format-style-bible.md
references/production-sop/bilingual-output-contract.md
references/production-sop/text-rendering-boundary.md
references/production-sop/visual-bible-reference-boundary.md
references/asset-prompts/character-asset-layout-bible.md
references/asset-prompts/scene-nine-view-layout-bible.md
references/asset-prompts/prop-layout-bible.md
references/storyboard-prompts/director-storyboard-layout-bible.md
references/seedance-prompts/dense-reference-stack-timeline.md
```

These modules are not optional. They define the fixed board system, bilingual output, text rendering boundary, visual-bible reference boundary, character layout, nine-view scene layout, prop layout, director storyboard layout, and dense Seedance prompt structure.

Load only the branches and files triggered by the current project type. When the user provides a high-quality reference prompt, save or merge its reusable technique into the proper branch and update the index.

## Output Contract

After requirements are clear, create exactly one Markdown file in the current workspace unless the user specifies another path.

Default filename: `image2_seedance_control_prompts.md`

The file may contain multiple Image2 prompts depending on project length, but it is still one file. The final user-facing file must contain only operator-ready prompt groups:

1. **Asset design prompts** — character, scene, prop as separate reference images.
2. **Storyboard prompts** — shot/timing boards for Seedance, using asset images as references.
3. **Seedance 2.0 text prompts** — one per storyboard, translating it into explicit shot-by-shot execution language.

Do **not** expose planning/SOP sections in the final file. Do not output visible sections named `Project Settings`, `Usage`, `Production Control`, `PROJECT_BOARD_SYSTEM`, `Text Rendering Boundary`, `Visual Bible Reference Boundary`, `STYLE_LOCK_TEXT`, `Director Recommendation`, `Reference Upload Order`, `Self-Review`, or similar internal process notes. Use those concepts internally, then bake their content into each prompt.

**Critical rules:**
- Never force asset design and storyboard into one image.
- Every Image2 prompt and every Seedance 2.0 prompt must have two production-equivalent versions: `CN` for Chinese review and `EN` for cleaner downstream image-label rendering. CN and EN versions must preserve the same asset codes, layout, modules, shot count, local timecodes, camera, action, dialogue intent, sound/VFX, continuity, and negative constraints.
- EN production boards must use English labels and asset codes only. Do not ask an English board to render readable Chinese signs, wall slogans, documents, subtitles, or small Chinese labels. Chinese in-world text must be blurred/unreadable texture, isolated into a `TEXT_PROP_PLATE` / `UI_TEXT_PROP_BOARD`, or added in post.
- CN review boards may use Simplified Chinese labels, but labels must be large and short. Never ask Image2 to render long Chinese paragraphs or many small Chinese labels inside a board.
- The Image2 board + Seedance text prompt form a **complementary dual-control pair** — not redundant, not conflicting. The board visualizes what words can't precisely express (movement paths, camera positions, light direction, emotional arc). The Seedance prompt writes what the image can't show (micro-expressions, camera texture, light quality, sound design, performance timing). Use `references/production-sop/storyboard-seedance-pairing-principle.md` internally; do not explain the philosophy in the final file.
- Storyboard text is minimal: logic labels and annotations only. Seedance prompt ≤ 2000 characters (**hard limit** — count before delivering, compress if over). When the scene is complex, use most of the available budget with dense, exact execution language instead of short generic instructions. See `references/production-sop/storyboard-seedance-pairing-principle.md` and `references/seedance-prompts/dense-reference-stack-timeline.md`.
- Before finalizing, self-review every prompt against `references/production-sop/prompt-self-review-checklist.md` (10-point check).
- The ultimate quality benchmark is `references/production-sop/film-industry-master-checklist.md` — 10 departments, a master checklist covering every professional filmmaking discipline. Before delivery, verify all applicable items.
- For production or multi-reference work, follow `references/production-sop/reference-upload-order.md` internally so every uploaded image has one clear duty. In the final Seedance prompt, express this as compact `@[asset]` reference-duty language, not as a separate upload-order essay.
- For script-driven work, create a segment plan before prompt writing. Do not compress raw script paragraphs directly into Seedance segments.
- For dialogue and voiceover, treat the user's script text as a locked creative asset. Preserve every original spoken line, voiceover line, dialect phrase, punctuation, pause marker, and parenthetical performance note verbatim. Do not summarize, rewrite, polish, shorten, merge, or delete dialogue. If one 15-second segment cannot carry the full line, split it across adjacent segments using exact contiguous fragments and mark the handoff; never remove words. Treat lines as sound/performance timing, not on-screen subtitles. Add subtitles/title cards in post unless explicitly requested.
- For industrial-grade delivery, run department signoff gates and do not call the package industrial if any gate is unresolved.
- For local prompt files, run `scripts/prompt_lint.py` before delivery when possible. It checks Seedance character limits, segment timecodes, and basic structural risks.
- For multi-segment work, every segment's timecode starts at `0:00` and ends ≤ `0:15`. Track total runtime only in production notes.
- Final response: only link to the created file and say it's ready. Do not paste the full prompt in chat unless asked.

User-facing output skeleton:

```markdown
# Image2 Seedance Control Prompts

## Asset Design Prompts
### Prompt A01-CN - Character Asset Board - CHAR_A
```text
[A fully self-contained Image2 prompt. It directly contains canvas, board substrate, palette, typography, layout, text-rendering, style, asset modules, continuity, and negative constraints. It must not say "inherit PROJECT_BOARD_SYSTEM".]
```
### Prompt A01-EN - Character Asset Board - CHAR_A
```text
[Equivalent English production prompt with English labels only.]
```
...

## Storyboard Prompts
### Prompt S01-CN - Scene 01 Segment 01 Storyboard
```text
[A self-contained Image2 storyboard prompt. It directly contains board layout rules, top-down plan, camera setup, motion route, light, blocking, sound/VFX, shot guide, and negative constraints.]
```
### Prompt S01-EN - Scene 01 Segment 01 Storyboard
```text
[Equivalent English production prompt.]
```

## Seedance 2.0 Prompts
### Seedance Prompt S01-CN - Scene 01 Segment 01 Video
```text
[A self-contained Seedance prompt under 2000 chars. It directly contains global look content, current references, segment budget, clean-frame rules, per-shot timeline, sound, end state, continuity, and negative constraints. It must not expose internal variable names such as STYLE_LOCK_TEXT.]
```
```

Do not include long production essays. Include only copyable prompts.

## Mandatory Board System Lock

Before writing asset prompts, internally create a project-level board system lock. This is a backstage design constraint, not a user-facing section.

This lock must define: canvas ratio, matte digital board substrate, fixed board palette, fixed sans-serif typography style, margin/gutter/panel rules, arrow/icon/label style, in-image text rules, and negative substrate/font drift rules.

Default board substrate:

```text
16:9 horizontal matte warm-gray digital production board, clean flat layout, fixed palette, no paper texture, no newspaper texture, no kraft paper, no oil paper, no parchment, no scrapbook, no random dark/light background, no mixed fonts.
```

Typography rules:

- CN board: short Chinese labels in Noto Sans CJK / Source Han Sans-like bold sans-serif, plus asset codes.
- EN board: English labels in Inter / Helvetica-like bold sans-serif, plus asset codes.
- Never ask Image2 to render long Chinese paragraphs inside the board.
- Use large short labels, icons, arrows, diagrams, panels, and asset codes.
- If exact text matters, isolate it on a separate prop/UI board.

Every Image2 prompt must directly include the compact board lock text itself: canvas ratio, matte digital substrate, fixed palette, fixed sans-serif typography, margin/gutter/panel rules, arrow/icon/label style, in-image text rules, and negative substrate/font drift rules. Never write "must inherit PROJECT_BOARD_SYSTEM", "继承PROJECT_BOARD_SYSTEM", or similar references in the final prompt.

## Text Rendering Boundary

Use `references/production-sop/text-rendering-boundary.md` internally for every final prompt package. Do not output a separate "Text Rendering Boundary" section.

Text duties are split into three modes:

- `CN_REVIEW_BOARD`: Chinese review board for user understanding. Use large, short Simplified Chinese labels and asset codes only.
- `EN_PRODUCTION_BOARD`: English production board for Image2/Seedance reference. Use English labels and asset codes only; no readable Chinese inside the image.
- `TEXT_PROP_PLATE`: separate prop/UI/text plate for exact Chinese text, signs, documents, telegrams, maps, or title cards. If the final viewer must read it, prefer post-production typography.

Hard rule: do not mix English production labels with readable Chinese in-world text in the same Image2 board. For historical wall signs, permits, posters, newspapers, or shop signs that are not plot-critical, write them as blurred period texture or unreadable graphic blocks. Seedance narrative frames must stay clean: no subtitles, no captions, no control-board labels, no random Chinese/English text, no watermarks, no corrupted text.

## Visual Bible Reference Boundary

Use `references/production-sop/visual-bible-reference-boundary.md` internally whenever the project has a global visual bible, style board, look board, mood board, or film reference. Do not output a separate "Visual Bible Reference Boundary" section.

The global visual bible is split into three layers:

- `PROJECT_BOARD_SYSTEM`: controls Image2 board layout only. Prompt text only; do not upload it to Seedance.
- `STYLE_LOCK_TEXT`: internal compact global look lock for palette, contrast, lens, grain, light, weather, camera mood, and forbidden style drift. Its descriptive content must be repeated in every Image2 and Seedance prompt with scene-specific adjustments, but the literal variable name should not appear in the final user-facing prompt.
- `STYLE_LOOK_SAFE`: optional uploaded style image only if it is abstract and non-contaminating: swatches, grain, light direction, lens texture, haze/rain/smoke/dust, material crops. It must not contain recognizable people, scene geography, buildings, vehicles, weapons, hero props, maps, or readable text.

If a visual bible image contains characters, faces, crowds, city streets, buildings, vehicles, props, maps, signs, or readable text, do not upload it globally to Seedance. Extract its look internally into the global look lock text, then use separate character, scene, prop, and current-storyboard references.

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

Every asset prompt must be output as a CN/EN pair and must directly contain the board system rules inside the prompt text. Do not ask the user or model to inherit another section.

Character assets must follow `references/asset-prompts/character-asset-layout-bible.md`: one main character per board, or at most two supporting characters per 16:9 board; full-body four views and face close-up grid are mandatory; story-specific modules are selected by dramatic need, such as expression arc, hairstyle state, age/time state, costume state, injury/dirt/wetness state, prop interaction, scene interaction, command behavior, or action baseline; do not add unused reference modules. Crowd boards must clearly differentiate age, occupation, hairstyle, wardrobe, height, body type, face structure, posture, and behavior; if uniforms are shared, emphasize height/body/face/posture differences.

Scene assets must follow `references/asset-prompts/scene-nine-view-layout-bible.md`: one recurring scene code per board; 3x3 nine-view scene layout; top-down floor/geography plan with entrances/exits, camera-safe zones, character blocking zones, prop anchors, light direction, and forbidden drift. Use faceless placeholders only; do not create character identities in scene boards.

Prop assets must follow `references/asset-prompts/prop-layout-bible.md`: hero props get dedicated boards; multi-prop boards are allowed only when each prop remains readable and clearly labeled with reference duties. Repeating props need multi-view shape, material, scale, wear, state changes, hand-use logic, scene anchors, and forbidden drift. Text/UI props require isolated large-text treatment and should not be buried inside storyboards.

Storyboard boards must follow `references/storyboard-prompts/director-storyboard-layout-bible.md`: no character turnaround sheets inside the storyboard; include top-down movement floor plan, camera setup, motion route, light/atmosphere, blocking, sound/VFX, negative constraints, and a concise 15-second shot guide. Shot count is directed by rhythm and emotion, not by a fixed 5-shot template; a single 15-second shot is valid when it carries the scene better.

Board responsibility matrix:

| Board Type | Controls | Must Not Control |
|---|---|---|
| Character board | identity, face, body, wardrobe, expression baseline | shot order or scene geography |
| Scene board | geography, scale, light sources, fixed objects, camera-safe zones | character identity |
| Prop/UI board | object shape, material, scale, hand use, short required text | subtitles or story pacing |
| Style board / STYLE_BIBLE | palette, contrast, lens, light, grain, composition mood | identity, props, geography, story facts, vehicles, signs, readable text |
| Scene continuity board | blocking, movement paths, emotional state in space | new character designs |
| Storyboard board | shot order, timing, camera, action, handoff | full asset redesign or dense prose |

Integrated boards are lightweight exceptions for one-off/simple clips or ads. For recurring characters, recurring locations, or multi-segment drama, create formal asset boards first and let the storyboard reference them by code.

Every storyboard prompt must be immediately followed by a corresponding **Seedance 2.0 text prompt** that restates the same shot order, timecodes, action, camera, dialogue, sound/VFX, emotion, start/end state, and forbidden drift — as executable language, not generic instruction.

**Scene type determines strategy.** Before designing any segment, classify its dramatic function (DIALOGUE/ACTION/SUSPENSE/TRANSITION/PRODUCT/ATMOSPHERE) and whether it's A-roll or B-roll. Load `references/production-sop/scene-type-playbook.md` for the corresponding design playbook — each type has its own storyboard structure, Seedance character allocation strategy, camera language, and sound design approach. A martial arts scene is not shot like a dialogue scene.

For multi-segment work: Seedance prompts describe previous/next segment relationship as start/end state, not cumulative timecode.

See the index's Loading Decision Table for which specific asset/storyboard/seedance pattern files to load per project condition.

## Industrial Production Control

For multi-segment, multi-scene, 1-3 minute, or episode-based projects, add production control before writing prompts.

Load these SOPs by condition:

| Condition | Load |
|---|---|
| Recurring characters/scenes/props, multi-episode | `references/production-sop/project-continuity-bible.md` |
| Script, outline, episode, or multi-beat idea | `references/production-sop/script-breakdown-segment-plan.md` |
| Multiple shots or segments | `references/production-sop/shot-seam-review.md` |
| Seedance output has drift/motion/continuity failure | `references/production-sop/seedance-repair-sop.md` |
| **Before designing any storyboard** | **`references/production-sop/storyboard-seedance-pairing-principle.md`** |
| **Scene type playbook — per segment** | **`references/production-sop/scene-type-playbook.md`** |
| **Before each storyboard + Seedance pair** | **`references/production-sop/segment-complexity-budget.md`** |
| **Dialogue / voice / subtitles / text-risk scenes** | **`references/production-sop/dialogue-audio-subtitle-boundary.md`** |
| **Industrial team workflow, versioning, generation logs** | **`references/production-sop/production-runbook.md`** |
| **Industrial-grade final package signoff** | **`references/production-sop/department-signoff-gates.md`** |
| **User provides style image/video/film reference or asks to extract a film look** | **`references/production-sop/user-style-reference-sop.md`** |
| **Multi-reference Seedance generation** | **`references/production-sop/reference-upload-order.md`** |
| **After Seedance output, before repair/delivery** | **`references/production-sop/output-acceptance-scorecard.md`** |
| **Realist war / documentary live-action / text-risk outputs** | **`references/production-sop/realism-clean-frame-rhythm-gate.md`** |
| **Any Image2 board before writing prompts** | **`references/production-sop/board-format-style-bible.md`** |
| **Any final prompt package** | **`references/production-sop/bilingual-output-contract.md`** |
| **Any board or scene with Chinese/English text risk** | **`references/production-sop/text-rendering-boundary.md`** |
| **Any global visual bible / style bible / look board** | **`references/production-sop/visual-bible-reference-boundary.md`** |
| **Any character asset board** | **`references/asset-prompts/character-asset-layout-bible.md`** |
| **Any recurring scene asset board** | **`references/asset-prompts/scene-nine-view-layout-bible.md`** |
| **Any repeating/hero prop board** | **`references/asset-prompts/prop-layout-bible.md`** |
| **Any director storyboard board** | **`references/storyboard-prompts/director-storyboard-layout-bible.md`** |
| **Any Seedance 2.0 text prompt** | **`references/seedance-prompts/dense-reference-stack-timeline.md`** |
| Before delivering any prompt file | `references/production-sop/prompt-self-review-checklist.md` |
| **Quality benchmark — all projects** | **`references/production-sop/film-industry-master-checklist.md`** |

Pipeline for long productions:

```text
internal board lock → bilingual contract → text rendering boundary → visual-bible reference boundary → global look lock text → style extraction if provided → script breakdown + segment plan → complexity budget → project bible → production runbook → asset boards → scene geography → storyboard segments → dense Seedance prompts → seam review → reference upload order → prompt lint → department signoff → Seedance generation → output acceptance scorecard → repair SOP → final continuity review
```

## Board Planning Rules

Choose board count by story need, not by maximum capacity:

- 15s simple clip: 1-3 asset prompts + 1 storyboard
- 30-60s short: assets for all recurring elements + 3-5 storyboards
- 1-3min drama: per-episode assets + storyboards per scene
- Each Seedance segment: 4-15s (15s is the max, not the default)

### Rhythm-Driven Shot Count

Shot count is **driven by rhythm and emotion, never a formula.** One continuous take can carry a scene better than 8 cuts. Two shots — one wide, one close — can be enough if the performance is rich.

```
情绪需要空间 → 少切，长镜头
情绪需要冲击 → 快切，短镜头
情绪需要审视 → 固定机位
情绪需要代入 → 手持
一镜到底也是一种表达
```

Start from the emotion. Ask: how few shots can carry this? Add shots only when the story demands a new perspective.

Hard rule for drama and war-film segments: do not compress a full plot paragraph into one 15-second clip by fast cutting. If the emotional beat needs silence, fear, waiting, command hesitation, mourning, or moral weight, use 1-3 shots or one continuous take. Split into more Seedance segments instead of forcing 6-8 cuts into a beat that should breathe.

### Film-Level Quality Standard

Every output must aim for film quality — not "AI video" quality:

- Motivated camera: every move has a story reason. No floating orbits.
- Source-motivated light: light originates from windows, practicals, sky — not generic "cinematic."
- Physical weight: gravity, inertia, effort in every movement.
- Natural imperfections: asymmetry, skin texture, human irregularity — no AI plastic.
- Performance space: room for actors to breathe, react, exist — not just hit marks.

## Image2 Board Design Standard

Every Image2 prompt must ask for a visual control chart Seedance can read from the image:

- Clean production-board layout, not a decorative poster.
- Large, legible printed labels. Bilingual short labels where helpful: `S01 / 0-2s / CLOSE-UP / 近景`.
- Clear panel numbers and arrows for order. Color-coded zones.
- One consistent visual style across all boards in the same project.
- Fixed matte digital board substrate and palette must be written directly into every Image2 prompt. Do not drift into parchment, kraft paper, newspaper, oil paper, scrapbook, random white/dark boards, mixed fonts, or decorative collage textures.
- Visuals carry identity, action, staging, camera, and continuity — do not rely on long in-image text.
- For realist live-action, historical, war, documentary, police, period, or serious drama projects: lock photographic cinema realism. Do not allow game concept art, UE/CG look, glossy illustration, heroic poster faces, plastic skin, or stylized digital-painting texture unless the user explicitly asks for it.
- Use Simplified Chinese for Chinese project boards by default. Do not use Traditional Chinese unless the project region, era document, or user request specifically requires it.
- If the user provides a style reference image/video/film title, extract a compact global look lock first and apply its descriptive content to every asset board, storyboard board, and Seedance prompt. Only create/upload a safe abstract style image if it contains no people, scene geography, vehicles, props, maps, or readable text. The skill's default taste never overrides the user's requested style.

## Image2 Prompt Writing Rules

Write Image2 prompts as paired CN and EN versions by default. Use the Chinese version for user understanding and Chinese production review; use the English version to improve in-image label stability and downstream reference clarity.

For CN boards, use only short Simplified Chinese labels plus asset codes. For EN boards, use only short English labels plus the same asset codes. Never ask Image2 to render long Chinese paragraphs inside an image. Never ask EN boards to render readable Chinese in-world text; use blurred period texture, a separate `TEXT_PROP_PLATE`, or post-production typography.

Each prompt must specify: canvas ratio, visual style, board title, panel count, region contents, label readability, continuity constraints, negative constraints.

Storyboard prompts additionally require: shot number, timecode, shot size, visual content, action, dialogue/line, camera method, camera parameters, edit note, asset references.

## Script Dialogue Verbatim Rule

When the user provides a script, first extract a `DIALOGUE_LOCK` internally:

- All `【画外音】`, `【旁白】`, `【对白】`, character dialogue, radio/telephone/PA lines, chants, crowd responses, dialect calls, and parenthetical performance notes.
- Preserve exact wording, punctuation, names, brackets, ellipses, dashes, dialect words, numbers, and quotation marks from the user's script.
- A prompt may add camera language, performance detail, sound design, and pauses around the line, but it must not alter the line itself.
- If a line is too long for one Seedance prompt, split the scene into more segments or split the line into exact contiguous fragments. Record the split as `台词承接/Dialogue continuation`; never paraphrase.
- Storyboard prompts must mention the exact line or exact fragment assigned to the segment. Seedance prompts must include the exact line or exact fragment as spoken audio/performance timing.
- If the prompt budget is tight, compress visual description first. Dialogue is higher priority than optional camera adjectives, mood prose, extra negative clauses, or reference explanation.
- Before delivery, compare every script line against the final prompt file and verify no spoken line has been dropped or rewritten.

## Seedance Compatibility Rules

Design boards and Seedance text prompts as dual-control pairs — the board is readable as an image; the matching prompt executes the same storyboard even if Seedance misses part of the visual intent.

- **Asset boards** visually encode: stable references, drift prohibitions, exact identity, source-of-truth when based on user assets.
- **Storyboard boards** visually encode: who appears, where, what changes over time, camera movement, shot size, dialogue intention, start/end state, next-shot handoff.
- **Seedance prompts** textually encode: same shot order/timecodes as storyboard, same character/scene/prop/VFX/dialogue/sound/emotion, same camera logic, explicit continuity and forbidden drift.
- **Dense prompt structure**: every Seedance prompt names exact `@` reference duties, embeds the global look content directly, segment setup, start state, per-shot timeline, performance, camera/lens, light/color, sound/VFX, end state, continuity handoff, and multi-dimensional negative constraints under the 2000-character limit.
- **Style lock boundary**: Seedance should be controlled primarily by the repeated global look text embedded in every segment. Upload an abstract safe style image only when it is free of people, scene geography, vehicles, props, maps, and readable text. Never upload a mixed visual bible globally as a style reference.
- **Style reference boundary**: style references control palette, contrast, lighting, lens language, grain/texture, composition, camera mood, and pacing tendencies. They must not override character identity, scene geography, props, story facts, clean-frame rules, or crowd diversity.
- **Clean-frame boundary**: storyboard labels, S01/S02 markers, dialogue notes, and production annotations exist only on the control board. They must not appear in the generated video frame. Seedance prompts for narrative footage must explicitly say: no subtitles, no captions, no shot labels, no UI text, no random Chinese/English text, no watermarks, clean cinematic image only.
- **Crowd identity boundary**: named recurring characters stay locked; background soldiers, civilians, workers, crowds, and extras must not inherit the same face. Group scenes need varied ages, face shapes, heights, body builds, skin texture, hairlines, fatigue, posture, and micro-reactions while keeping wardrobe/era/unit continuity.

Avoid: tiny text labels, abstract mood boards, random decorative UI, 25+ panel boards for single Seedance clips, incompatible costume/face options, asking Image2 to generate exact long paragraphs in-image.

## Production Execution Rules

When the user asks for industrialized output, team handoff, stable series production, or repeatable SOP, load `references/production-sop/production-runbook.md` and include compact execution controls in the final prompt file:

- production unit naming: project / episode / scene / segment / shot / take.
- reference upload order and each reference image's duty.
- generation log template when Seedance takes will be reviewed.
- acceptance gate using `references/production-sop/output-acceptance-scorecard.md`.
- smallest repair decision using `references/production-sop/seedance-repair-sop.md`.

These controls must be absorbed into the prompts or kept in an internal working draft. Do not add user-facing instruction chapters unless the user explicitly asks for SOP documentation.

When generating a local Markdown prompt file, run:

```bash
python3 scripts/prompt_lint.py image2_seedance_control_prompts.md
```

If lint reports hard failures, revise before delivery. If lint reports only warnings, use judgment and mention only material unresolved assumptions.

## Final Response Rule

After creating the file, reply briefly:

```text
已做好：[filename](absolute/path)
```

Mention any unresolved assumption only if it materially affects production.
