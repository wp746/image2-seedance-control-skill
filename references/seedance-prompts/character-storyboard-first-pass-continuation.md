# Character Sheet + Storyboard First Pass And Continuation Pattern

Use this pattern when Seedance 2.0 needs to generate a cinematic action, fantasy, sci-fi, adventure, VFX, monster, or high-motion sequence from multiple visual references:

- character sheet
- location / environment sheet
- 3x3 storyboard or shot board
- optional last frame from a previous generated video

This pattern is especially important for 15-second segments that must later connect into 30 seconds, 60 seconds, or longer sequences.

## Core Intent

Do not feed Seedance a vague story and hope for continuity.

Use a reference hierarchy:

1. For the first pass, use the character/location sheet and 3x3 storyboard as strict visual references.
2. For the next segment, use the final frame of the previous 15-second video as the opening-state reference.
3. Keep the original character sheet and storyboard as secondary references so identity, costume, location, weapon, palette, and action logic do not drift.

## Best For

- cinematic sci-fi fight sequence
- two-character temporary alliance
- hero + rival versus monster / robot / guardian
- high-motion VFX action
- game cinematic trailer style
- multi-segment 15s + 15s continuation
- any scene where the user has generated an Image2 character/location sheet and a 3x3 storyboard board

## First-Pass Reference Priority

For seconds `0-15`, tell Seedance:

```text
Use the provided character/location sheet and the 3x3 storyboard as strict visual references.
Generate this as a 15-second first pass.
```

Reference responsibilities:

- character sheet: identity, face, body, costume, weapons, armor, color, silhouette
- location sheet: shared place, architecture, lighting, weather, floor material, atmosphere
- 3x3 storyboard: shot order, staging, action escalation, framing, camera rhythm, ending state

## Continuation Reference Priority

For a continuation segment, tell Seedance:

```text
本段本地时间 0:00-0:15。上一段末帧只负责本段 0:00 首帧姿态/站位/光线/情绪/道具状态。
原始角色/地点设定表仍是身份与空间最高源。
当前故事板负责本段镜头顺序和动作。
从上一段最后一帧无缝继续，不要重启故事。
```

Reference responsibilities:

- last frame: exact 0:00 starting pose, camera direction, location state, lighting, debris, water, smoke, VFX residue, character spacing, enemy condition
- original character sheet: highest identity and costume source
- original storyboard/current storyboard: keeps action logic and style consistent
- continuation prompt: defines what happens next, not a reset of the scene

## Prompt Anatomy

Use this structure:

1. `REFERENCE STACK`
2. `FORMAT / DURATION / GENRE`
3. `LOCATION LOCK`
4. `CHARACTER LOCK`
5. `ENEMY / OBJECT LOCK`
6. `SHOT SEQUENCE`
7. `VISUAL STYLE`
8. `CAMERA NOTES`
9. `DIALOGUE AUDIO`
10. `CONTINUITY RULES`
11. `FORBIDDEN DRIFT`

## First-Pass Reusable Seedance Prompt

```text
使用我上传的角色/地点设定表和 3x3 故事板作为严格视觉参考。先生成一个 15 秒首段视频。

[FORMAT / DURATION / GENRE]
电影级 [类型] 动作段落，15 秒，16:9，超高细节，电影预告片质感。

[REFERENCE STACK]
角色/地点设定表负责：角色身份、脸、体型、服装、武器、盔甲、颜色、轮廓、材质、地点结构、灯光和氛围。
3x3 故事板负责：镜头顺序、动作升级、构图、运镜节奏、角色站位、结尾画面状态。
必须严格使用这些参考，不得重新设计。

[LOCATION LOCK]
共同地点：[地点名称和描述]。保持完全一致的空间设定：[建筑结构、地面、水面/灰尘/雨雾/烟雾、灯光颜色、反射、背景层次、标识、天气、关键道具]。

[CHARACTER LOCK]
[CHARACTER_A]：[身份、服装、发型、颜色、武器、动作风格、VFX 颜色、站位关系]。
[CHARACTER_B]：[身份、服装、发型、颜色、武器/机械结构、动作风格、VFX 颜色、站位关系]。
两位角色的脸、身形、轮廓、武器、盔甲设计和颜色必须与角色设定表完全一致。

[ENEMY / OBJECT LOCK]
[敌人/怪物/机器人/关键物体]：[尺寸、材质、颜色、能量核心、动作方式、威胁感、破坏方式]。

[SHOT SEQUENCE]
1. 开场使用广角建立镜头，明确地点、角色左右站位、共同威胁和紧张关系。
2. 切到 [CHARACTER_A] 中近景，展示武器/能力启动，角色说一句短台词：[台词]。
3. 切到 [CHARACTER_B] 中近景，展示武器/机械结构/能力启动，角色回应：[台词]。
4. 敌人/威胁从环境中出现，水花/玻璃/灰尘/火花/霓虹/烟雾发生真实物理反应。
5. [CHARACTER_A] 率先攻击，动作轨迹和 VFX 颜色清晰可辨。
6. [CHARACTER_B] 从不同方向攻击，动作轨迹与 [CHARACTER_A] 的轨迹形成视觉对比。
7. 敌人反击，两位角色通过同步闪避、交叉走位或互补动作形成临时合作。
8. 两位角色短句交流，明确下一步目标：[台词 A] / [台词 B]。
9. 两位角色联合命中关键目标，能量/物理冲击汇聚，结尾停在一个可继续的强画面状态。

[VISUAL STYLE]
高端电影级 [科幻/奇幻/动作/灾难/怪兽/游戏预告] 质感，动态但可读的打斗，快速但清晰的动作，戏剧性运镜，适度手持，顺滑慢动作瞬间，体积光，雨雾/烟尘/水花/火花/碎片模拟，浅景深，清晰面部，可读轮廓，精致编舞，有重量的物理反馈，高级 VFX。

[CAMERA NOTES]
动作可以快，但必须读得清。保持每个角色的 VFX 颜色和运动轨迹有明显区分。镜头必须与 3x3 故事板一致，每个镜头都要连贯、电影感强、紧张、有方向。

[DIALOGUE AUDIO]
[CHARACTER_A]：[声线和情绪，例如沉稳自信的女声]。
[CHARACTER_B]：[声线和情绪，例如低沉锐利的女声]。
[敌人]：[只使用机械咆哮/怪物低吼/环境音，不说人话，除非剧情需要]。

[CONTINUITY RULES]
严格保持同一角色、同一地点、同一灯光、同一色彩逻辑、同一武器/VFX 设定、同一空间方向。
所有镜头必须按故事板顺序推进，不能跳过、合并、随机重排或重新设计。
结尾要保留明确的可续接状态：角色站位、敌人状态、环境破坏、光线、烟雾、水花、能量残留都要清楚。

[FORBIDDEN]
禁止换脸、换装、换武器、换场景、随机增加角色、改变左右关系、改变 VFX 颜色、忽略故事板、跳切割裂、动作不可读、画面文字、水印、字幕乱码、分屏、UI 元素。
```

## Continuation Reusable Seedance Prompt

```text
本段本地时间 0:00-0:15。使用上一段 15 秒视频的最后一帧作为 0:00 首帧姿态/站位/光线/情绪/道具状态参考。角色/地点设定表仍是身份与空间最高优先级参考，当前故事板负责本段镜头顺序和动作。

请从上一段视频最后一帧无缝继续，不要重新开场，不要重置角色站位，不要更换地点，不要改变光线、天气、破坏状态、烟雾、水花、火花、VFX 残留和角色相对距离。

[FORMAT / DURATION / GENRE]
继续生成 15 秒，16:9，电影级 [类型] 动作段落，必须与上一段视频同一场戏、同一风格、同一空间。

[STARTING STATE FROM LAST FRAME]
从上一段最后一帧继承：角色位置、姿势、朝向、武器状态、敌人受损状态、地面水花/灰尘/碎片、光线方向、背景建筑、烟雾/VFX 残留、镜头方向。

[CONTINUATION ACTION]
接下来发生：[本段 0:00-0:15 内的动作升级、反击、追击、二次危机、情绪转折或悬念]。

[CHARACTER LOCK]
继续保持 [CHARACTER_A] 和 [CHARACTER_B] 的脸、身形、服装、武器、VFX 颜色、动作风格和关系张力，与角色设定表完全一致。

[SHOT SEQUENCE 0:00-0:15]
S01/0:00-0:03：[从上一段结尾动作自然延续，不能跳切重启]
S02/0:03-0:06：[新的攻击/闪避/反击，保持空间方向]
S03/0:06-0:09：[角色互动、台词或战术变化]
S04/0:09-0:12：[冲突升级，敌人/环境产生真实物理反馈]
S05/0:12-0:15：[段落结尾，给下一段留下清晰可接的最后一帧]

[CAMERA NOTES]
延续上一段的镜头语言。可以更激烈，但必须读得清。保持角色运动方向、屏幕左右关系和镜头轴线稳定。不要突然切到陌生机位造成割裂。

[DIALOGUE AUDIO]
台词必须短，贴合动作节奏。声线延续上一段。

[FORBIDDEN]
禁止重新开始故事、重新建立场景、换脸、换衣、换武器、换场景、改变角色左右关系、改变敌人状态、忽略上一段最后一帧、VFX 颜色漂移、动作断裂、跳切割裂、画面文字、水印、字幕乱码。
```

## Why This Works

- The first pass uses boards to establish the world, identity, choreography, and ending state.
- The continuation pass uses the actual last frame as the strongest continuity anchor.
- Original sheets remain secondary references so the model does not slowly drift away from the design.
- Each 15-second segment ends with a deliberate handoff frame, which makes longer videos easier to stitch together.

## Production Rule

For long videos, repeat this cycle:

```text
asset sheet + storyboard -> local 0:00-0:15 first pass -> save last frame -> next local 0:00-0:15 continuation -> save last frame -> next local 0:00-0:15 continuation -> seam review -> edit
```

Before generating the next segment, identify the last frame's:

- character positions
- body direction
- eye line
- weapon / prop state
- enemy state
- environment damage
- lighting direction
- VFX residue
- smoke / water / dust / debris
- emotional state

Then write the continuation prompt from those exact facts.
