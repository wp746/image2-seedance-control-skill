# UE5 MetaHuman Technical Character Sheet Pattern

Use this pattern when character continuity requires technical precision across many views, especially for realistic humans, humanoids, fantasy creatures, robots, aliens, armor-heavy characters, and any role with important asymmetrical details.

## Best For

- AI live-action drama characters
- photoreal humanoid roles
- UE5 / game cinematic / virtual production style
- fantasy creatures with exact anatomy
- robot/alien/hard-surface characters
- characters with asymmetrical scars, tattoos, armor, garments, accessories, prosthetics, wings, tails, or weapons

## Core Intent

Create a complex UE5 MetaHuman-style production character reference sheet, not a glamour poster.

The sheet must prioritize strict production continuity:

- preserve face identity
- preserve body proportions
- preserve hairstyle/groom
- preserve outfit
- preserve accessories and props
- preserve markings, scars, tattoos
- preserve all asymmetrical left/right details
- never mirror asymmetrical details between views

Important side rule:

Left and right are always from the character's perspective.

## Layout Requirements

Use a technical 3D character-reference layout:

- orthographic-style body views
- clean studio lighting
- neutral background
- panel borders
- callout lines
- body landmark labels
- surface detail panels
- hands/feet reference
- hair/groom reference
- costume/armor/prop detail panels

Separate body documentation from complex costume documentation:

- Use a simple readable base outfit for body measurement panels.
- Put complex clothing, armor, asymmetrical garments, props, and accessories into dedicated costume panels.

## Required Fields

Include these fields in the Image2 prompt when relevant:

- CHARACTER TYPE: human / humanoid / fantasy creature / robot / alien / animal-like / stylized / realistic / other
- CHARACTER SUMMARY
- DEMOGRAPHIC BASELINE
- AGE / APPARENT AGE
- HEIGHT & BUILD
- PROPORTION STYLE: realistic 7-7.5 heads / fashion 8 heads / heroic / chibi / creature-specific / stylized
- FACE & HEAD DESIGN
- SKIN / SURFACE
- OUTFIT / ARMOR
- ASYMMETRICAL DETAILS
- ACCESSORIES / PROPS
- LABEL & VISUAL STYLE
- IMPORTANT CONTINUITY LOCKS

## Required Views

Ask Image2 to include:

1. Front view
2. 3/4 left view
3. Left profile
4. Back view
5. 3/4 right view
6. Right profile
7. Looking-up view
8. Action pose
9. Body measurement and landmark panel
10. Surface detail close-ups
11. Hands and feet close-ups
12. Hair/groom or head-detail panel
13. Costume/armor/prop detail panel

## Reusable Instruction Block

```text
创建一张复杂的 UE5 MetaHuman 风格制作角色参考表，用于 AI 视频、虚拟制片和 Seedance 2.0 角色连续性控制。必须严格遵守制作连续性：所有视角下角色必须保持同一张脸、同一身材比例、同一发型、同一服装、同一配饰、同一标记，以及所有左右不对称细节。左右方向始终以角色自身视角为准，绝不能在不同视图之间镜像不对称细节。

使用技术性 3D 角色参考图布局，不要做成漂亮海报。包含正交投影式人体视图、干净摄影棚灯光、中性背景、分格边框、标注线、身体特征点标签、表面细节面板、手脚参考、头发/groom 参考、服装/盔甲/道具细节面板。

将中性身体文档与复杂服装文档分开：身体测量面板使用简单可读的基础服装；复杂服装、盔甲、不对称衣片、道具和配饰放入专门的服装细节面板。
```

## Continuity Lock Labels

Use large labels:

- STRICT PRODUCTION CONTINUITY
- SAME FACE ALL VIEWS
- SAME BODY PROPORTIONS
- LEFT/RIGHT FROM CHARACTER POV
- NEVER MIRROR ASYMMETRY
- KEEP HAIR/GROOM
- KEEP OUTFIT/ARMOR
- KEEP MARKINGS
- KEEP ACCESSORIES

## When To Prefer This Over Director Character Sheet

Prefer this pattern when:

- exact multi-view consistency matters more than expressive art direction
- the character has complex costume, armor, hard-surface parts, or asymmetry
- Seedance must preserve the same actor-like body/face across many shots
- the project is closer to game cinematic, virtual production, sci-fi, fantasy, or technical character continuity

Prefer `character-design-sheet.md` when:

- performance, psychology, casting, cinematic portrait, and director-facing role identity matter more
- the board needs to guide acting, emotion, and costume taste rather than technical orthographic consistency
