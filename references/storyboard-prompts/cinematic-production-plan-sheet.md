# Cinematic Production Plan Sheet Pattern

Use this pattern when a simple idea needs to become a compact GPT Image 2 pre-production control board before Seedance 2.0 generation.

This pattern is especially useful when the user says things like:

- "把这个想法做成电影感控制图"
- "先出一张能指导 Seedance 的制作计划表"
- "我只有一个简单冲突，帮我补成可拍的前期板"
- "需要角色、场景、机位、调色、灯光、分镜都在一张图里"

## Core Intent

Do not generate a random cinematic image.

Generate a professional cinematic pre-production plan sheet that defines the creative direction before video generation. The board should help Seedance understand:

- who the characters are
- where the scene happens
- how characters move through the space
- where the camera is placed
- what each shot does
- what color, light, mood, style, and VFX rules must remain consistent

## Best For

- 10-15 second action or fantasy beat
- two-character confrontation
- short monster / superhero / martial arts moment
- noir, yakuza, cyberpunk, fantasy, disaster, horror, game-trailer style scene
- a single scene where space relationship and camera positions matter
- converting one sentence into a strong visual direction board

## Board Layout

Create one clean production plan sheet, not a decorative poster.

Required sections:

1. `TITLE / PROJECT NAME`
2. `CHARACTER REFERENCES`
3. `ENVIRONMENT`
4. `TOP-DOWN FLOOR PLAN`
5. `CHARACTER MOVEMENT PATHS`
6. `NUMBERED CAMERA POSITIONS`
7. `STORYBOARD / SHOT LIST`
8. `COLOR PALETTE`
9. `LIGHTING / MOOD / STYLE NOTES`

The board must use thin borders, clear section titles, legible printed labels, directional arrows, numbered shot markers, and color swatches. Keep text short enough to be readable inside the image.

## Character Reference Section

For each character, define:

- role and dramatic function
- age range / body type / ethnicity only if story-relevant
- face and hair identity
- wardrobe, shoes, accessories
- tattoos, scars, special marks, or hero props
- power / VFX signature if relevant
- forbidden drift notes

Use contrast between characters when helpful: white vs dark red, gold vs red-black energy, clean suit vs damaged suit, warm vs cold palette.

## Environment Section

Define the set as a film location, not a vague background.

Include:

- main location name
- time of day
- weather
- practical light sources
- set dressing
- floor texture
- reflective surfaces
- background depth
- atmosphere such as smoke, rain, steam, dust, sparks, ash

## Floor Plan And Blocking

Always include a top-down floor plan when the scene has action, confrontation, pursuit, or multi-character staging.

The floor plan must show:

- character starting positions
- movement paths with arrows
- object / obstacle placement
- camera positions labeled `CAM 1`, `CAM 2`, etc.
- shot numbers mapped to camera positions
- direction of screen movement

This prevents spatial confusion and helps Seedance preserve geography across shots.

## Storyboard Shot List

Use 4-6 shots for one 10-15 second Seedance segment.

Each shot should include:

- shot number
- timing range
- shot size / angle
- camera movement
- core visual
- character action
- VFX or physical effect
- emotional beat
- edit-out state

Example structure:

```text
S01 / 0-3s / WIDE LOW CRANE: two characters face off in rain; neon reflections; tension rises.
S02 / 3-6s / MEDIUM SIDE TRACK: hero steps forward, removes jacket, reveals signature mark.
S03 / 6-9s / FRONT CLOSE HANDHELD: villain's mark glows; rain streaks across face.
S04 / 9-12s / WIDE LOW DOLLY: hero energy rises behind body, forming a large visible shape.
S05 / 12-15s / WIDE DYNAMIC PUSH-IN: two forces collide; shockwave fills the frame; end on suspended impact.
```

## Color Palette

Use 5-7 explicit swatches. The palette should separate:

- character identity colors
- environment base colors
- VFX energy colors
- highlight / practical light colors
- ground or material colors

## Reusable Image2 Instruction Block

```text
创建一张名为“[PROJECT TITLE]”的电影制作计划表，画面风格像专业电影前期制作板，不是宣传海报。16:9 横向大画布，布局干净，细边框，真实电影概念图质感，所有标签清晰可读。

这张图必须把一个简单创意转化成可供 Seedance 2.0 理解的前期控制图。请包含以下区域：

1. CHARACTER REFERENCES / 角色参考：
[CHARACTER_A]：[身份、年龄感、体型、脸型、发型、服装、鞋子、配饰、特殊标记、能力/VFX、禁止变化项]
[CHARACTER_B]：[身份、年龄感、体型、脸型、发型、服装、鞋子、配饰、特殊标记、能力/VFX、禁止变化项]

2. ENVIRONMENT / 环境：
[具体地点、时间、天气、灯光来源、地面材质、背景层次、道具陈设、烟雾/雨水/灰尘/反射等气氛元素]

3. TOP-DOWN FLOOR PLAN / 俯视平面图：
画出主要场景的俯视布局，包含人物起始位置、移动路径箭头、障碍物/关键道具、CAM 1-CAM 5 摄像机位置、每个机位对应的镜头编号、角色运动方向和屏幕方向。

4. STORYBOARD / 分镜，共 [4-6] 个镜头：
S01 / [0-3s] / [景别+角度+运镜]：[画面内容、人物动作、情绪、光线/VFX、出镜状态]
S02 / [3-6s] / [景别+角度+运镜]：[画面内容、人物动作、情绪、光线/VFX、出镜状态]
S03 / [6-9s] / [景别+角度+运镜]：[画面内容、人物动作、情绪、光线/VFX、出镜状态]
S04 / [9-12s] / [景别+角度+运镜]：[画面内容、人物动作、情绪、光线/VFX、出镜状态]
S05 / [12-15s] / [景别+角度+运镜]：[画面内容、人物动作、情绪、光线/VFX、出镜状态]

5. COLOR PALETTE / 调色板：
[5-7 个色块：角色主色、反派主色、环境底色、灯光色、VFX 色、材质色]

6. LIGHTING / MOOD / STYLE NOTES / 灯光氛围风格：
灯光：[主光、轮廓光、实际光源、反射逻辑]
氛围：[紧张/神秘/暴力/浪漫/荒诞/灾难/高级等]
风格：[照片级写实、电影现实主义、高级故事板、具体类型片风格]

要求：角色在所有分镜中保持完全一致；空间关系不得错乱；机位、运动路径和分镜编号必须互相对应；文字要少而清晰，视觉信息优先，方便用户把这张图和资产图一起上传给 Seedance 2.0。
```

## Seedance Handoff

After generating this board, the Seedance prompt should not repeat every detail loosely. It should reference the board as a strict production sheet, then provide a concise timeline.

Use `references/seedance-prompts/cinematic-production-sheet-timeline.md` when writing the video prompt from this board.

## When Not To Use

Avoid this pattern when:

- the user needs a full episode broken into many scenes
- the scene is dialogue-heavy and depends on subtle performance
- the user already has a complete storyboard table
- the project needs many asset boards before a storyboard

For full drama episodes, split by scene and use `storyboard-control-board.md` or `traditional-storyboard-table-board.md`.
