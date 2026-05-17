# Dense Reference Stack Timeline Seedance Prompt

Use this for every Seedance 2.0 prompt after assets and storyboards are ready.

## Goal

Seedance prompts should actively use the available prompt budget. They should be detailed, exact, and reference-aware, usually aiming for a dense prompt under 2000 Chinese characters or an equivalent English length.

## Required Structure

Every Seedance prompt must include:

1. `REFERENCE STACK / 参考图职责`
2. `GLOBAL LOCK / 全局锁定`
3. `SEGMENT SETUP / 本段设定`
4. `START STATE / 起始状态`
5. `SHOT TIMELINE / 逐镜头时间线`
6. `PERFORMANCE / 表演`
7. `CAMERA + LENS / 摄影机与焦段`
8. `LIGHT + COLOR / 光线与色彩`
9. `SOUND + VFX / 声音与特效`
10. `END STATE / 结尾状态`
11. `CONTINUITY / 连续性`
12. `NEGATIVE / 负面约束`

## Reference Stack Rule

Do not vaguely say "use the references." Assign each uploaded image one job:

```text
@[CHAR_A] = identity lock: face, body, age, hair, costume, posture, performance baseline.
@[SCENE_01] = environment lock: geography, layout, entrances/exits, light source, fixed objects.
@[PROP_01] = prop lock: shape, material, scale, hand use, state.
Global look content = prompt-only style lock written directly into the Seedance prompt: palette, contrast, lens, grain, light, weather, camera mood, and forbidden style drift. Do not expose the variable name `STYLE_LOCK_TEXT` in the final user-facing prompt.
@[STYLE_LOOK_SAFE] = optional abstract style image only: palette, contrast, lens texture, grain, light quality; must not contain people, geography, props, vehicles, maps, signs, or readable text.
@[STORYBOARD_S01] = current segment director board: shot order, floor plan, camera positions, motion paths, lighting cues, sound/VFX cues, edit-out frame.
@[PrevLastFrame] = first-frame continuity only when continuing from previous segment.
```

When the asset library is large, point to the exact board and exact module/panel:

```text
Use @CHAR_MENGJUNQI, especially FULL BODY 4 VIEWS + FACE CLOSE-UP GRID + PERFORMANCE row.
Use @SCENE_FIELD_HQ, especially V04 CAMERA A, V08 LIGHT, and the top-down floor plan.
Use @PROP_MAP_TABLE, especially the hand/map interaction panel.
```

## Visual Bible Boundary Rule

Do not upload a mixed global visual bible to Seedance if it contains people, faces, city streets, buildings, vehicles, weapons, props, floor plans, maps, signs, or readable text. Extract its style into compact global look text internally, then repeat that descriptive text inside every Seedance prompt.

Only use an uploaded style image if it is explicitly `STYLE_LOOK_SAFE`: abstract swatches, lens/grain/light/weather/material samples with no story content. If uploaded, state that it controls style only and does not control identity, wardrobe, geography, props, vehicles, signs, or text.

## Text Boundary Rule

Every Seedance prompt for narrative footage must keep the frame clean:

```text
纯净电影画面；不要字幕、不要标题、不要画面内文字、不要控制板标签、不要随机中文/英文、不要水印、不要乱码。对白/旁白只作为声音/口型/表演节奏；历史字幕、地点字幕、文件可读文字和片名后期添加，除非本段明确使用单独TEXT_PROP_PLATE做特写。
```

## Shot Timeline Rule

Every shot must include:

- local timecode starting at `0:00`
- shot number matching storyboard
- shot size
- camera position/movement/lens
- composition/blocking
- character action
- dialogue/VO
- sound/VFX
- light/color state
- in/out handoff

If the storyboard has only one 15-second shot, the Seedance prompt should still divide the performance internally by seconds while keeping it one shot:

```text
S01 / 0:00-0:15 / ONE TAKE:
0:00-0:03 [in state]
0:03-0:08 [slow change]
0:08-0:12 [emotional peak]
0:12-0:15 [hold and edit-out]
```

## Negative Prompt Dimensions

Negative constraints must be specific to the project and segment:

- identity drift: face, age, body, hair, costume, injury, dirt, wetness
- scene drift: layout, door/window/road/river direction, time/weather, light source
- prop drift: shape, material, scale, hand, text, state
- style drift: palette, contrast, texture, lens, era
- spatial drift: left/right relationship, eyeline, distance, entrance/exit
- motion drift: floating camera, random slow motion, skipped action, impossible body physics
- edit drift: missing in/out frame, jump cut, merged shots, random extra shots
- text drift: subtitles, watermarks, UI, garbled labels unless required
- historical/domain drift: wrong era, wrong equipment, wrong uniforms, modern objects

## Chinese Dense Template

```text
参考图职责：
全片影像风格：直接写出色彩、对比、镜头、颗粒、光线、天气、摄影机气质、禁止风格漂移；每段都要按当前剧情重复并微调，不要暴露内部变量名。
@[STYLE_LOOK_SAFE] = 可选安全风格图：只控制色彩/光线/镜头/颗粒/质感；不得控制人物、服装、场景地理、道具、车辆、招牌、文字或剧情。
@[CHAR_...] = 角色身份锁：脸、年龄、体型、发型、服装、姿态、表演基准。
@[SCENE_...] = 场景空间锁：地理/室内布局、入口出口、固定物、光源方向、天气。
@[PROP_...] = 道具锁：形状、材质、尺度、持握方式、状态。
@[STORYBOARD_Sxx] = 当前导演故事板：镜头顺序、顶视动线、机位、构图、运镜、声音/VFX、结尾帧。

生成[时长]秒[画幅]视频。本段只使用本段内部时间码，从0:00开始。整体保持[直接写出的项目风格内容]。本段情绪目标：[情绪目标]。起始状态：[上一段末帧或本段起点]。不要把混有人物/场景/道具/文字的总视觉圣经图当全局参考。

逐镜头时间线：
S01 / [0:00-0:xx] / [景别] / [镜头焦段与运镜]：[构图占位、人物动作、台词/画外音、声音、光线、情绪、入帧和出帧状态]。
S02 / ...

表演：写清眼神、呼吸、停顿、手部动作、身体重量、台词力度。
摄影：写清机位、焦段、镜头高度、运动速度、是否手持、景深和运动模糊。
光线与色彩：写清主光来源、方向、软硬、色温、烟尘/雨/雾、调色。
声音/VFX：写清环境声、脚步/衣料/道具声、音乐进入退出、爆点、声音桥。
结尾状态：[下一段必须接住的最后一帧]。
连续性：角色、场景、道具、左右方向、眼线、光线、天气、情绪必须承接。
禁止：[按本项目定制的多维负面约束，覆盖身份/场景/道具/风格/空间/运动/剪辑/文字/年代错误]。纯净电影画面；不要字幕、不要标题、不要画面内文字、不要控制板标签、不要随机中文/英文、不要水印、不要乱码。
```

## English Dense Template

The English version must be production-equivalent to the Chinese prompt, not shorter:

```text
REFERENCE STACK:
Global look content: directly write the palette, contrast, lens, grain, light, weather, camera mood, and forbidden style drift. Repeat and adapt it in every segment; do not expose internal variable names.
@[STYLE_LOOK_SAFE] = optional safe abstract style image: palette, lighting, lens texture, grain, material samples only; it must not control identity, wardrobe, geography, props, vehicles, signs, text, or story facts.
@[CHAR_...] = character identity lock: face, age, body, hair, costume, posture, performance baseline.
@[SCENE_...] = environment lock: geography/layout, entrances/exits, fixed objects, light direction, weather.
@[PROP_...] = prop lock: shape, material, scale, hand use, state.
@[STORYBOARD_Sxx] = current director storyboard: shot order, top-down blocking, camera positions, composition, camera movement, sound/VFX cues, final frame.

Generate a [duration]-second [aspect ratio] video. Use local segment timecode only, starting at 0:00. Overall style: [directly written project look]. Emotional goal: [goal]. Start state: [previous final frame or segment opening]. Do not use any mixed visual-bible image containing people/scenes/props/text as a global Seedance reference.

SHOT TIMELINE:
S01 / [0:00-0:xx] / [shot size] / [lens and camera move]: [composition, blocking, action, dialogue/VO, sound, light, emotion, in-frame and out-frame state].
S02 / ...

PERFORMANCE: [eyes, breath, pauses, hand behavior, body weight, line delivery].
CAMERA: [camera position, lens, height, speed, handheld/locked/dolly, depth of field, motion blur].
LIGHT + COLOR: [source, direction, softness, color temperature, smoke/rain/fog, grade].
SOUND + VFX: [ambience, Foley, prop sounds, music cues, impact, sound bridge].
END STATE: [final frame the next segment must inherit].
CONTINUITY: Preserve character, scene, prop, screen direction, eyeline, lighting, weather, and emotion.
NEGATIVE: [project-specific constraints covering identity drift, scene drift, prop drift, style drift, spatial drift, motion drift, edit drift, text/watermark, historical/domain errors]. Clean cinematic frame only: no subtitles, no captions, no on-screen text, no control-board labels, no random Chinese/English text, no watermark, no corrupted text.
```

## Self Review

- Does every reference have one clear duty?
- Is global style controlled by descriptive text embedded in the prompt instead of an unsafe mixed visual bible image?
- If a STYLE_LOOK_SAFE image is referenced, is it abstract and free of people/scenes/props/vehicles/maps/text?
- Does every shot mirror the storyboard?
- Is the prompt detailed enough to approach the 2000-character budget without rambling?
- Does it include exact local timecodes?
- Does it include start and end states?
- Does the negative prompt cover likely failure modes for this specific project?
- Does the prompt forbid subtitles, on-screen text, control-board labels, random Chinese/English, and corrupted text?
