# Dense Reference Stack Timeline Seedance Prompt

Use this for every Seedance 2.0 prompt after assets and storyboards are ready.

## Goal

Seedance prompts should actively use the available prompt budget. They should be detailed, exact, and reference-aware, usually aiming for a dense prompt under 5000 Chinese characters or an equivalent English length.

## Required Structure

Every Seedance prompt must include:

1. `REFERENCE STACK / 参考图职责`
2. `GLOBAL LOCK / 全局锁定`
3. `SEGMENT SETUP / 本段设定`
4. `START STATE / 起始状态`
5. `SCREEN DIRECTION / 180度轴线锁`
6. `VOICE LOCK / 角色音色锁`
7. `SHOT TIMELINE / 逐镜头时间线`
8. `PERFORMANCE / 表演`
9. `CAMERA + LENS / 摄影机与焦段`
10. `LIGHT + COLOR / 光线与色彩`
11. `SOUND + VFX / 声音与特效`
12. `END STATE / 结尾状态`
13. `CONTINUITY / 连续性`
14. `NEGATIVE / 负面约束`

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

Final Seedance prompts must use the actual names displayed by the video tool after upload: `@图片1`, `@图片2`, `@图片3`... Do not circle references in the final prompt as `@A01-EN`, `@CHAR_A`, `@SCENE_01`, or `@STORYBOARD_S01`, because the tool will show only image numbers. The board/asset codes still matter, but they should appear inside parentheses after the numbered reference.

Before every fenced Seedance prompt, add one Markdown upload note line for the user. This line is not part of the prompt to copy, and it must map every `@图片N` to the exact generated board and English label:

```markdown
> 上传参考图（这行不复制进 Seedance）：@图片1 = Prompt A01-EN / Character Asset Board / CHAR_LI_XIA；@图片2 = Prompt A06-EN / Scene Asset Board / SCENE_YANAN；@图片3 = Prompt S01-EN / Storyboard Board / STORYBOARD_01_EN。
```

The upload note must be outside the fenced ```text block. The fenced Seedance prompt itself still uses `@图片N(...)` references.

Final Seedance prompts must not use vague delegation language such as "角色资产管脸/服装，场景资产管空间，道具资产管手持和位置，故事板管机位/路线" or "character assets control face/costume, scene assets control geography, prop assets control hand-use, storyboard controls camera/path."

Replace vague duties with exact reference targeting:

```text
本段按顺序上传：@图片1=A01-EN角色板；@图片2=A06-EN场景板；@图片3=S01-EN故事板。
@图片1（A01-EN/CHAR_LI_XIA）读FULL BODY 4 VIEWS + FACE GRID + 服装状态“延安灰长衫+行李箱” + 表情“使命坚定”，忽略上海雨夜/阁楼服装。
@图片2（A06-EN/SCENE_YANAN_BAOTA）读上半区宝塔山送别九视角 + 下方TOP VIEW PLAN里李侠站位/首长站位/敬礼方向/光源方向，忽略窑洞面板。
@图片3（S01-EN/STORYBOARD）读TOP VIEW + CAMERA A/B/C + SHOT PANELS + SOUND/VFX，忽略任何控制板标签，不把它们生成到画面里。
```

Every referenced board line should answer five questions: which upload number the platform will display; which image/board that number corresponds to; which asset code/module/panel/label inside that board should be read; what exact information should be extracted; which nearby modules/panels/text should be ignored to avoid contamination. If the same uploaded board contains two needed assets, reuse the same image number, e.g. `@图片1（A04-EN/CHAR_LIU_NINA）` and `@图片1（A04-EN/CHAR_YE_DANQIU）`.

## Camera Package + Lens Rule

Every Seedance prompt must include a project-appropriate camera package and per-shot focal lengths. Do not write only "cinematic camera" or "long lens." Use concrete specs, for example:

```text
Camera package: ARRI Alexa 35, 4.6K Open Gate downsampled to 4K 16:9, 24fps, 180-degree shutter, vintage Cooke Speed Panchro/i Classic prime set, Kodak 5219/5207 film-emulation grain, restrained handheld/dolly grammar.
```

Each shot in the timeline must include a focal length:

```text
S01 / 0:00-0:03 / WIDE / 32mm locked low tripod...
S02 / 0:03-0:07 / MEDIUM CLOSE / 50mm slow push...
S03 / 0:07-0:10 / CLOSE-UP / 75mm handheld micro drift...
```

Choose focal lengths from the same lens family unless a special macro/telephoto reason exists. Historical, realist, spy, war, police, and period projects should usually prefer restrained vintage primes and avoid ultra-wide distortion unless geography demands it.

## Visual Bible Boundary Rule

Do not upload a mixed global visual bible to Seedance if it contains people, faces, city streets, buildings, vehicles, weapons, props, floor plans, maps, signs, or readable text. Extract its style into compact global look text internally, then repeat that descriptive text inside every Seedance prompt.

Only use an uploaded style image if it is explicitly `STYLE_LOOK_SAFE`: abstract swatches, lens/grain/light/weather/material samples with no story content. If uploaded, state that it controls style only and does not control identity, wardrobe, geography, props, vehicles, signs, or text.

## Text Boundary Rule

Every Seedance prompt for narrative footage must keep the frame clean:

```text
纯净电影画面；不要字幕、不要标题、不要画面内文字、不要控制板标签、不要随机中文/英文、不要水印、不要乱码。对白/旁白只作为声音/口型/表演节奏；历史字幕、地点字幕、文件可读文字和片名后期添加，除非本段明确使用单独TEXT_PROP_PLATE做特写。
```

## Voice Lock Rule

Voice is a recurring character asset. Do not let Seedance improvise a new voice per segment. For every main or recurring speaking character, define a `VOICE_LOCK` in the Seedance prompt itself. This belongs in text/audio direction, not in Image2 visual boards.

Each `VOICE_LOCK` should include:

- age range and vocal age
- pitch range: low / mid-low / mid / high
- timbre: clear, hoarse, warm, cold, nasal, dry, thick, thin, metallic, breathy, etc.
- breath support: shallow, steady, thick, broken, restrained
- volume and projection: whisper, low voice, normal, command voice, never shouting unless scripted
- rhythm and speech rate: normal Chinese dramatic speech is usually about 3-4 chars/sec; slower for tension
- articulation: clipped, clear, soft consonants, regional cadence, educated diction, soldier-like brevity
- accent/dialect: specify none/light/strong; avoid caricature unless the script requires it
- emotional variation: what changes under fear, grief, anger, secrecy, command, or tenderness
- forbidden voices: AI narrator, broadcast announcer, idol youth voice, theatrical recitation, shouting, wrong age, wrong gender, random accent

Before every spoken line, repeat the relevant compact voice lock and performance state, then preserve the line verbatim.

Chinese example:

```text
音色锁：李侠=30多岁男声，中低音，清冷克制，气息偏浅但稳定，咬字清楚，语速3-4字/秒；紧张时音量不升高，只让尾音更短，禁止播音腔、偶像青年音、AI朗读腔。
李侠在压住眼泪、先吸气0.4秒后，用低而坚定的音色说：“只要我的工作对党有利，我义不容辞。”
```

English example:

```text
VOICE_LOCK: Li Xia = male voice in his 30s, mid-low pitch, cool restrained timbre, shallow but steady breath, clear articulation, 3-4 Chinese chars/sec; under tension his volume does not rise, only the line endings become shorter. Forbid announcer voice, idol-youth voice, AI narration, random accent.
Li Xia, holding back tears and inhaling 0.4s first, says in this locked low firm voice: “只要我的工作对党有利，我义不容辞。”
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

## Screen Direction + 180-Degree Axis Rule

For every dialogue, confrontation, chase, combat, entry, exit, or geography-critical segment, Seedance prompts must explicitly lock the 180-degree axis. This is mandatory because multi-reference video generation can otherwise flip screen direction between shots.

Write:

- the action axis: which two characters or path endpoints define it
- the safe camera side: which side of the axis all cameras stay on
- the fixed screen relationship: who remains screen-left/screen-right, which way they look, which way they exit
- the forbidden spatial drift: no axis crossing, no eyeline reversal, no flipped geography, no reversed exit direction
- the only allowed exception: a clearly motivated neutral-axis bridge shot or visible tracking move that crosses the line on-screen

Example:

```text
轴线锁：李侠与首长的连线为180度轴线，摄影机始终在观众侧同一半区；李侠保持画面左，首长保持画面右，过肩和反应镜头不反转眼线。李侠离开时沿画面右前方土路走，不得突然反向。禁止画面越轴、左右关系反转、眼线错位、出口方向反转。
```

English:

```text
Screen-direction lock: the line between Li Xia and the chief is the 180-degree axis; all cameras remain on the same audience-side half. Li Xia stays screen-left, the chief stays screen-right; OTS and reaction shots never reverse eyelines. Li Xia exits toward screen front-right along the dirt path, never the opposite direction. No axis crossing, reversed left/right relation, eyeline mismatch, or flipped exit direction.
```

## B-Roll + Reaction Rule

Use B-roll, inserts, reaction shots, and empty atmosphere when they make the scene more cinematic or more controllable. They should not be decorative. Each B-roll shot must have one job:

- preserve prop continuity, such as a suitcase handle, radio key, document, weapon, or hand position
- hold emotional reaction, such as listener eyes, swallowed breath, hand tightening, restrained nod
- create atmosphere and breath, such as wind, rain, dust, lamp flicker, empty road, distant landmark
- reset geography, such as doorway, road exit, river direction, corridor, stairs, window light
- bridge edits while keeping the same screen-direction axis

Keep B-roll inside the same scene geography and style. Do not introduce new locations, new props, readable text, or story facts unless the script requires them.

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
- axis drift: crossing the 180-degree line, reversed screen-left/screen-right relation, mismatched eyeline, flipped geography, reversed exit direction
- motion drift: floating camera, random slow motion, skipped action, impossible body physics
- edit drift: missing in/out frame, jump cut, merged shots, random extra shots
- text drift: subtitles, watermarks, UI, garbled labels unless required
- historical/domain drift: wrong era, wrong equipment, wrong uniforms, modern objects

## Chinese Dense Template

```text
参考图职责：
全片影像风格：直接写出色彩、对比、镜头、颗粒、光线、天气、摄影机气质、禁止风格漂移；每段都要按当前剧情重复并微调，不要暴露内部变量名。
@[STYLE_LOOK_SAFE] = 可选安全风格图：只控制色彩/光线/镜头/颗粒/质感；不得控制人物、服装、场景地理、道具、车辆、招牌、文字或剧情。
本段按顺序上传：@图片1=[板名/内容]；@图片2=[板名/内容]；@图片3=[板名/内容]。
@图片1（BOARD/CHAR_...）= 精确引用：写明哪个面板/标签/模块，以及忽略哪些同图内容。
@图片2（BOARD/SCENE_...）= 精确引用：写明哪个九视角/顶视图/机位标签、哪些入口出口/固定物/光源方向。
@图片3（BOARD/PROP_...或STORYBOARD_...）= 精确引用：写明道具细节图/手持状态，或当前故事板的TOP VIEW、CAMERA A/B/C、SHOT PANELS、LIGHT、SOUND/VFX和结尾帧。

生成[时长]秒[画幅]视频。本段只使用本段内部时间码，从0:00开始。整体保持[直接写出的项目风格内容]。本段情绪目标：[情绪目标]。起始状态：[上一段末帧或本段起点]。不要把混有人物/场景/道具/文字的总视觉圣经图当全局参考。
摄影系统：[ARRI/RED/Sony/Panasonic等具体机型]，[画幅/帧率/快门角度/镜头组/胶片颗粒/运动风格]。
轴线锁：[写清180度轴线、可用机位侧、固定左右关系、眼线方向、入口/出口方向、是否允许通过中性镜头换轴]。
音色锁：[按角色写清年龄音色、音高、音质、气息、音量、语速、咬字、口音、情绪变化和禁止错误声音]。

逐镜头时间线：
S01 / [0:00-0:xx] / [景别或B-roll/反应/空镜] / [焦段mm + 镜头高度 + 运镜]：[构图占位、人物动作、台词/画外音、音色锁调用、声音、光线、情绪、轴线/左右关系、入帧和出帧状态]。
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
Upload for this segment in order: @图片1=[board/content]; @图片2=[board/content]; @图片3=[board/content].
@图片1 (BOARD/CHAR_...) = exact reference: panel/label/module to read, and nearby content to ignore.
@图片2 (BOARD/SCENE_...) = exact reference: nine-view/top-plan/camera labels, entrances/exits, fixed objects, light direction.
@图片3 (BOARD/PROP_... or STORYBOARD_...) = exact reference: prop detail/hand state, or current storyboard TOP VIEW, CAMERA A/B/C, SHOT PANELS, LIGHT, SOUND/VFX, final frame.

Generate a [duration]-second [aspect ratio] video. Use local segment timecode only, starting at 0:00. Overall style: [directly written project look]. Emotional goal: [goal]. Start state: [previous final frame or segment opening]. Do not use any mixed visual-bible image containing people/scenes/props/text as a global Seedance reference.
Camera package: [specific ARRI/RED/Sony/Panasonic body], [format/frame rate/shutter angle/lens set/film grain/movement grammar].
Screen-direction lock: [write the 180-degree axis, safe camera side, fixed left/right relationship, eyeline direction, entrance/exit direction, and whether an axis-change bridge is allowed].
Voice lock: [write each speaking character's vocal age, pitch, timbre, breath, volume, speech rate, articulation, accent, emotional variation, and forbidden wrong voices].

SHOT TIMELINE:
S01 / [0:00-0:xx] / [shot size or B-roll/reaction/empty shot] / [focal length mm + camera height + move]: [composition, blocking, action, dialogue/VO with voice-lock callout, sound, light, emotion, axis/left-right relation, in-frame and out-frame state].
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
- Is the prompt detailed enough to approach the 5000-character budget without rambling?
- Does it include exact local timecodes?
- Does it include start and end states?
- Does the negative prompt cover likely failure modes for this specific project?
- Does the prompt forbid subtitles, on-screen text, control-board labels, random Chinese/English, and corrupted text?
