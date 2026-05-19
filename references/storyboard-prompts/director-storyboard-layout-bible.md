# Director Storyboard Layout Bible

Use this for every Seedance storyboard prompt. The storyboard is a director execution board, not a character asset sheet or a photoreal production still.

## Core Principle

The storyboard draws what the Seedance prompt cannot reliably describe. The Seedance prompt writes what the board cannot fully express. They are complementary, not competing.

Storyboard boards must use a **director sketch / previs line-art** visual language. Do not render photoreal scenes, finished cinematic stills, realistic faces, detailed wardrobe, skin texture, or rich production-design surfaces inside storyboard thumbnails. Seedance should read the board as camera/blocking/motion/sound/VFX structure, not as a competing visual source.

## Visual Style Lock

Use:

- grayscale or low-saturation sketch thumbnails
- rough silhouettes and faceless placeholders
- simple scene outlines and major set boundaries
- top-down floor-plan diagrams
- arrows for camera movement, actor movement, light, sound, VFX, and edit direction
- limited accent colors for reference duties, light zones, danger zones, and VFX triggers
- abstract VFX drawn as particles, waves, flashes, smoke arrows, impact rings, waveform marks, or translucent shapes

Avoid:

- photoreal live-action frames
- cinematic production stills
- detailed faces, pores, hair strands, costume folds, or prop textures
- realistic street/room/set rendering that can pollute Seedance scene references
- new character likenesses or wardrobe interpretations
- dense tiny dialogue text inside thumbnails

## Fixed Storyboard Board Layout

Default canvas: 16:9 horizontal, inheriting `PROJECT_BOARD_SYSTEM`.

The board must include these zones in a consistent order:

1. `HEADER`: first visible top title must start with the storyboard index, e.g. `S01 / YANAN FAREWELL / DIRECTOR STORYBOARD`; segment id, local duration, aspect ratio, scene function, emotional goal, asset codes.
2. `REFERENCE DUTIES`: very short; which assets control character, scene, prop, style. No long text.
3. `TOP-DOWN FLOOR PLAN`: largest zone. Shows scene outline, character placeholders, movement paths, camera positions, camera direction, action zones, entrance/exit.
4. `CAMERA + MOTION MAP`: CAM numbers, shot size, lens, height, movement path, speed/energy.
5. `LIGHT / ATMOSPHERE`: light source, direction, intensity, weather, smoke/rain/dust, practical light.
6. `SOUND / VFX`: ambience, music, Foley, dialogue/VO cue, VFX trigger and direction.
7. `SHOT GUIDE`: 1-8 shot rows or panels. Only include shot number, local timecode, shot size, composition/blocking, camera move, dialogue/VO cue, sound cue, edit-out frame.
8. `NEGATIVE LOCKS`: production-critical drift prevention only.

## Absolutely No Character Sheet Inside Storyboard

Do not include:

- full-body turnarounds
- face close-up grids
- wardrobe breakdowns
- expression sheets
- competing identity portraits

Use:

- asset codes
- colored silhouettes
- faceless placeholders
- backs/distant figures
- simple position markers

The user will upload character assets separately to Seedance. The storyboard only controls shot order, staging, camera, action, sound, light, VFX, and edit handoff. If a realistic face, costume, location detail, or prop texture is needed, it belongs in the asset board, not the storyboard.

## Shot Count Is Director-Driven

Never default to 5 shots mechanically.

Choose shot count by dramatic need:

- 1 shot: a continuous emotional hold, suspense observation, one-take movement, breath/atmosphere.
- 2 shots: establish + reaction, reveal + consequence.
- 3 shots: setup, turn, aftermath.
- 4-6 shots: normal 10-15s dialogue/action/suspense segment.
- 7-8 shots: fast action, chaos, montage, cause-effect chain.

If one held shot creates better rhythm and film quality, use one shot. More generated clips are acceptable if they preserve cinematic quality and continuity. If a scene needs 20+ seconds, split it into linked storyboard/Seedance segments and design the next segment to continue from the previous final frame or generated video.

## Shot Guide Fields

Every shot row/panel must include only:

- `SHOT`
- `TIME`
- `SIZE`
- `COMPOSITION / BLOCKING`
- `CAMERA`
- `DIALOGUE / VO`
- `SOUND / VFX`
- `EDIT OUT`

Avoid long action paragraphs inside the image. Put detailed performance and timing in the Seedance prompt.

## Image2 Prompt Injection

Chinese:

```text
必须使用固定导演故事板版式：顶部主标题必须以本故事板编号开头，例如 S01 / 场次英文名 / DIRECTOR STORYBOARD，并且 S编号必须和提示词编号完全一致、最大号、左对齐；顶部段落信息和资产职责，最大区域为顶视运动平面图，清楚展示场景轮廓、人物占位、运动路线、机位、镜头方向、入口出口；旁边是机位/运镜路线图、光影氛围、声音/特效标注；底部是本段分镜引导，只写镜号、时间、景别、构图占位、运镜、对白/画外音、音效/VFX、剪辑出口。故事板里不得画角色三视图、人脸特写、服装拆解或新的角色设计，只能用资产编号、无脸占位和动线箭头。
故事板视觉形式必须是导演草图/预演线稿，不是实景照片或电影剧照：灰阶线稿、粗略人物剪影、无脸占位、简单场景轮廓、顶视平面图、机位箭头、运镜路线、光区、声音/VFX图标、少量强调色。禁止照片级真实人物、真实街景/室内渲染、电影剧照、皮肤细节、服装纹理、道具材质细节和新角色长相。
```

English:

```text
Use the fixed director storyboard layout. The first visible top title must begin with the storyboard number, for example S01 / SCENE NAME / DIRECTOR STORYBOARD; the S-number must match the prompt number exactly, largest and left-aligned. Include top segment header and reference duties; the largest zone is a top-down movement floor plan showing scene outline, character placeholders, movement paths, camera positions, camera direction, entrance and exit; side zones show camera/motion map, lighting atmosphere, sound/VFX cues; bottom zone is the segment shot guide with shot number, timecode, shot size, composition/blocking, camera move, dialogue/VO, sound/VFX, and edit-out frame only. Do not include character turnarounds, face close-up grids, costume breakdowns, or new character designs. Use asset codes, faceless placeholders, and movement arrows only.
Storyboard visual form must be director sketch / previs line-art, not photoreal footage or cinematic stills: grayscale linework, rough silhouettes, faceless placeholders, simple scene outlines, top-down floor plan, camera arrows, motion routes, light zones, sound/VFX icons, limited accent colors. No realistic faces, photoreal streets or interiors, cinematic production stills, skin detail, wardrobe texture, prop material detail, or new character likeness.
```

## Negative Rules

- no character asset design inside storyboard
- no photoreal storyboard thumbnails
- no cinematic production stills
- no realistic faces, skin detail, wardrobe texture, or new character likeness
- no texture-rich street/interior rendering that competes with scene assets
- no long paragraphs in the image
- no default 5-shot formula
- no unclear floor plan
- no camera moves without story reason
- no random shot count
- no new props/locations not in assets
- no duplicate responsibilities between storyboard and asset board
