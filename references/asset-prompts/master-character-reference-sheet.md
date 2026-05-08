# Master Character Reference Sheet Pattern

Use this pattern when the project needs one clean, highly readable master character reference sheet for Seedance 2.0 identity control.

This branch is distilled from a single-character reference sheet method: the board is not a poster and not a beauty portrait. It is a technical visual bible whose main job is to let Image2 generate a stable character sheet, then let Seedance read the character's face, body, wardrobe, expression system, hand behavior, and optional prop without confusion.

## Best For

- 单人物角色母版参考表
- AI真人剧、仿真人剧、漫剧主角、短片主角
- 用户给一张参考图后，要保持同一个人连续出镜
- 用户只给文字角色设定，需要自动补全姓名、年龄、性格、身份、服装和视觉锚点
- 需要 Seedance 明确读取角色正面、侧面、背面、表情、头部角度、手势和道具
- 任意风格角色：真人电影感、写实 3D、风格化 3D、动画、二次元、黑色电影、定格动画等

## Use Instead Of Other Character Branches When

- Use this branch when the board must be clean, structured, and Seedance-readable above all else.
- Use `cinematic-character-card-generator.md` when the role needs a richer电影提案感、场景化肖像、服装材质戏剧性和人物心理说明。
- Use `character-design-sheet.md` when the role needs stronger导演美术设计感、怪兽/生物/大型角色或更艺术化的非对称排版。
- Use `ue5-metahuman-technical-sheet.md` when the role needs硬核技术转面、左右不对称锁定、装备/盔甲/硬表面部件、手脚和身体标尺精确控制。
- Use `simple-seedance-character-reference-sheet.md` when the role很简单，只需要快速锁定可爱角色、机器人、吉祥物或简单生物。

## Input Handling

The user may provide:

- text description only
- uploaded reference image
- uploaded reference image plus style conversion request
- a vague role such as “落魄侦探”“高中女生主角”“未来女战士”“怪兽片记者”

If using an uploaded image, preserve the identity first. The prompt may refer to it as:

```text
以用户上传的参考图作为角色身份主参考，严格保持同一个人的面部结构、年龄感、发型轮廓、五官比例、气质和可识别度。
```

If details are missing, infer them using film character logic:

- name or code
- alias
- role
- age range
- personality
- core theme
- speech accent or speaking style
- wardrobe details
- accessories
- one key prop if important
- visual identity notes
- 6-8 color palette swatches

## Board Format

Use a horizontal 4:3 board.

Layout requirements:

- clean white or off-white background
- minimal technical production-board style
- clear section titles
- readable labels
- balanced spacing
- no clutter
- no watermark, logo, poster typography, or decorative UI
- the selected visual style applies to the character artwork only, not to the board layout
- avoid tiny paragraphs inside the image; use short labels and compact notes
- Chinese labels are allowed, but short bilingual labels are often better for model readability, such as `MAIN IDENTITY / 主身份`, `SCALE / 比例`, `EXPRESSIONS / 表情`

## Required Layout Hierarchy

The board must make `MAIN IDENTITY + SCALE SHEET / 主身份与比例表` the largest and most visually dominant section.

Recommended layout:

- top left: title and compact character info block
- top right: 6-8 color palette swatches
- center and left-center: largest full-body identity and scale sheet
- right column: expression progression, head details, neutral baseline, posture variation, and one close-up pose
- bottom strip: wardrobe/accessory callouts, optional prop, and hand gestures

## Required Modules

### 1. Top Info Block

Include:

- Name / 姓名
- Alias / 代号
- Role / 角色功能
- Age / 年龄
- Personality / 性格
- Core Theme / 核心气质
- Speech Accent / 说话方式或口音

Keep it compact. Do not let text dominate the board.

### 2. Color Palette

Place in the top-right area.

Requirements:

- 6-8 clean swatches
- no long labels
- colors must match character wardrobe, skin/hair tone, props, and story tone

### 3. Main Identity + Scale Sheet

This is the biggest section.

Must include:

- full body front view
- full body 3/4 view
- full body side view
- full body back view
- height guide lines with clear marks
- consistent face, hair, body proportion, wardrobe, shoes, and accessory placement across all views
- no handheld prop in the main scale views unless it is permanently attached to the body
- no interaction pose in the main scale views

Add a small silhouette guide:

- neutral stance silhouette
- profile silhouette
- posture identity notes
- special trait notes

### 4. Expression Progression

Create exactly 8 expression panels:

- Neutral / 平静
- Curious / 好奇
- Worried / 担忧
- Surprised / 惊讶
- Afraid / 恐惧
- Sad / 悲伤
- Determined / 坚定
- Relieved / 释然

All panels must keep the same face structure, age impression, hairline, eye shape, nose, mouth, jaw, and skin tone.

### 5. Micro Expressions

Create exactly 5 micro-expression panels:

- subtle eye tension / 眼神绷紧
- slight smirk / 轻微笑意
- lip tension / 嘴唇紧张
- micro fear / 微弱恐惧
- controlled breath / 克制呼吸

These are for actor-like performance continuity. They should be subtle, not cartoon exaggerations.

### 6. Head Detail Sheet

Include:

- 3/4 headshot
- side headshot
- top angle
- low angle
- diagonal angle

The hairstyle, eye spacing, facial structure, and identity must remain locked from every angle.

### 7. Neutral Baseline

Include one relaxed, no-emotion baseline panel.

This panel is the default face Seedance should return to when no strong emotion is specified.

### 8. Posture Variation

Include 2-3 posture panels:

- relaxed
- tense
- confident

Posture should reveal personality and body rhythm, not just pose variety.

### 9. Cinematic Close-Up Pose

Include exactly one chest-up or shoulder-up cinematic close-up.

Requirements:

- shows facial identity clearly
- shows hairstyle clearly
- shows upper wardrobe clearly
- expression fits the story tone
- emotional presence is readable
- should feel like a still from the film or episode, but still inside the reference sheet

### 10. Wardrobe / Accessories Details

Include exactly 4 close-up callouts selected from:

- hairstyle detail
- outerwear structure
- footwear
- accessories
- fabric/material
- stitches, wear marks, stains, usage traces

Every close-up must reinforce continuity, not add random design variants.

### 11. Optional Prop

Only include a prop if it is important to the story or character identity.

If included:

- exactly 1 isolated prop image
- compact info block: Object Name, Type, Traits
- same prop must not change size, color, material, or wear pattern across later boards

If no prop is important, use the space for hands, wardrobe details, or silhouette notes.

### 12. Hand Gestures

Include:

- relaxed hand
- tense fingers
- pointing
- gripping
- subtle gesture near face

Hands must match the character's age, body type, job, and personality.

## Reusable Image2 Prompt Block

```text
请创建一张 4:3 横版 MASTER CHARACTER REFERENCE SHEET / 单角色母版参考表，用于 GPT Image 2 出图后上传到 Seedance 2.0 作为角色连续性参考。

角色风格：[STYLE]
角色描述：[SUBJECT_DESCRIPTION]

整体画面是干净、专业、极易读取的影视制作技术板：白色或暖白背景，清晰分区，短标签，大字号，可读文字，留白充足，不要海报感，不要杂乱装饰，不要水印，不要品牌 logo。风格只作用在角色绘制上，板式本身保持简洁技术图风格。

如果角色信息不完整，请自动补全姓名、代号、角色功能、年龄、性格、核心气质、说话方式、服装细节、配饰、关键道具、视觉锚点和 6-8 个色卡。

画面布局：
顶部左侧放角色标题和紧凑信息块：Name / Alias / Role / Age / Personality / Core Theme / Speech Accent。
顶部右侧放 6-8 个干净色卡，不要长文字。
中央最大区域放 MAIN IDENTITY + SCALE SHEET / 主身份与比例表，必须是全图最醒目的部分：完整展示正面、3/4 面、侧面、背面全身转面，带身高参考线，保持同一张脸、同一发型、同一体型、同一服装、同一鞋子、同一配饰位置。主比例区不要让角色手持道具，不要做互动动作。
主比例区角落加入 SILHOUETTE GUIDE / 剪影指南：中性站姿剪影、侧面剪影、姿态特征、小型视觉锚点说明。
右侧放 EXPRESSIONS / 表情递进，正好 8 格：Neutral, Curious, Worried, Surprised, Afraid, Sad, Determined, Relieved。所有表情都必须保持五官结构、年龄感、发际线、眼型、鼻子、嘴型、下颌和肤色一致。
右侧或下方加入 MICRO EXPRESSIONS / 微表情，正好 5 格：subtle eye tension, slight smirk, lip tension, micro fear, controlled breath。表演要真实克制，不能夸张卡通化。
加入 HEAD DETAIL SHEET / 头部角度表：3/4 headshot, side headshot, top angle, low angle, diagonal angle，保持同一身份。
加入 NEUTRAL BASELINE / 中性基准表情：1 格放松、无强情绪的默认脸。
加入 POSTURE VARIATION / 姿态变化：2-3 格 relaxed, tense, confident，体现角色性格和身体节奏。
加入 CINEMATIC CLOSE-UP / 电影近景：正好 1 格胸像或肩部以上近景，清楚展示脸、发型、上半身服装和情绪气质。
底部放 WARDROBE / ACCESSORIES DETAILS / 服装配饰细节，正好 4 个特写：从发型、外套结构、鞋子、配饰、布料材质、缝线、磨损、污渍中选择最重要的 4 个。
如果角色有关键道具，加入 PROP / 道具：正好 1 个孤立道具图，并配 Object Name / Type / Traits 小信息块；如果没有重要道具，就把空间留给手势或服装细节。
加入 HAND GESTURES / 手势表：relaxed hand, tense fingers, pointing, gripping, subtle gesture near face。

严格保持角色完全一致：同一张脸、同一年龄感、同一体型、同一发型、同一服装结构、同一配饰、同一视觉气质。禁止脸漂移、衣服随机变化、年龄变化、发型变化、身体比例变化、手指错误、额外肢体、模糊细节、文字过小。

最终效果应像高质量影视项目的角色连续性视觉圣经，Seedance 2.0 能直接从图中读取角色身份、比例、表情、头部角度、手势、服装和道具规则。
```

## Style Slot Examples

Use one style slot, then adapt to the project:

- cinematic realism / 电影写实
- live-action drama realism / 真人剧真实感
- stylized 3D animation / 风格化 3D 动画
- realistic 3D game cinematic / 写实 3D 游戏电影感
- anime feature film / 剧场版动画
- noir detective film / 黑色电影
- stop-motion miniature film / 定格动画

## Negative Requirements

- no poster layout
- no beauty photo sheet
- no tiny unreadable text
- no dense paragraphs
- no random costume variants
- no face drift between panels
- no inconsistent height or body proportion
- no mixed art styles inside the same character
- no extra props unless story-relevant
- no distorted hands
- no extra limbs
- no watermark
