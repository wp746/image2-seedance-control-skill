# Project Continuity Bible SOP

Use this SOP when a project is longer than one simple clip, has recurring characters/scenes, or must feel like one continuous film instead of separate AI shots.

This module creates the project-level continuity bible before asset prompts and storyboard prompts. It locks what must never drift across seconds, minutes, episodes, or long-form production.

## When To Use

- 30-60 second short with several scenes
- 1-3 minute AI真人剧 / 仿真人剧 / 创意短片
- episode-based live-action drama or webtoon production
- recurring characters, recurring locations, or plot-critical props
- user asks for industrialized production, stable series output, or long-form continuity

## Core Principle

Do not start shot prompts until the global rules are locked.

The continuity bible defines:

- who is in the story
- where the story happens
- how time moves
- how the camera behaves
- how the emotional arc changes
- what must stay identical
- what is allowed to change
- how every scene inherits previous state

## Required Bible Sections

### 1. Project Lock

Include project title, format, total duration, aspect ratio, visual style, genre, target platform, and production unit: clip, scene, or episode.

### 2. Global Visual Style Lock

Lock color palette, lens language, camera movement language, lighting style, contrast, exposure, texture, frame composition rules, and forbidden style drift.

If the user provides a style image, reference video, film title, director/cinematographer reference, brand look, or asks to extract a movie style, do not invent a default look. First load `user-style-reference-sop.md`, create a STYLE_BIBLE, then summarize only its compact production-ready style lock here.

Example:

```text
全片保持冷青灰阴雨写实调色，50mm/85mm浅景深人物镜头为主，手持轻微呼吸感，禁止突然变成高饱和广告片或二次元风格。
```

### 3. Character Continuity Matrix

For every recurring character, define:

- character code
- name / role
- age impression
- face identity anchors
- body scale and posture
- hair
- wardrobe state
- accessories
- voice / speaking rhythm
- emotional baseline
- gesture habits
- arc state by scene
- forbidden drift

Use status changes, not redesigns:

```text
CHAR_A 场景1：外套干净，情绪压抑。
CHAR_A 场景2：左袖湿透，眼神开始失控。
CHAR_A 场景3：脸上有雨水和轻微血痕，但脸型、发型、外套结构不变。
```

### 4. Scene Geography Bible

For every recurring scene, define scene code, floor plan, entrances/exits, fixed objects, camera-safe areas, light source direction, day/night/weather state, character starting positions, movement routes, and forbidden layout drift.

The scene must behave like a real place. Do not let doors, roads, furniture, vehicles, windows, or light direction randomly change.

### 5. Prop And Object Continuity

For every recurring prop, define prop code, shape/material/color, scale, who holds it, which hand, where it begins, where it ends, damage/state changes, close-up requirements, and forbidden drift.

### 6. Timeline And State Tracking

Track story state by scene or segment:

- time of day
- weather
- location
- character physical state
- character emotional state
- costume/prop state
- conflict state
- previous segment ending frame
- next segment starting need

This prevents long-form production from feeling reset every clip.

### 7. Emotional Arc And Conflict Map

For every scene or segment, define starting emotion, pressure source, conflict beat, reversal or discovery, ending emotion, and next-scene carryover.

Emotion should progress, not randomly jump.

### 8. Sound And Music Bible

Define recurring environmental sounds, character breath/footstep/cloth details, music motif, silence points, impact sounds, transitions, and dialogue tone.

Sound continuity helps shots feel joined even when image generation is segmented.

### 9. VFX And Motion Rules

If the project uses VFX, lock VFX type, color logic, origin point, movement behavior, body/prop/environment interaction, intensity progression, and forbidden VFX drift.

Do not let the same magical energy, explosion, smoke, blood, rain, lens flare, or interface style mutate between shots.

### 10. Global Forbidden Drift List

Always include:

- no face drift
- no age drift
- no costume redesign
- no scene layout flip
- no prop shape/color change
- no random style shift
- no camera direction contradiction
- no emotional reset between connected shots
- no sudden lighting/time/weather change unless scripted

## Image2 Project Bible Board Prompt

Use this when the final deliverable should include a visual project bible board:

```text
请创建一张项目级连续性圣经控制图，用于后续 GPT Image 2 资产板、故事板和 Seedance 2.0 视频生成统一参考。

项目：[PROJECT_TITLE]
类型：[FORMAT]
总时长：[DURATION]
画幅：[ASPECT_RATIO]
风格：[STYLE]

这是一张影视工业级 continuity bible / 连续性圣经，不是海报。画面必须清晰分区、标签大、文字短、结构像制片团队使用的总控板。

必须包含以下区域：
1. PROJECT LOCK / 项目锁定：片名、类型、时长、画幅、风格、生产单位。
2. GLOBAL STYLE / 全片风格：色彩、镜头语言、光线、质感、构图规则、禁止风格漂移。
3. CHARACTER MATRIX / 角色连续性矩阵：每个角色的编号、脸部锚点、身高体型、发型、服装、配饰、表演基准、情绪弧线、禁止漂移。
4. SCENE GEOGRAPHY / 场景空间圣经：主要场景的平面图、入口出口、固定物、光源方向、角色移动路线、禁止空间漂移。
5. PROP CONTINUITY / 道具连续性：重复道具的形状、材质、颜色、尺寸、持握方式、状态变化。
6. TIMELINE STATE / 时间线状态：每场戏的时间、天气、角色身体状态、服装状态、道具状态、冲突状态。
7. EMOTIONAL ARC / 情绪递进：每场戏的进入情绪、压力来源、冲突点、转折、离开情绪。
8. SOUND + VFX RULES / 声音与视觉特效规则：环境声、音乐动机、静默点、VFX颜色与运动逻辑。
9. DO NOT CHANGE / 禁止漂移：脸、年龄、服装、场景布局、道具、光线、风格、方向、情绪承接。

整体要求：像真正影视项目的总导演手册，所有信息服务于长片/分集稳定生产。视觉上要清楚、可读、可被 Seedance 作为总参考理解。
```

## Output Rule

For longer projects, include a concise `Production Control` section in the user's final Markdown file before asset prompts:

```markdown
## Production Control / 工业化连续性控制
- 项目圣经:
- 角色状态:
- 场景空间:
- 声音/VFX:
- 禁止漂移:
```

Keep it practical and short. The main deliverable is still the prompts.
