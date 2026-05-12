# Storyboard Control Board Pattern

Use this pattern when creating Image2 storyboard prompts for Seedance 2.0.

Before writing any storyboard, always apply the master pairing philosophy:
```text
references/production-sop/storyboard-seedance-pairing-principle.md
```

## Core Principle

```
故事板把文字表达不精准的东西画出来。
Seedance prompt 把图画不出来的东西写出来。
两者互补，不互扰。
```

The storyboard image is a **visual control chart** — its job is to visualize what words cannot precisely express. Text on the board is minimal: logic labels, annotations, behavioral rules.

The matching Seedance 2.0 text prompt fills in everything the image can't show: micro-expressions, camera texture, light quality, sound design, performance rhythm, material patina.

## Applicability

Use for every Seedance generation segment, usually 4-15 seconds.

Storyboard boards should not display full character sheets. They should reference asset codes such as `CHAR_A`, `SCENE_01`, and `PROP_PHONE`.

If the user provided original character, scene, or prop assets, those assets are the source of truth. The storyboard may only stage and animate them. It must not redesign faces, costumes, locations, props, materials, colors, or identity traits.

## Visual Storytelling Elements (Must Include)

These are the things the storyboard image must visualize — the things text cannot precisely convey:

### 1. 俯视动线图 / Top-Down Movement Floor Plan

A clear overhead diagram showing:

- Space outline: room, street, plaza, corridor — walls, doors, windows, obstacles
- Character starting positions: labeled with asset codes
- Movement paths: dotted or dashed directional arrows, with speed/timing marks if relevant
- Key blocking moments: marked positions where characters stop, turn, sit, interact
- Camera positions: numbered (CAM 1, CAM 2...) with direction arrows and lens labels
- Legend: simple icon key for character paths, camera positions, product/prop anchors

```text
风格参考：像导演和摄影指导在勘景时画的俯视调度图。清楚、实用，不是美术作品。
```

### 2. 机位设置 / Camera Setup Map

For each camera position on the floor plan:

- CAM number (CAM 1, CAM 2...)
- Shot size: LS / MS / CU / ECU / OTS / 2-SHOT
- Lens: focal length or character (85mm portrait, 35mm environmental, 24mm wide)
- Height: eye-level / low / high / overhead / chest / waist
- Movement: locked-off / handheld / dolly / crane / steadicam / slider
- Movement path if the camera moves: arrow with direction and speed note

```text
每个机位标注：CAM 编号、景别、镜头、高度、运动方式。如果机位运动，画出运动箭头。
```

### 3. 灯光氛围说明 / Lighting Atmosphere Guide

Visual indications of:

- Primary light source direction: arrows showing key light angle
- Light quality: hard shadow edge vs. soft wrap — can be indicated with edge style
- Color temperature: warm/cool/neutral with approximate Kelvin or gel note
- Practical sources in scene: lamps, windows, screens, candles — circled or highlighted
- Atmospheric elements: haze, dust, rain, smoke — simple visual indicators
- Light changes: dimmer cue, flicker note, practical switch moment

```text
灯光不是"电影感"三个字。光源方向、软硬、色温、氛围元素，都要画出来。
```

### 4. 情绪关键词 / Emotion Keywords

Large, visible labels showing:

- Emotional state per shot or per beat
- Emotional progression across the sequence
- Micro-expression triggers: "眼移向门", "嘴角收紧", "喉结滚动"
- Tension/release mapping: where pressure builds, where it breaks

```text
用大号中文关键词标注，不要用抽象词。不是"悲伤"，是"压抑→崩溃前0.5秒"。不是"紧张"，是"瞳孔定住、呼吸暂停"。给演员和Seedance一个可执行的表演锚点。
```

### 5. 声音/特效标注 / Sound & VFX Annotations

On the timeline or beside shots:

- Sound cue positions: where music enters, where it cuts, where silence falls
- Foley markers: footsteps, cloth rustle, object handling
- Ambience notes: room tone character, external environment
- VFX trigger frames and behavior: explosion origin, magic source, screen glitch, particle direction
- Sound bridges: which sound carries across the edit point

```text
声音不是后期的事。在故事板上就标注：这里音乐进、这里只剩呼吸声、这里有一声枪响后的耳鸣。Seedance需要这些。
```

### 6. 逻辑标签 / Logic Labels (Minimal Text)

Keep these short and bilingual:

- Shot number: `S01`, `S02`, `S03`
- Local timecode: `0-2s`, `2-5s`, `5-8s`
- Shot size: `CU / 特写`, `MS / 中景`, `WS / 广角`
- Edit type: `CUT`, `DISSOLVE`, `MATCH CUT`
- Asset codes: `CHAR_A`, `SCENE_01`, `PROP_PHONE`
- Continuity locks: `LOCK FACE`, `KEEP HAND`, `MAINTAIN EYELINE`

## Rhythm-Driven Shot Count

Shot count is **never a formula**. It is always driven by rhythm and emotion.

```
情绪需要空间 → 少切，长镜头，让观众呼吸
情绪需要冲击 → 快切，短镜头，制造压迫
情绪需要审视 → 固定机位，不打扰
情绪需要代入 → 手持，跟随呼吸
情绪需要压迫 → 缓慢推近
情绪需要释放 → 缓慢拉远
情绪需要孤独 → 广角，远离人物
情绪需要亲密 → 长焦，贴近面孔
```

- **One continuous take** can express a complete emotional arc better than 8 cuts. A 10-second locked-off wide shot of a character sitting alone in silence can be devastating.
- **Two shots** — one wide establishing, one close reaction — can carry an entire scene if the performance is rich.
- **No shot minimum.** Start from the emotion and ask: how few shots can carry this? Add shots only when the story demands a new perspective, not to fill panels.

Use this as guidance, not rule:

| 情绪功能 | 倾向 | 原因 |
|---|---|---|
| 需要呼吸空间 | 1-3 镜 | 长镜头给情绪发酵时间 |
| 需要节奏推进 | 3-5 镜 | 中速切换推动叙事 |
| 需要冲击/混乱 | 5-8 镜 | 快速切换制造紧张 |
| 一镜到底 | 1 镜 | 连续空间和表演建立真实感 |

**The storyboard exists to serve the emotion, not to fill panels.** Choose the minimum shot count that carries the weight. If one shot is enough, use one. If three shots feel right but five are "standard," use three.

## Film-Level Quality Standard

Every storyboard must aim for film quality, not "AI video" quality. The board must communicate:

### Forbidden AI Signatures (Board Must Visually Exclude)

- Unmotivated camera movement (floating, orbiting)
- Generic "cinematic lighting" with no source logic
- Perfect symmetry, no human imperfection
- Characters looking at camera for no reason
- Over-saturated, over-sharp, HDR-heavy look
- Random slow-motion with no narrative purpose

### Required Film Signatures (Board Must Visually Include)

- Motivated camera: every move drawn on the floor plan has a story reason
- Source-motivated light: light arrows originate from windows, practicals, sky
- Physical weight: movement arrows show gravity, inertia, effort
- Natural asymmetry: character positions and compositions avoid dead center
- Performance space: room in the frame for actors to breathe and react
- Temporal logic: time-of-day light changes, weather progression, practical light state

## Storyboard Image Region Layout

The storyboard image should contain these labeled regions:

1. **Segment Header**: segment ID, local duration, aspect ratio, scene function, emotion goal
2. **Floor Plan + Camera Map**: top-down movement diagram with CAM positions, paths, blocking (this is the largest, most important region)
3. **Lighting & Atmosphere Guide**: light direction, quality, color temp, atmosphere elements
4. **Emotion Map**: emotion keywords per beat, micro-expression triggers, tension arc
5. **Shot Timeline**: shot table with S01/S02..., timecodes, shot sizes, key visual notes (text kept minimal)
6. **Sound & VFX Markers**: cue positions on timeline, music/silence/foley/VFX annotations
7. **Continuity Locks**: asset codes used, forbidden drift, handoff notes
8. **Negative Notes**: only production-critical constraints (DO NOT CHANGE FACE, KEEP HAND POSITION)

## Text on the Board: Minimal Rule

- Shot labels, timecodes, asset codes, CAM markers → keep
- Emotion keywords → keep (short, large)
- Sound/VFX markers → keep (short)
- Descriptions of action, camera texture, light quality → **move to Seedance prompt**
- Dialogue, performance nuance, micro-expression detail → **move to Seedance prompt**

The board should be visually dense with diagrams, arrows, labels, and markers — not with paragraphs.

## The Complementary Pair Check

Before finalizing a storyboard, verify:

1. Does the board show what words can't precisely express? (movement paths, camera positions, light direction, emotional arc)
2. Is board text minimal — only logic labels and annotations?
3. Will the matching Seedance prompt fill in the missing texture, nuance, and sensory detail?
4. Is there any duplication between board and prompt? If yes, remove it from the board.
5. Can Seedance understand this board as a visual control chart, even if the user only writes "按此图生成"?

## Reusable Instruction Block

```text
这是给 Seedance 2.0 读取的故事板视觉控制图，不是海报，不是资产图，不是 moodboard。

它的任务是把文字表达不精准的东西画出来：
- 俯视动线图：空间轮廓、人物起始位置、移动路径箭头、关键阻挡位
- 机位设置：每个 CAM 的编号、景别、镜头、高度、运动方式、运动路径
- 灯光氛围：主光源方向和软硬、色温、氛围元素（烟/尘/雨/雾）
- 情绪关键词：每段节拍的情绪标注、微表情触发点、紧张/释放映射
- 声音/特效标注：音效入出点、音乐动机、VFX触发帧和行为

板上文字极少——只有逻辑标签和标注。不要写段落、不要写描述。
角色、场景、道具只用资产编号引用（CHAR_A, SCENE_01, PROP_PHONE）。

如果用户提供了原始资产图，必须以用户资产为最高优先级——故事板只调度镜头、动作、表演和节奏，禁止重新设计人物、场景和道具。

整体版式：导演+摄影指导勘景时的调度图风格。清楚、实用、一眼看懂空间关系和镜头逻辑。不是美术作品，不是海报。
电影级标准：运镜有动机、光源有出处、表演有空间、构图有不对称性、质感有人间感——不要AI塑料味。
```
