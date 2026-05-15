# Director Storyboard Layout Bible

Use this for every Seedance storyboard prompt. The storyboard is a director execution board, not a character asset sheet.

## Core Principle

The storyboard draws what the Seedance prompt cannot reliably describe. The Seedance prompt writes what the board cannot fully express. They are complementary, not competing.

## Fixed Storyboard Board Layout

Default canvas: 16:9 horizontal, inheriting `PROJECT_BOARD_SYSTEM`.

The board must include these zones in a consistent order:

1. `HEADER`: segment id, local duration, aspect ratio, scene function, emotional goal, asset codes.
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

The user will upload character assets separately to Seedance. The storyboard only controls shot order, staging, camera, action, sound, light, VFX, and edit handoff.

## Shot Count Is Director-Driven

Never default to 5 shots mechanically.

Choose shot count by dramatic need:

- 1 shot: a continuous emotional hold, suspense observation, one-take movement, breath/atmosphere.
- 2 shots: establish + reaction, reveal + consequence.
- 3 shots: setup, turn, aftermath.
- 4-6 shots: normal 10-15s dialogue/action/suspense segment.
- 7-8 shots: fast action, chaos, montage, cause-effect chain.

If one 15-second shot creates better rhythm and film quality, use one shot. More generated clips are acceptable if they preserve cinematic quality and continuity.

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
必须使用固定导演故事板版式：顶部段落信息和资产职责，最大区域为顶视运动平面图，清楚展示场景轮廓、人物占位、运动路线、机位、镜头方向、入口出口；旁边是机位/运镜路线图、光影氛围、声音/特效标注；底部是15秒分镜引导，只写镜号、时间、景别、构图占位、运镜、对白/画外音、音效/VFX、剪辑出口。故事板里不得画角色三视图、人脸特写、服装拆解或新的角色设计，只能用资产编号、无脸占位和动线箭头。
```

English:

```text
Use the fixed director storyboard layout: top segment header and reference duties; the largest zone is a top-down movement floor plan showing scene outline, character placeholders, movement paths, camera positions, camera direction, entrance and exit; side zones show camera/motion map, lighting atmosphere, sound/VFX cues; bottom zone is the 15-second shot guide with shot number, timecode, shot size, composition/blocking, camera move, dialogue/VO, sound/VFX, and edit-out frame only. Do not include character turnarounds, face close-up grids, costume breakdowns, or new character designs. Use asset codes, faceless placeholders, and movement arrows only.
```

## Negative Rules

- no character asset design inside storyboard
- no long paragraphs in the image
- no default 5-shot formula
- no unclear floor plan
- no camera moves without story reason
- no random shot count
- no new props/locations not in assets
- no duplicate responsibilities between storyboard and asset board
