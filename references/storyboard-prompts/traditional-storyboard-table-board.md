# Traditional Storyboard Table Board Pattern

Use this pattern when the project needs a traditional storyboard sheet that Seedance 2.0 can follow with almost no extra prompt. It is especially useful for dialogue scenes, romance scenes, short drama moments, emotional beats, simple action beats, and any 8-15 second segment where the model should obey shot order, timing, shot size, camera movement, action, dialogue, sound, and music.

This pattern is distilled from a X reference by John AGI about using GPT Image 2 to generate a traditional storyboard image, then giving that image directly to Seedance 2.0 and writing only a short instruction such as “根据故事板分镜生成视频”. The author also confirmed in comments that a 15-second video works best with around 6 shots and should usually not exceed 8 shots.

Source: `https://x.com/johnAGI168/status/2050569545614553248`

## Best For

- 传统故事板分镜图
- 15 秒以内的真人剧、仿真人剧、恋爱、告白、对话、情绪反转
- 用户希望 Seedance 直接读图执行，而不是依赖复杂文字提示
- 每个镜头都需要清楚写明景别、运镜、画面动作、台词对白、音效音乐
- 用户已经有人物角色卡，需要把角色卡和分镜图一起上传给 Seedance 全能参考
- 用户有手绘分镜，也想转成更规整的 Image2 分镜表

## Core Idea

The board should look like a professional storyboard table, not an infographic poster.

Seedance should be able to read each row as:

```text
Shot number -> Time range -> Shot size -> Visual frame -> Camera movement -> Screen action -> Dialogue -> Sound/music -> Continuity note
```

The image should visually carry the production logic. The user should only need to upload the board and write:

```text
请根据这张故事板分镜生成连续视频，严格遵守镜头编号、时间、景别、运镜、画面动作、台词对白、音效音乐和人物一致性。
```

## Shot Count Rule

For direct Seedance execution:

- 8-10 seconds: 4-5 shots
- 12-15 seconds: 5-6 shots is the safest default
- 15 seconds maximum: usually do not exceed 8 shots
- 6 shots is often the best balance for clarity, rhythm, and execution stability

Use more than 8 rows only for planning overview, not for one Seedance generation segment.

## Board Layout

Use one horizontal production-board image.

Recommended structure:

- top title bar: project name, duration, aspect ratio, style, asset references
- large preview still or hero frame near the top: the emotional key frame or final look of the sequence
- lower main table: 5-8 numbered storyboard rows
- optional bottom footer: continuity lock, character reference requirement, Seedance input sentence, sound/music summary

The lower table is the core. It must be readable even if the top preview is visually attractive.

## Required Table Columns

Use short, large, readable labels. Bilingual labels are recommended:

- `SHOT / 镜头`
- `TIME / 时间`
- `SIZE / 景别`
- `FRAME / 画面`
- `CAMERA / 运镜`
- `ACTION / 动作`
- `LINE / 台词`
- `SOUND / 音效音乐`
- `NOTE / 连续性`

If space is limited, combine columns carefully:

- `SIZE + FRAME / 景别画面`
- `CAMERA + PARAM / 运镜参数`
- `LINE + SOUND / 台词声音`

Do not remove `SHOT`, `TIME`, `FRAME`, `CAMERA`, or `ACTION`.

## Row Design

Each row should contain:

- one large shot number
- exact time range, such as `0-2s`, `2-4s`, `4-6.5s`
- shot size: wide, medium, close-up, over-shoulder, insert, POV
- small visual thumbnail showing composition and character position
- camera movement icon or mini diagram: push-in, pull-back, pan, tilt, handheld, dolly, orbit, locked-off
- concise screen action: one action per row
- dialogue or subtitle intention, if any
- sound/music cue: heartbeat, footsteps, wind, low string, silence, impact hit, phone vibration
- continuity note: keep face, costume, prop, eyeline, position, lighting, or emotional state consistent

## Timing And Rhythm

Each row should represent one executable shot, not one vague story beat.

Recommended rhythm:

- Row 1: establish location, relationship, or immediate tension
- Row 2: first emotional or physical reaction
- Row 3: closer shot for eye contact, touch, clue, or decision
- Row 4: peak action, confession, reveal, hit, or turn
- Row 5: aftermath or emotional hold
- Row 6: ending frame or suspense hook

For romance/drama:

- begin with spatial relationship
- move into reaction close-ups
- use at least one tactile detail, such as hand, sleeve, phone, rain, breath, shoulder, door handle
- end on a held emotional frame

For action:

- begin with clear geography
- keep left/right direction consistent
- separate impact, reaction, and aftermath into different rows
- write physics and sound explicitly

## Asset Binding

The board should not repeat full character sheets. It should reference them by code:

- `CHAR_A`
- `CHAR_B`
- `SCENE_01`
- `PROP_RING`
- `PROP_PHONE`

At the top or bottom, write a compact asset reference line:

```text
ASSET REF / 参考资产：CHAR_A 男主, CHAR_B 女主, SCENE_01 夜晚巷道, PROP_PHONE 手机
```

If character consistency matters, add:

```text
人物一致性：上传人物角色卡作为参考；本故事板只控制镜头、动作、节奏和声音。
```

## Visual Style

Use the same visual style as the project:

- cinematic live-action realism
- AI真人剧真实质感
- romantic short drama
- Hollywood disaster film
- stylized 3D
- anime film
- product commercial

The table itself should remain clean and functional:

- dark slate or charcoal board with warm gold/white labels works well for cinematic scenes
- white/off-white production sheet works well for commercials and clean briefs
- high contrast labels
- no tiny text
- no decorative clutter
- no poster layout

## Reusable Image2 Prompt Block

```text
请创建一张适合 Seedance 2.0 直接读取的传统故事板分镜控制图，不是海报，不是角色资产图，而是一张专业影视分镜表。

项目：[PROJECT_NAME]
总时长：[DURATION]
画幅：[ASPECT_RATIO]
风格：[STYLE]
参考资产：[ASSET_CODES]
段落目标：[SCENE_GOAL]

画面采用横版 production board 构图。顶部放标题栏，写清项目名、总时长、画幅、风格、参考资产编号。上半部分可放 1 个较大的关键预览画面，展示本段最终影像质感、人物关系、场景光线和情绪基调。下半部分必须是清晰的传统分镜表格，表格才是核心。

分镜表格必须包含 5-6 个镜头行，若剧情确实复杂最多不超过 8 行。每一行都是一个 Seedance 可执行镜头，禁止把多个动作塞进同一行。

每一行必须包含以下字段，并使用大号可读标签：
SHOT / 镜头编号
TIME / 秒级时间
SIZE / 景别
FRAME / 画面缩略图
CAMERA / 运镜
ACTION / 画面动作
LINE / 台词对白
SOUND / 音效音乐
NOTE / 连续性

每个镜头行的画面缩略图要清楚显示角色站位、构图、视线方向、动作起点或终点。CAMERA 栏要用短文字和小图标说明运镜，例如 push-in, pull-back, pan, tilt, handheld, dolly, locked-off。ACTION 栏只写一个主要动作。LINE 栏写本镜头台词或“无对白”。SOUND 栏写心跳、脚步、风声、环境声、音乐进入、音乐停顿、冲击声等。NOTE 栏写人物一致性、服装、道具、左右方向、情绪承接、光线和场景连续性。

镜头数量节奏建议：
1 建立场景和人物关系
2 第一反应或靠近
3 眼神/触碰/关键道具特写
4 情绪爆点、告白、冲突、揭示或动作峰值
5 余波和情绪停顿
6 结尾留白或悬念帧

底部加入一条 Seedance 使用说明：
“上传本故事板与人物/场景/道具资产图，输入：请根据这张故事板分镜生成连续视频，严格遵守镜头编号、时间、景别、运镜、画面动作、台词对白、音效音乐和人物一致性。”

整体必须高对比、文字清楚、行列整齐、编号醒目、时间码准确、箭头方向明确、画面缩略图足够大。禁止小字密集、装饰海报化、镜头过多、时间不清、动作混乱、角色资产三视图挤进分镜表。
```

## Seedance Input Sentence

Use after the user generates this board image:

```text
请根据这张故事板分镜生成连续视频，严格遵守镜头编号、时间、景别、运镜、画面动作、台词对白、音效音乐和人物一致性。人物、场景、道具请参考我同时上传的资产图。
```

## Negative Requirements

- no poster-only composition
- no pure moodboard
- no missing time codes
- no vague action descriptions
- no more than 8 shots for a 15-second direct-generation segment
- no tiny unreadable table text
- no full character turnaround inside the storyboard area
- no inconsistent character face, costume, prop, eyeline, or position
- no unclear camera movement
- no multiple major actions in one row
