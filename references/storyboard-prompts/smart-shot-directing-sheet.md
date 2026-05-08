# Smart Shot Directing Sheet Pattern

Use this pattern when a vague idea or one-sentence concept must become a complete cinematic shot plan before video generation.

Core principle:

Production document leads. Video is proof.

## Best For

- vague one-sentence ideas
- cinematic fantasy/action scenes
- fashion campaigns
- product spots
- narrative scenes
- detective/interview scenes
- any project where camera movement, blocking, lighting, and character consistency must feel directed rather than random

## Core Method

This is a two-stage planning workflow:

1. One model interprets the idea and builds the shot plan / directing sheet.
2. Seedance 2.0 renders the final cinematic sequence from the locked plan.

The user only provides the idea. The planning board handles visual direction.

## Required Directing Sheet Modules

A Smart Shot-style Image2 board should include:

- character reference sheets: front, side, back, close-up, costume, detail views
- color palette defining visual identity
- environment and set design showing world, atmosphere, and location details
- floor plan with top-down blocking, character placement, and camera positions
- side elevation view for composition and spatial depth
- storyboard panels planned step by step
- camera directions: shot type, movement, lens choice, timing
- lighting notes for mood and contrast
- mood and style keywords
- cinematography notes defining the sequence's visual language

## Why It Works

This pattern makes AI video feel directed because:

- camera moves with intention
- shot changes feel designed
- character consistency is pre-planned
- motion, framing, and lighting follow a locked creative direction
- the video feels like a rendered scene, not a random AI clip

## Board Layout

Use a wide 16:9 cinematic production sheet with distinct sections:

1. `CONCEPT / LOGLINE`
2. `CHARACTER REFERENCES`
3. `ENVIRONMENT / SET DESIGN`
4. `FLOOR PLAN / BLOCKING`
5. `SIDE ELEVATION / DEPTH`
6. `STORYBOARD PANELS`
7. `CAMERA PLAN`
8. `LIGHTING NOTES`
9. `MOOD / STYLE KEYWORDS`
10. `CINEMATOGRAPHY NOTES`

If the image becomes too dense, split into:

- asset/directing sheet
- storyboard/camera sheet

## Reusable Image2 Instruction Block

```text
请把这个一句话概念转化成一张完整的电影导演总控板 / Smart Shot directing sheet。原则是：production document leads, video is proof。视频生成前，必须先把角色、环境、空间、镜头、灯光和摄影语言锁定。

生成 16:9 横向高级电影前期制作板，不是海报。版面必须清晰分区，包含：
1. CONCEPT / LOGLINE：一句话故事概念
2. CHARACTER REFERENCES：角色正面、侧面、背面、特写、服装和关键细节
3. ENVIRONMENT / SET DESIGN：世界观、氛围、地点细节
4. FLOOR PLAN / BLOCKING：俯视平面图，标出角色位置、移动路径、镜头机位
5. SIDE ELEVATION / DEPTH：侧立面图，展示构图层次和空间深度
6. STORYBOARD PANELS：按步骤规划镜头
7. CAMERA PLAN：景别、镜头运动、镜头焦段、时间安排
8. LIGHTING NOTES：主光、轮廓光、环境光、对比关系
9. MOOD / STYLE KEYWORDS：情绪和风格关键词
10. CINEMATOGRAPHY NOTES：整体摄影语言

画面必须像真正电影团队的前期导演文件。所有文字标签要大而清晰，避免密集小字。角色、场景、镜头和灯光设计必须服务同一个创意方向。
```

## Seedance Pairing Prompt

```text
Use the attached directing sheet as the locked production plan. Follow the character references, environment design, floor plan, blocking, storyboard panels, camera plan, lighting notes, mood keywords, and cinematography notes. Generate a cinematic sequence where the camera movement feels intentional, the framing feels designed, the characters remain consistent, and the lighting follows the planned mood.
```

## Application Patterns

### Fantasy / Action Scene

Use when prompt resembles:

- a blind oracle and a shadow king confront each other in burning temple ruins
- an ice monarch battles a dark shadow lord in a ruined frozen courtyard

Focus on:

- character silhouettes
- opposing positions
- environment destruction
- elemental effects
- dramatic blocking
- lens choices and lighting contrast

### Narrative Scene

Use when prompt resembles:

- a detective questions a witness in a dim apartment

Focus on:

- blocking
- tense close-ups
- over-the-shoulder shots
- controlled camera movement
- motivated practical lighting

### Fashion Campaign

Use when prompt resembles:

- a streetwear model moves through a neon-lit city

Focus on:

- wardrobe consistency
- editorial pacing
- hero shots
- rhythmic camera movement
- campaign-ready frames

### Product Spot

Focus on:

- product hero shot
- cutaways
- texture close-ups
- controlled lighting
- brand-safe composition

## When Not To Use

Avoid this pattern when the task only needs a simple 8-shot process board or a pure dance choreography sheet. Use:

- `infographic-8-shot-poster.md` for simple process/product/lifestyle
- `sixteen-panel-dance-choreography-board.md` for dance/movement
- `two-part-cinematic-production-board.md` for 25-40 second emotional shorts
