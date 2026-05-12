# Prompt Library Index

> Last updated: 2026-05-12 | Version: 1.2.0

This skill uses a modular prompt library. Do not overwrite the core workflow when the user provides a strong reference prompt. Add it to the proper branch and update this index.

## Loading Decision Table

Before writing prompts, use this table to load only the files needed for the current project.

### Asset Prompts — Character Type

| 项目条件 | 加载文件 |
|---|---|
| 真人角色 / AI 真人剧 / 生物 / 怪兽 | `character-design-sheet.md` |
| UE5 / MetaHuman / 游戏影视级角色 | `+ ue5-metahuman-technical-sheet.md` |
| 用户上传照片 / 文字描述角色 | `+ cinematic-character-card-generator.md` |
| 需要主参考表 (4:3 Seedance 身份锁) | `+ master-character-reference-sheet.md` |
| 简洁 3D / 机器人 / 吉祥物 / Q 版角色 | `simple-seedance-character-reference-sheet.md` |
| 儿童 / 青少年 / 地区文化角色 | `+ cultural-child-character-card.md` |
| 双人 / 情侣角色 | `+ couple-character-reference-sheet.md` |
| 动画电影级角色提案板 | `+ animated-cinematic-character-pitch-board.md` |

### Asset Prompts — Scene / Prop / Continuity

| 项目条件 | 加载文件 |
|---|---|
| 重复出现或有固定布局的场景 | `scene-asset-board.md` |
| 特写/重复/推动剧情/品牌展示的道具 | `prop-asset-board.md` |
| 场景复杂、多角色互动、情绪在空间中变化 | `+ scene-continuity-board.md` |

### Storyboard Prompts — Segment Function

| 段落功能 | 加载文件 |
|---|---|
| **默认基线** (任何 Seedance 段落) | `storyboard-control-board.md` |
| 对白 / 情感戏 / 短剧节拍 (行式表格) | `traditional-storyboard-table-board.md` |
| 产品 / 流程 / 生活方式 / 社交媒体广告 (8 帧信息图) | `infographic-8-shot-poster.md` |
| 一键速出 (单句想法 → 完整分镜) | `smart-shot-directing-sheet.md` |
| 快速分镜 (单行想法 → 6-9 板) | `one-line-smartshot-storyboard.md` |
| 紧凑预产计划 (单句 → 机位+分镜) | `cinematic-production-plan-sheet.md` |
| 25-40 秒影视 / 情感 / 动作 (两段生成) | `two-part-cinematic-production-board.md` |
| 15 秒商业广告 (食品/旅游/亲子/动漫) | `integrated-15s-commercial-production-board.md` |
| 高端广告 / 汽车 / 时尚 / 红毯 (5 帧资产锁定板) | `asset-locked-lookbook-camera-storyboard.md` |
| 奢侈品 / 时尚 / 香水 / 汽车 / 酒店 (8 场景创意方向) | `luxury-ad-creative-direction-board.md` |
| 竖屏 9:16 香水/护肤/美妆 (12 帧氛围板) | `vertical-fragrance-mood-ad.md` |
| 动作 / 追车 / 打斗 / VFX (PREVIS 时间线) | `previs-action-vfx-music-timeline.md` |
| 舞蹈 / 武术 / 走秀 / 编排 (16 帧身体节点) | `sixteen-panel-dance-choreography-board.md` |
| 体育高光 / 足球 / 篮球 / 赛车 | `sports-highlight-sequence-board.md` |

### Seedance Prompts — Dual-Control Pair

| 对应故事板 / 场景类型 | 加载文件 |
|---|---|
| 情侣/双人介绍 | `romantic-couple-introduction.md` |
| 产品广告 (12-20 秒) | `product-ad-timeline.md` |
| 影视制作计划板执行 | `cinematic-production-sheet-timeline.md` |
| 角色+故事板首通 → 续生成 (15-30 秒延续) | `character-storyboard-first-pass-continuation.md` |
| 多参考动作场景 (明确标签职责) | `named-reference-stack-action-prompt.md` |

### Production SOP — 工业化控制

| 生产条件 | 加载文件 |
|---|---|
| 多段 / 多场景 / 分集 / 长片 | `project-continuity-bible.md` |
| 多镜头 / 多 Seedance 段落 | `shot-seam-review.md` |
| Seedance 输出有漂移/动作/连续性问题 | `seedance-repair-sop.md` |
| **设计任何故事板之前** | **`storyboard-seedance-pairing-principle.md`** |
| **任何提示词文件交付前** | `prompt-self-review-checklist.md` |

---

## Branches

### Asset Prompt Branch

Path: `references/asset-prompts/`

Use for Image2 prompts that design stable visual assets: character asset boards, scene asset boards, prop asset boards, wardrobe/material boards, style/look bibles, monster/creature sheets, live-action actor continuity sheets.

Current files:

- `character-design-sheet.md`: director-level character design sheet pattern for humans, creatures, monsters, and recurring roles.
- `ue5-metahuman-technical-sheet.md`: technical UE5/MetaHuman-style character reference sheet for strict multi-view continuity, asymmetry, body landmarks, hands/feet, hair/groom, costume/armor/prop detail.
- `cinematic-character-card-generator.md`: film-production character card generator pattern for text/photo inputs, identity preservation, height scale, wardrobe/material breakdown, and AI真人剧 character continuity.
- `master-character-reference-sheet.md`: clean 4:3 single-character master reference sheet for Seedance identity control, with dominant scale sheet, exact expression progression, micro-expressions, head angles, posture, close-up, wardrobe callouts, optional prop, and hand gestures.
- `simple-seedance-character-reference-sheet.md`: lightweight clean Seedance character reference sheet for stylized 3D characters, robots, mascots, simple creatures, and fast identity locking.
- `cultural-child-character-card.md`: culturally grounded child/teen character card pattern for regional authenticity, child proportions, height scale, local wardrobe logic, and actor-like micro-performance.
- `couple-character-reference-sheet.md`: couple/dual-character reference sheet for romantic or relationship-driven scenes.
- `scene-asset-board.md`: scene asset board pattern for recurring locations — multiple angles, entrance/exit, camera-safe zones, light direction, key objects, color palette, forbidden layout/weather drift.
- `prop-asset-board.md`: prop asset board pattern for repeating/close-up/plot-driving props — multi-view, material/scale/color, hand relationship, story context, forbidden shape/color/scale drift.
- `scene-continuity-board.md`: scene continuity board pattern bridging scene asset and storyboard — character positions, movement paths, light/atmosphere, emotional state flow, edit in/out frames.
- `animated-cinematic-character-pitch-board.md`: high-budget animated cinematic character pitch-board pattern for GPT Image 2, emphasizing art-directed asymmetric composition, human vs stylized creature layout choices, character psychology, actor-like performance direction, signature quote, action/idle poses, wardrobe/material accuracy, strict turnaround, head studies, cinematic portrait, always-present props, color/texture guide, and production-ready fidelity notes for film, Seedance, merchandising, and pitch decks.

### Storyboard Prompt Branch

Path: `references/storyboard-prompts/`

Use for Image2 prompts that design Seedance-readable shot boards: timing boards, scene segment storyboards, action choreography boards, dialogue scene boards, product ad boards, MV rhythm boards, episode scene boards.

Current files:

- `storyboard-control-board.md`: baseline Seedance 2.0 storyboard control board pattern.
- `traditional-storyboard-table-board.md`: traditional storyboard table pattern for Seedance-readable 5-8 shot boards with shot number, timing, shot size, frame thumbnail, camera movement, action, dialogue, sound/music, and continuity notes.
- `infographic-8-shot-poster.md`: clean 8-panel infographic storyboard poster for 12-15 second product/process/lifestyle/social ad sequences.
- `smart-shot-directing-sheet.md`: complete cinematic directing sheet method that turns one idea into character references, environment design, floor plan/blocking, side elevation, storyboard, camera plan, lighting notes, mood/style, and cinematography notes before Seedance rendering.
- `one-line-smartshot-storyboard.md`: fast Smartshot-style pattern for expanding one short idea into a detailed 6-9 panel storyboard image with character locks, environment lock, camera style, color/VFX notes, ready video prompt summary, and continuation-friendly final frame.
- `cinematic-production-plan-sheet.md`: compact GPT Image 2 cinematic pre-production plan sheet pattern for turning one simple idea into a Seedance-readable board containing character references, environment, top-down floor plan, movement paths, numbered camera positions, 4-6 shot storyboard, color palette, lighting, mood, and style notes.
- `two-part-cinematic-production-board.md`: 25-40 second cinematic/story/emotional short pattern using one or two boards split into Storyboard 1 and Storyboard 2, generated separately in Seedance then edited together.
- `integrated-15s-commercial-production-board.md`: one-page 15-second commercial production board pattern for food, drink, tourism-specialty, mascot, kids/family, anime, and stylized brand ads, combining light asset locks, product/prop design, set design, camera map, palette, sound notes, negative notes, and a 5-shot timeline table.
- `asset-locked-lookbook-camera-storyboard.md`: asset-locked production board for user-provided characters, products, vehicles, props, or scenes, combining asset reference modules, location/camera floor plan, and a 5-frame Seedance storyboard.
- `luxury-ad-creative-direction-board.md`: 15-20 second high-end commercial creative direction board for fragrance, car, travel/hotel, skincare, fashion, and premium product ads with styling, set design, route guide, 8-scene storyboard, lighting, audio, cinematography, and Seedance prompt.
- `vertical-fragrance-mood-ad.md`: 9:16 vertical 12-shot mood storyboard pattern for fragrance, skincare, beauty, quiet UGC-style premium ads, and 15-second atmosphere films.
- `previs-action-vfx-music-timeline.md`: director-style PREVIS action storyboard pattern for kinetic action, dance, ink/paint/energy VFX, strict color logic, music/SFX timing, and 2-second beat Seedance timelines.
- `sixteen-panel-dance-choreography-board.md`: 4x4 sixteen-panel choreography/storyboard pattern for dance, cultural performance, martial forms, fabric/water/reflection motion, and ordered body-action nodes.
- `sports-highlight-sequence-board.md`: sports highlight storyboard pattern for tackle-to-goal, fast break, race overtake, or other action chains requiring ball/object continuity, broadcast camera logic, and realistic sports physics.

### Seedance Prompt Branch

Path: `references/seedance-prompts/`

Use for Seedance 2.0 video prompts that turn existing Image2 assets/storyboards into motion: relationship introductions, product ad timelines, dialogue scenes, action/martial arts, VFX/dance prompts, scene continuation prompts, reference-image binding language.

Current files:

- `romantic-couple-introduction.md`: Seedance relationship-introduction prompt using a couple character sheet, detail -> identity -> relationship -> presence -> full reveal.
- `product-ad-timeline.md`: concise product ad timeline prompt structure for 12-20 second commercials using product boards/storyboards.
- `cinematic-production-sheet-timeline.md`: Seedance prompt pattern that treats an uploaded Image2 cinematic production plan sheet as a strict directing document, preserving character identity, scene geography, CAM positions, shot order, color, lighting, VFX, and continuity for a 4-15 second segment.
- `character-storyboard-first-pass-continuation.md`: Seedance prompt pattern for using a character/location sheet plus 3x3 storyboard as first-pass references, then using the previous 15-second video's last frame as the main reference for seamless 15-30 second continuation while keeping original sheets as secondary continuity anchors.
- `named-reference-stack-action-prompt.md`: Seedance prompt pattern for multi-reference action scenes using explicit labels such as `@[CurrentStoryboardRef]`, `@[HeroRef]`, `@[VillainRef]`, and `@[LocationRef]` so each uploaded image has one clear responsibility: shot flow, identity lock, antagonist lock, or environment lock.

### Production SOP Branch

Path: `references/production-sop/`

Use for industrialized long-form or multi-segment production control: project continuity bibles, shot seam checking, Seedance repair and regeneration, version/state tracking, post-generation quality control, prompt self-review.

Current files:

- `project-continuity-bible.md`: project-level continuity bible for locking characters, scenes, props, timeline, style, sound, VFX, emotion, and forbidden drift across clips, scenes, episodes, or long-form production.
- `shot-seam-review.md`: shot-to-shot and segment-to-segment continuity review SOP using IN state, action, OUT state, next handoff, direction, emotion, light, sound, and edit checks.
- `seedance-repair-sop.md`: post-generation defect diagnosis and repair workflow for identity drift, scene drift, prop drift, motion failure, camera failure, emotion failure, style failure, and seam failure.
- `storyboard-seedance-pairing-principle.md`: master design philosophy for the complementary dual-control pair — storyboard visualizes what words can't express (movement paths, camera positions, light, emotion keywords, sound/VFX markers), Seedance prompt writes what images can't show (micro-expressions, camera texture, light quality, sound design, performance timing) using the full 2000-character limit. Film-level quality standard.
- `prompt-self-review-checklist.md`: mandatory 10-point delivery checklist: responsibility separation, identity isolation, storyboard purity, UI/text control, constraint balance, logical consistency, timecode check, shot rhythm, storyboard/seedance mirror, and production readability.

## Selection Rule

1. Use the **Loading Decision Table** above to match project conditions to files.
2. Identify the project type and required assets.
3. Identify storyboard type by scene function.
4. For multi-segment/multi-scene/episode-based production, identify required SOP files.
5. Load only the matched reference file(s).
6. Adapt the pattern to the user's project. Do not copy reference prompts blindly.

## Update Rule

When the user provides a high-quality prompt reference:

1. Decide whether it belongs to asset, storyboard, seedance, or SOP.
2. Save it as a new reference file or merge its reusable technique into an existing file.
3. Preserve the core idea and applicability conditions.
4. Add it to this index and update the Loading Decision Table.
5. Do not replace unrelated existing branches.
