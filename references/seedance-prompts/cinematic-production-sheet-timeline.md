# Cinematic Production Sheet Timeline Seedance Prompt Pattern

Use this pattern after GPT Image 2 has generated a cinematic production plan sheet containing character references, environment, floor plan, camera positions, storyboard panels, color palette, lighting, mood, and style notes.

## Core Intent

Seedance should treat the uploaded production sheet as a strict directing document, not just a mood image.

The prompt should:

- bind character identity to the board
- bind environment geography to the floor plan
- follow the storyboard shot order
- preserve camera positions and movement direction
- maintain color, lighting, mood, VFX, and style
- generate one continuous 4-15 second segment

## Best For

- one-scene 10-15 second cinematic clip
- two-character confrontation
- action collision
- fantasy / supernatural VFX reveal
- noir, cyberpunk, disaster, monster, martial arts, yakuza, game-trailer style scenes
- any board created with `cinematic-production-plan-sheet.md`

## Prompt Structure

Use this order:

1. `REFERENCE LOCK`
2. `CINEMATIC SETUP`
3. `CHARACTERS`
4. `ENVIRONMENT / GEOGRAPHY`
5. `TIMELINE`
6. `STYLE AND QUALITY`
7. `CONTINUITY RULES`
8. `NEGATIVE / FORBIDDEN DRIFT`

## Timeline Rules

Use 4-6 beats for one Seedance generation.

Each beat should include:

- time range
- camera position / shot size / movement
- character action
- visual effect or physical effect
- emotional change
- edit-out or end state

Keep each beat short and direct. Seedance performs better when the prompt is firm and cinematic, not overwritten with long prose.

## Reusable Seedance Prompt

```text
请严格参考我上传的电影制作计划表和资产图生成连续视频。制作计划表是最高优先级导演文件，不是普通氛围参考。必须遵守其中的角色设定、环境平面图、人物移动路径、CAM 机位编号、分镜顺序、调色板、灯光、VFX 和风格说明。

[CINEMATIC SETUP]
[一句话定义类型片风格、镜头质感、核心氛围。例如：超写实电影级黑帮幻想，雨夜霓虹小巷，湿地反射，蒸汽，粗粝神秘气氛。]

[CHARACTERS]
[CHARACTER_A]：[核心身份、服装、发型、特殊标记、动作状态、VFX 签名。必须与制作计划表一致。]
[CHARACTER_B]：[核心身份、服装、发型、特殊标记、动作状态、VFX 签名。必须与制作计划表一致。]

[ENVIRONMENT / GEOGRAPHY]
[地点、时间、天气、灯光来源、地面材质、背景层次。严格遵守制作计划表中的俯视平面图、人物站位、移动方向和 CAM 机位关系，不得随机换场景或改变空间方向。]

[TIMELINE]
0-3秒：[CAM 1 / 景别 / 角度 / 运镜] [画面内容、人物动作、情绪、光线/VFX、空间状态。]
3-6秒：[CAM 2 / 景别 / 角度 / 运镜] [画面内容、人物动作、情绪、光线/VFX、空间状态。]
6-9秒：[CAM 3 / 景别 / 角度 / 运镜] [画面内容、人物动作、情绪、光线/VFX、空间状态。]
9-12秒：[CAM 4 / 景别 / 角度 / 运镜] [画面内容、人物动作、情绪、光线/VFX、空间状态。]
12-15秒：[CAM 5 / 景别 / 角度 / 运镜] [画面内容、人物动作、情绪、光线/VFX、空间状态。]

[STYLE AND QUALITY]
照片级写实，电影现实主义，高级故事板质感，真实材质，连续光线，统一调色，符合制作计划表的色卡和灯光逻辑。运动自然、有重量、有物理反馈。VFX 必须贴合角色动作和环境光，不得像贴纸。

[CONTINUITY RULES]
角色脸、身形、服装、纹身/标记、发型、道具、能量颜色保持一致。
人物移动方向、相对距离、场景布局、地面反射、背景霓虹/建筑/道具位置保持一致。
每个镜头的出镜状态必须自然衔接下一个镜头的入镜状态。
动作从蓄势到爆发逐步升级，情绪从对峙到冲突递进。

[FORBIDDEN]
不得换脸、换衣服、换发型、换场景、改变左右关系、随机增加角色、随机改变 VFX 颜色、跳切割裂、机位乱跳、空间方向错乱、画面文字、水印、字幕乱码。
```

## Compact Variant

Use this when the user only wants a short Seedance input sentence beside the uploaded board:

```text
严格参考上传的电影制作计划表和资产图，把制作表中的角色、环境平面图、人物移动路径、CAM 机位、分镜顺序、调色板、灯光、VFX 和风格作为最高优先级，生成一个连续 [时长] 秒电影镜头。按 S01-S05 时间线执行，保持角色一致、场景一致、空间方向一致、动作物理连续、情绪逐步升级，禁止换脸、换衣、换场景、机位错乱、VFX 颜色漂移和跳切割裂。
```

## Repair Hooks

If the generated result fails:

- identity drift: repeat only `REFERENCE LOCK` + `CHARACTERS` + forbidden drift
- spatial confusion: emphasize `ENVIRONMENT / GEOGRAPHY` and floor plan
- weak action: rewrite `TIMELINE` with stronger verbs and physical consequences
- VFX sticker feel: specify VFX contact points, reflected light, shadow, particles, and environmental reaction
- broken edit: add each shot's final state and next shot's first state
