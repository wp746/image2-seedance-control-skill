# PREVIS Action VFX Music Timeline Pattern

Use this pattern for highly kinetic action, dance, fashion motion, abstract VFX performance, ink/paint/energy trails, music-driven movement, or any short where the body, camera, VFX, and sound must synchronize tightly.

## Best For

- hiphop / street dance with VFX
- ink wash action
- calligraphy brush motion
- fashion silhouette performance
- abstract movement films
- martial arts with elemental trails
- 12-15 second high-impact social clips
- motion tests where randomness must be reduced

## Core Method

Step 1: Generate a director-style PREVIS action storyboard with GPT Image 2 using simple natural language.

Purpose:

- reduce motion randomness
- lock action flow
- lock camera movement
- make VFX trails feel intentionally directed
- make the final Seedance video follow a rhythm instead of drifting

Step 2: Use the PREVIS board as the reference image for Seedance.

## Required Planning Layers

The prompt should define:

- SUBJECTS: performer, wardrobe, object/prop, how VFX attaches to body/prop
- ENVIRONMENT: often minimal so motion reads clearly
- MUSIC: rhythm curve, density changes, silence/drop moments, final accent
- COLOR LOGIC: strict palette, e.g. pure white + black ink only
- STYLE: visual language, VFX type, composition logic
- TIMELINE: second-by-second or 2-second beats
- SFX: sound design per beat

## PREVIS Board Requirements

The Image2 PREVIS board should include:

- clear action poses
- camera direction arrows
- motion trails/VFX trails
- beat/timing labels
- body direction and weight shift
- prop path
- density progression of VFX
- final frame/payoff

Keep the board visually readable. For kinetic work, motion arrows and trail shapes matter more than long text.

## Timeline Structure

For a 15-second sequence, a useful rhythm is:

- 0:00-0:02: first motion hook, establish prop/VFX trail
- 0:02-0:04: camera reacts to arm/body movement
- 0:04-0:06: pull-back/push-in contrast, vertical action or level change
- 0:06-0:08: rotation/orbit, circular trails
- 0:08-0:10: density increase, aggressive advance
- 0:10-0:12: close push or pass-by, VFX wraps body
- 0:12-0:13.5: brief tension hold or near-silence
- 0:13.5-0:15: final impact, VFX floods frame or lands on strong pose

## Reusable Image2 Instruction Block

```text
请创建一张导演风格 PREVIS 动作故事板，用于控制 Seedance 2.0 的动作、镜头运动、VFX 轨迹和音乐节奏。重点不是漂亮海报，而是减少运动随机性，让动作、摄影机和特效流动都显得经过导演设计。

画面需要展示：关键动作姿态、身体重心变化、镜头运动箭头、道具运动路径、VFX/墨迹/能量轨迹、节奏时间码、视觉密度变化和最终爆点。每个动作节点都要清晰、连续、可执行。

使用清晰分镜版式，标注 TIME、ACTION、CAMERA、VFX TRAIL、MUSIC/SFX、FINAL PAYOFF。运动箭头和轨迹线必须醒目，避免长篇小字。
```

## Reusable Seedance Prompt Structure

```text
Use the attached PREVIS action storyboard as the exact motion and camera reference.

SUBJECTS:
[performer / wardrobe / prop / VFX relationship]

ENVIRONMENT:
[minimal or specific environment]

MUSIC:
[rhythm curve, beat density, silence/drop, final accent]

COLOR LOGIC:
[strict palette]

STYLE:
[visual language + VFX behavior + composition]

TIMELINE:
0:00-0:02: [camera + action + VFX + SFX]
0:02-0:04: [camera + action + VFX + SFX]
0:04-0:06: [camera + action + VFX + SFX]
0:06-0:08: [camera + action + VFX + SFX]
0:08-0:10: [camera + action + VFX + SFX]
0:10-0:12: [camera + action + VFX + SFX]
0:12-0:13.5: [tension hold / drop / contraction]
0:13.5-0:15: [final impact / frame flood / strong ending]
```

## Design Principles

- Treat the prop as part of the choreography.
- VFX must be caused by body/prop motion, not random decoration.
- Camera motion should react to physical movement.
- Sound design should be written into each beat.
- Color palette should be strict for graphic clarity.
- Negative space can be a major composition tool.
- Final frame should have a strong payoff, e.g. full-frame ink flood, impact pose, blackout, whiteout.

## When Not To Use

Avoid this pattern for:

- dialogue scenes
- slow emotional drama
- product process demos
- multi-location stories

For dance without heavy VFX, use `sixteen-panel-dance-choreography-board.md`.

For product/process flow, use `infographic-8-shot-poster.md`.
