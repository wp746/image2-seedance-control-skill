---
name: image2-seedance-control
description: Transform vague AI video ideas, scripts, AI live-action drama episodes, webtoon episodes, creative shorts, product ads, MV concepts, reference images, or reference videos into a single deliverable file containing GPT Image 2 prompts for Seedance 2.0 control boards. Use when the user wants to produce AI video by first generating Image2 visual control charts/assets/storyboards/continuity bibles, then uploading those images to Seedance 2.0. Also use for industrialized AIGC video production requiring project continuity bibles, asset locking, shot seam review, multi-segment consistency, or Seedance repair SOP. Trigger on requests such as “做成 image2 提示词”, “拿图去 Seedance 出视频”, “设计 Seedance 能看懂的图”, “真人剧/漫剧按集生产”, “模糊想法转分镜图”, “工业化生产”, “镜头接缝审核”, “Seedance 返修”, or “只给我 image2 的提示词文件”.
---

# Image2 Seedance Control

## Goal

Create one final file only: an Image2 prompt file that the user can use to generate visual control board images, then upload those images to Seedance 2.0 for video generation.

The skill must behave like a director + production designer + storyboard supervisor, but the final deliverable is not an explanation. The final deliverable is one file containing Image2 prompts.

## Modular Prompt Library

This skill has a growing prompt reference library. Before writing a final prompt file, inspect the library index when the task involves asset design or storyboard design:

```text
references/prompt-library-index.md
```

Load only the relevant branch files:

- Asset prompts: `references/asset-prompts/`
- Storyboard prompts: `references/storyboard-prompts/`
- Seedance prompts: `references/seedance-prompts/`
- Production SOP: `references/production-sop/`

When the user provides a high-quality reference prompt, do not replace the core workflow. Save or merge its reusable technique into the proper branch and update the index. Treat the library as a growing arsenal of patterns selected by project needs.

## Output Contract

After requirements are clear, create exactly one Markdown file in the current workspace unless the user specifies another path.

Default filename:

```text
image2_seedance_control_prompts.md
```

The file may contain multiple Image2 prompts depending on project length, but it is still one file.

The prompts must be separated into two groups:

1. Asset design prompts: generate character, scene, and prop assets as separate reference images.
2. Storyboard prompts: generate shot/timing boards for Seedance 2.0, using the asset images as external references.
3. Seedance 2.0 text prompts: after every storyboard prompt, include one matching Seedance 2.0 prompt that translates the storyboard into explicit shot-by-shot motion, camera, dialogue, sound, emotion, continuity, and negative instructions.

Do not force asset design and storyboard planning into one single image. Asset details consume visual space and reduce storyboard readability.

Do not rely on vague Seedance wording such as "please follow the storyboard". The storyboard image and the Seedance text prompt are a dual-control pair. The board controls visual reference; the text prompt controls execution.

Before finalizing the file, perform a prompt self-review pass and revise any prompt that could cause logical drift, role confusion, UI text errors, duplicated responsibilities, or ambiguous model guessing.

For multi-segment video generation, every storyboard and its matching Seedance 2.0 prompt must use local segment timecode. Each segment starts at `0:00` and ends at or before `0:15`. Do not write cumulative episode timecodes such as `0:59-1:14` or `1:14-1:30` inside a Seedance generation prompt. Track total runtime only in the editing/continuity notes.

Final assistant response should only link to the created file and briefly say it is ready. Do not paste the full prompt in chat unless the user asks.

## Input Routing

Classify the user input before producing prompts:

- `IDEA_ONLY`: a vague idea, e.g. “金刚大战哥斯拉”.
- `SHORT_SCRIPT`: a short script, outline, ad concept, MV concept, or creative short.
- `LIVE_ACTION_DRAMA_EPISODE`: AI 真人剧, 仿真人剧, 1-3 minute episode, or longer dramatic script.
- `WEBTOON_EPISODE`: 漫剧 / 短剧单集.
- `ASSETS_OR_REFERENCE_READY`: the user provides character images, scene images, prop images, screenshots, or a reference video.

## Existing Asset Handling

When the user provides existing assets such as character images, scene images, prop images, style frames, screenshots, hand-drawn sketches, or partial boards, treat those assets as the primary source of truth.

Do not skip asset design just because the user already has assets. First convert the provided assets into a formal asset design prompt package, then generate storyboard prompts that strictly bind to those assets.

Workflow for `ASSETS_OR_REFERENCE_READY`:

1. Identify and label every user-provided asset:
   - characters: `CHAR_A`, `CHAR_B`, etc.
   - scenes: `SCENE_01`, `SCENE_02`, etc.
   - props: `PROP_PHONE`, `PROP_SWORD`, etc.
   - style references: `STYLE_REF_01`, etc.
2. Extract the visible invariants from each asset:
   - face identity, age impression, body proportion, hair, wardrobe, accessories, posture, expression baseline
   - location geography, architecture, light direction, color palette, weather, set dressing, background depth
   - prop shape, size, material, color, wear marks, usage logic, hand relationship
3. Create formal asset design prompts that preserve and clarify the user assets:
   - character continuity sheet / role bible
   - scene continuity board
   - prop continuity board
   - optional style/look bible
4. Only after those asset prompts are defined, create storyboard prompts.
5. Every storyboard prompt must reference the asset codes and state that the storyboard must obey the uploaded assets exactly.

If the provided asset is incomplete, extend it conservatively. Fill only what is necessary for video production and do not change the user's visible design unless the user asks for a redesign.

Use strong binding language:

```text
以用户上传的资产图为最高优先级参考。故事板中的人物、场景、道具必须严格继承资产图的身份、比例、造型、服装、材质、颜色、位置逻辑和视觉气质。不得重新设计，不得随机替换，不得脸漂移、服装漂移、场景漂移或道具漂移。
```

## Requirement Clarification

For `IDEA_ONLY`, do not create prompts immediately. First ask concise questions and offer recommendations.

Collect only production-critical information:

- duration: 15s, 30s, 1min, 2-3min, or episode-based.
- aspect ratio: 16:9, 9:16, 1:1.
- style: suggest 2-3 suitable options if unclear.
- content type: live-action realism, fake documentary, monster film, short drama, MV, product ad, game trailer, anime, webtoon, etc.
- main characters and conflict.
- target platform or usage.
- existing assets or references.

If the user is unsure, recommend a direction instead of asking endless questions.

Example guidance:

```text
这个想法我建议做成 9:16 竖屏 30 秒灾难片钩子：前 3 秒直接城市警报和巨兽入画，中段对抗，最后留悬念。你确认一下：要竖屏还是横屏？偏好好莱坞怪兽片、伪手机目击，还是游戏 CG？
```

For `SHORT_SCRIPT`, `LIVE_ACTION_DRAMA_EPISODE`, or `WEBTOON_EPISODE`, first give a short director recommendation before writing files:

- what to keep
- what to simplify
- where the hook is
- where to split into Seedance-friendly segments

Then create the Image2 prompt file.

## Prompt Group Planning Rules

Always split Image2 prompts into asset prompts and storyboard prompts.

### Asset Prompt Group

Use this group to create stable references the user will upload to Seedance 2.0 together with the storyboard.

If the user already provides assets, use the asset prompt group to create a formalized asset design package from those assets. The goal is not to invent new designs, but to normalize the user's assets into Seedance-readable continuity boards.

Create only the assets required by the story:

- character asset prompt
- scene asset prompt
- prop asset prompt
- optional style/look bible prompt

Each asset prompt should generate a clear, spacious asset board. Do not cram it into storyboard images.

For user-provided assets, each asset prompt must include:

- uploaded asset as primary reference.
- asset code.
- what must be preserved.
- what may be clarified or completed.
- what must never change.
- how this asset will be referenced in storyboards.

### Storyboard Prompt Group

Use this group to create Seedance-readable shot boards.

Storyboard boards should focus on:

- duration
- shot number
- timing
- visual sketch of the frame
- shot size
- screen content
- action
- dialogue or subtitle intention
- camera technique
- camera parameters
- transition / edit-out frame
- continuity notes that matter for this segment

The storyboard may reference assets by labels, e.g. `CHAR_A`, `SCENE_01`, `PROP_PHONE`, but should not spend large space re-displaying full character sheets or prop boards.

When user-provided assets exist, every storyboard prompt must explicitly lock to those asset labels and visible invariants. Do not redesign the character, scene, or prop in the storyboard prompt. The storyboard controls only shot order, timing, staging, action, camera, dialogue, sound, edit point, and continuity.

The user will upload both the asset image(s) and storyboard image(s) to Seedance 2.0 as all-purpose references.

Every storyboard prompt must be immediately followed by a corresponding Seedance 2.0 prompt. This Seedance prompt must not be generic. It must restate the storyboard content in executable language:

- reference stack and each reference image's job.
- exact local segment duration and aspect ratio.
- start state and end state.
- shot-by-shot local timeline with timecode starting from `0:00`.
- who appears in each shot.
- scene geography and spatial direction.
- camera movement, shot size, lens feel, and pacing.
- physical action, facial performance, dialogue, sound, and emotional beat.
- VFX state changes and object/prop continuity.
- shot handoff from previous segment and to next segment.
- forbidden drift and common failure prevention.

For multi-segment work, the Seedance prompt must also state the previous segment's final frame and the next segment's required starting frame when relevant.

The previous/next segment relationship should be described as start/end state, not as cumulative timecode.

## Industrial Production Control

For multi-segment, multi-scene, 1-3 minute, episode-based, or long-form projects, add production control before writing asset/storyboard prompts.

Load only the needed SOP files:

```text
references/production-sop/project-continuity-bible.md
references/production-sop/shot-seam-review.md
references/production-sop/seedance-repair-sop.md
```

Use `project-continuity-bible.md` before asset prompts when the project needs recurring character, scene, prop, style, sound, VFX, emotion, timeline, or episode continuity.

Use `shot-seam-review.md` before finalizing storyboard prompts whenever there are multiple shots or multiple Seedance segments. Every shot must have an in-state, main action, out-state, and next-shot handoff.

Use `seedance-repair-sop.md` after the user shows a generated Seedance result with drift, weak motion, broken continuity, bad camera, or poor editability.

For long productions, manage the pipeline as:

```text
project bible -> asset boards -> scene geography -> storyboard segments -> seam review -> Seedance generation -> repair SOP -> final continuity review
```

## Board Planning Rules

Do not force everything into one or two images if it weakens performance.

Choose the number of Image2 boards by story need:

- 15s simple clip: usually 1-3 asset prompts + 1 shot-timeline storyboard prompt.
- 30-60s short: asset prompts for all recurring elements + 3-5 segment storyboard prompts.
- 1-3min short or drama: episode/scene asset prompts + several 4-15s storyboard prompts per scene.
- live-action drama/webtoon episode: manage assets by episode, produce storyboard prompts by scene.

Each Seedance generation segment should usually be 4-15 seconds. Use 15 seconds as the maximum, not the default.

Use fewer panels for emotional precision:

- 4 panels: one powerful emotional or action moment.
- 6 panels: short hook or micro-conflict.
- 8 panels: complete emotional turn.
- 12 panels: standard 10-15s sequence.
- 16-25 panels: only for overview/planning, not for one Seedance generation.

## Image2 Board Design Standard

Every Image2 prompt must ask for a visual control chart that Seedance 2.0 can read from the image.

Design principles:

- Use a clean production-board layout, not a decorative poster.
- Use large, legible printed labels. Avoid tiny paragraphs inside the image.
- Prefer bilingual short labels where helpful: `S01 / 0-2s / CLOSE-UP / 近景`.
- Use clear panel numbers and arrows to show order.
- Use color-coded zones: character, scene, prop, motion, continuity, forbidden changes.
- Use one consistent visual style across all boards in the same project.
- Ensure the board itself includes enough visual information that Seedance can follow it even if the user only writes “参考此图生成连续镜头”.
- Do not rely on long text inside the image. Let visuals carry identity, action, staging, camera, and continuity.

## Required Prompt Types

### Character Asset Board Prompt

Use for every recurring character.

For detailed character asset prompt patterns, load:

```text
references/asset-prompts/character-design-sheet.md
```

When the character requires strict technical multi-view continuity, UE5/MetaHuman/game-cinematic style, complex asymmetry, armor, hard-surface parts, body measurement panels, hands/feet reference, hair/groom reference, or exact left/right preservation, also load:

```text
references/asset-prompts/ue5-metahuman-technical-sheet.md
```

When the user provides a text character description, uploaded person photo, photo-plus-modification request, AI真人剧 role, or multi-character scene where height scale and identity preservation are important, also load:

```text
references/asset-prompts/cinematic-character-card-generator.md
```

When the project needs one clean single-character master reference sheet in any style, especially for Seedance-readable identity locking from a text description or uploaded reference image, also load:

```text
references/asset-prompts/master-character-reference-sheet.md
```

When the character is a simple stylized 3D role, robot, mascot, or creature and Seedance mainly needs a clean identity reference, also load:

```text
references/asset-prompts/simple-seedance-character-reference-sheet.md
```

When the character is a child/teen or culturally specific regional role where face structure, local wardrobe, height scale, child proportions, and actor-like micro-performance matter, also load:

```text
references/asset-prompts/cultural-child-character-card.md
```

The character board should feel like a film-production character design sheet for directors, casting, costume, performance, and AI video continuity. It should not look like a generic uniform model sheet.

Must include:

- character code, e.g. `CHAR_A`.
- character identity: name/code, alias or role, age range, height, body type, ethnicity/design language when relevant.
- asymmetric art-directed layout: no generic equal grid, no bland symmetry, no poster layout.
- turnarounds: full body front, 3/4 front, pure side, back, dynamic angle, all consistent.
- face design: structure, skin texture, eyes, hair, scars, distinctive features.
- head study: neutral, 3/4, side, looking down, looking up, dynamic emotional angle.
- expression range: baseline, anger, fear, pain, restraint, micro-expression.
- psychological profile: core trait, internal conflict, behavioral pattern, emotional baseline.
- performance direction: actor-like realism, micro-expressions, body language, idle behavior, gesture habits.
- costume and texture lock: main outfit, shoes, accessories, hero prop, fabric/material precision, weathering and stains.
- cinematic portrait: one environment-lit hero portrait with camera/lens/lighting notes.
- wardrobe/prop breakdown: isolated clothing pieces and key personal items with labels.
- body proportion and posture.
- color palette.
- forbidden drift: face change, costume change, age change, hairstyle change, extra limbs.

For human/live-action drama characters, prioritize actor continuity:

- realistic skin pores, uneven skin tone, eye fatigue, natural hairline, no AI doll face.
- consistent face from every angle.
- clear “performance baseline” so Seedance can preserve emotion across shots.

For creatures or monsters, adapt the same logic:

- anatomy identity, head shape, silhouette, scale, skin/fur/scale material, wounds, movement posture.
- emotional/behavioral baseline: predatory, protective, wounded, intelligent, berserk, etc.
- cinematic portrait and dynamic angle remain mandatory.

### Scene Asset Board Prompt

Use for every recurring or important location.

Must include:

- scene code, e.g. `SCENE_01`.
- multiple angles of the same space.
- entrance, exit, camera-safe zones.
- light direction and atmosphere.
- key furniture/objects and their fixed positions.
- color palette.
- forbidden drift: layout flip, object pop-in, time/weather change unless scripted.

### Prop Asset Board Prompt

Use only for props that repeat, enter close-up, drive plot, carry brand information, or require hand interaction.

Must include:

- prop code, e.g. `PROP_PHONE`.
- front/side/detail view.
- material, scale, color.
- how the hand holds or uses it.
- where it appears in the story.
- forbidden drift: shape change, color change, unreadable text, random extra parts.

### Scene Continuity Board

Use only when one scene is complex enough that scene layout and emotional continuity need a separate board beyond the scene asset.

Must include:

- same location from several useful angles.
- character positions and movement path.
- light source and atmosphere.
- key props and where they sit.
- emotional state entering and leaving the scene.
- edit-in and edit-out frames.

### Storyboard Shot Timeline Prompt

Use for each Seedance generation segment.

For detailed storyboard control-board patterns, load:

```text
references/storyboard-prompts/storyboard-control-board.md
```

For traditional storyboard table boards, dialogue/emotional scenes, short drama beats, romance scenes, or any 8-15 second segment where Seedance should execute directly from a row-based sheet with shot number, timing, shot size, frame, camera movement, action, dialogue, sound/music, and continuity notes, also load:

```text
references/storyboard-prompts/traditional-storyboard-table-board.md
```

For clean 12-15 second product/process/lifestyle/social ad sequences that benefit from an 8-shot infographic poster style, also load:

```text
references/storyboard-prompts/infographic-8-shot-poster.md
```

For 25-40 second cinematic, emotional, sci-fi/fantasy, action, or complex short sequences that should be planned as one story but generated as two Seedance halves, also load:

```text
references/storyboard-prompts/two-part-cinematic-production-board.md
```

For dance, cultural performance, martial forms, runway/fashion motion, water/fabric/sleeve choreography, or any sequence requiring 16 ordered body-action nodes, also load:

```text
references/storyboard-prompts/sixteen-panel-dance-choreography-board.md
```

For one-sentence ideas that need a complete cinematic shot plan with character references, environment design, floor plan/blocking, side elevation, storyboard panels, camera plan, lighting notes, mood/style, and cinematography notes before Seedance rendering, also load:

```text
references/storyboard-prompts/smart-shot-directing-sheet.md
```

For kinetic action, dance with VFX, ink/paint/energy trails, music-driven motion, strict color logic, or 12-15 second high-impact clips where body, prop, camera, VFX, and sound must synchronize, also load:

```text
references/storyboard-prompts/previs-action-vfx-music-timeline.md
```

For 15-20 second luxury commercials, fashion campaigns, fragrance, car, travel/hotel, skincare, beauty, or premium product ads requiring one creative direction board with styling reference, set design, route/camera guide, 8-scene storyboard, lighting, mood, audio, cinematography, and Seedance prompt, also load:

```text
references/storyboard-prompts/luxury-ad-creative-direction-board.md
```

When the user provides existing character, scene, prop, product, or vehicle assets and needs a storyboard that first shows locked asset references, then a location/camera floor plan, then a 5-frame Seedance execution storyboard, also load:

```text
references/storyboard-prompts/asset-locked-lookbook-camera-storyboard.md
```

For vertical 9:16 fragrance, skincare, beauty, quiet premium mood ads, 12-shot atmosphere storyboards, or 15-second UGC-style brand films, also load:

```text
references/storyboard-prompts/vertical-fragrance-mood-ad.md
```

For sports highlight sequences such as football tackle-to-goal, basketball fast break, racing overtake, or any play requiring ball/object continuity, realistic sports physics, field/court geography, and broadcast camera logic, also load:

```text
references/storyboard-prompts/sports-highlight-sequence-board.md
```

For romantic couple videos or relationship introductions using a couple reference sheet, load:

```text
references/asset-prompts/couple-character-reference-sheet.md
references/seedance-prompts/romantic-couple-introduction.md
```

For concise product ad Seedance wording after product/storyboard boards are ready, load:

```text
references/seedance-prompts/product-ad-timeline.md
```

Must include:

- total segment duration.
- panel-by-panel timing: e.g. `0-2s`, `2-4s`, `4-7s`, `7-10s`, `10-12s`.
- shot number: `S01`, `S02`, etc.
- shot size and angle.
- frame composition /画面内容.
- camera movement.
- camera parameters: lens feel, depth of field, shutter/motion blur if important, handheld/tripod/drone/crane.
- subject action.
- dialogue or subtitle intention if the scene includes speech.
- emotional beat.
- environment response.
- final frame for editing.
- asset references used: `CHAR_A`, `SCENE_01`, `PROP_PHONE`.

## Prompt File Structure

The one output file should use this structure:

```markdown
# Image2 Seedance Control Prompts

## Project Settings
- 片名:
- 类型:
- 画幅:
- 总时长:
- 风格:
- 生产策略:

## Usage
如果你已经有角色、场景、道具资产图，先把这些资产图与“资产设计提示词”一起放进 GPT Image 2，生成正规的角色/场景/道具连续性资产板。再复制“故事板提示词”去 GPT Image 2 出镜头时间轴图。进 Seedance 2.0 时，把用户原始资产图、正规资产板、故事板图一起作为全能参考上传，然后复制该故事板后面对应的“Seedance 2.0 视频提示词”。不要只输入“参考故事板生成”，必须使用逐镜头文字提示词形成双重控制。

## Production Control / 工业化连续性控制
- 项目圣经:
- 角色状态:
- 场景空间:
- 道具状态:
- 风格/光线:
- 声音/VFX:
- 情绪递进:
- 镜头接缝:
- 禁止漂移:

## Asset Design Prompts

### Prompt A01 - Character Asset Board - CHAR_A
```text
...
```

### Prompt A02 - Scene Asset Board - SCENE_01
```text
...
```

## Storyboard Prompts

### Prompt S01 - Scene 01 Segment 01 Storyboard
```text
本故事板为独立 Seedance 片段，时间码从 0:00 开始，最大不超过 0:15。
...
```

### Seedance Prompt S01 - Scene 01 Segment 01 Video
```text
参考图职责：
@[AssetRef] = 角色/场景/道具身份锁。
@[CurrentStoryboardRef] = 当前故事板，负责镜头顺序和画面构图。

生成 [时长，最长 15 秒] [画幅] 视频。本提示词使用本片段内部时间码，不使用整片累计时间。严格执行以下逐镜头时间线：
S01 / [timecode]：[画面、人物、动作、运镜、台词、声音、情绪]
S02 / [timecode]：[画面、人物、动作、运镜、台词、声音、情绪]
...

起始状态：[上一段结尾或本段开头状态]
结尾状态：[下一段必须接住的状态]
连续性：[角色、服装、场景、道具、空间方向、光线、VFX]
禁止：[换脸、换装、跳镜头、合并镜头、随机加人、乱码字幕、水印、UI 错乱]
```
```

Do not include long production essays in the file. Include only what helps the user generate asset boards and storyboard boards.

## Image2 Prompt Writing Rules

Write each Image2 prompt in Chinese by default, because the user works in Chinese.

Use English only for short visual labels that benefit model readability, such as:

- CLOSE-UP
- WIDE SHOT
- OVER-THE-SHOULDER
- TRACKING
- MATCH CUT
- DO NOT CHANGE FACE

Each prompt must specify:

- canvas ratio and layout.
- visual style.
- board title.
- grid/panel count.
- contents of each region.
- label size and readability requirements.
- continuity constraints.
- negative constraints.

For storyboard prompts, also specify these visible table columns or panel labels:

- shot number
- timecode
- shot size
- visual content
- action
- dialogue/line
- camera method
- camera parameters
- edit note
- asset references

## Seedance Compatibility Rules

Design boards and Seedance text prompts as dual-control pairs. The board must be readable as an image, and the matching Seedance prompt must be strong enough to execute the same storyboard even if Seedance misses part of the visual intent.

Asset boards must visually encode:

- who/what/where the stable references are
- what cannot drift
- exact character/scene/prop identity
- if based on user assets, which uploaded asset is the source of truth
- what is preserved from the user's asset and what is only production clarification

Storyboard boards must visually encode:

- who appears
- where they are
- what changes over time
- how the camera moves
- shot size and framing
- dialogue or line intention
- camera parameters
- start state, end state, and next-shot handoff

Seedance prompts must textually encode:

- the same shot order and timecodes as the storyboard.
- the same character, scene, prop, VFX, dialogue, sound, and emotion details.
- the same camera and movement logic.
- the exact start and end state for the segment.
- explicit continuity and forbidden drift rules.
- what emotion changes
- what the final frame should look like
- exact asset codes used in each shot
- asset-lock notes when the user provided original assets

Avoid:

- too many tiny text labels.
- abstract mood-board-only images.
- random decorative UI.
- overly dense 25-panel boards for a single Seedance clip.
- showing multiple incompatible costume or face options unless clearly marked as forbidden or alternate.
- asking Image2 to generate exact long paragraphs in-image.

## Prompt Self-Review Rules

Before delivering any prompt file, audit and fix it against these rules:

1. Responsibility separation:
   - Character boards lock identity, face, body, wardrobe, expressions, and status variants.
   - Scene boards lock space, light, material, geography, and usable camera areas.
   - Prop/UI boards lock object shape, usage, hand relationship, and short readable text.
   - Storyboard boards lock shot order, timing, staging, camera, action, dialogue intention, and handoff.
   Do not let one board accidentally perform another board's job unless the chosen reference pattern explicitly requires an integrated board.

2. No accidental identity sources:
   Scene boards should not show clear main-character faces unless the board is intentionally asset-locked. Use empty locations, distant passersby, silhouettes, or placeholders for scale.

3. UI and text control:
   If exact text matters, keep it short, large, and isolated. Do not ask Image2 to recreate complex app interfaces with many small labels. Prefer a separate UI/prop board for phone screens, signs, documents, chat messages, contracts, brand slogans, and curse rules.

4. Specific but not over-constrained:
   Lock non-negotiables: identity, wardrobe, scene geography, prop shape, UI text, story order, start/end state, and forbidden drift. Leave creative room for lighting texture, performance nuance, natural background detail, and cinematic composition.

5. Logical consistency:
   Check that every asset code used in storyboards exists. Check that every Seedance prompt references the same asset names as the storyboard. Check that character state changes happen in the right order and are not introduced early.

6. Segment timecode:
   For Seedance generation segments, verify every storyboard and matching Seedance prompt starts at `0:00` and ends at or before `0:15`. Do not use cumulative episode timestamps inside segment prompts. Put total runtime and edit order only in the production notes.

7. Production readability:
   Remove contradictory instructions, repeated labels, dense tiny paragraphs, and vague commands such as "make it cinematic" without execution detail. Each prompt should be clear enough that another agent can use it without asking what you meant.

## Final Response Rule

After creating the file, reply briefly:

```text
已做好：[filename](absolute/path)
```

Mention any unresolved assumption only if it materially affects production.
