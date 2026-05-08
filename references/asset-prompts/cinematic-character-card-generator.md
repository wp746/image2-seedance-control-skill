# Cinematic Character Card Generator Pattern

Use this pattern when the user wants a high-detail Image2 character card from text, an uploaded person photo, or a photo plus transformation request.

This pattern is especially useful for AI live-action drama and multi-character scenes because it emphasizes height, body scale, identity preservation, costume logic, and professional production notes.

## Best For

- AI真人剧人物角色卡
- 仿真人剧角色定型
- 用户上传照片后改造成某类角色
- 多人场景需要身高比例控制
- 需要导演、选角、服装、动画、AI视频团队共同使用的角色板
- 需要从模糊人物描述自动补全完整角色资料

## Input Handling

The user may provide:

- pure text description
- uploaded character/person photo
- photo plus modification request
- multi-condition role customization: name, age, height, job, wardrobe, prop, psychology, film genre, era, scene mood

When information is incomplete:

- auto-complete reasonable details using film character design logic
- ask only once if core identity is missing, such as gender/age range/role direction
- do not repeatedly question the user

## Core Design Principles

The output character card should feel like a high-budget film development board, not a generic AI portrait or simple model sheet.

Must prioritize:

- cinematic production quality
- art-directed asymmetric composition
- actor-like realism
- micro-expression and transitional emotion
- strict identity consistency across all views
- height and scale clarity
- costume/material logic
- concise professional production notes

Avoid:

- ordinary equal grid
- mechanical symmetry
- copied pose repetition
- stiff front-facing model pose
- random pretty clothing
- face drift between views
- costume drift
- plastic-looking fabric
- text overload

## Required Modules

### 1. Title / Identity Area

Include:

- character name
- alias or code
- age
- height
- body type
- occupation/role
- design style keywords

Use a small amount of English design-board text. Keep it readable and not dominant.

### 2. Full Body Turnaround

Must include:

- full body front view
- full body 3/4 front view
- full body side view
- full body back view
- full body 3/4 back view

All views must preserve:

- same face identity
- same height/body proportion
- same clothing structure
- same shoes
- same accessories
- same prop placement

### 3. Head And Expression Study

Must include:

- front neutral expression
- 3/4 primary personality expression
- side structure
- looking-down thinking expression
- looking-up alert expression
- dynamic intense emotional angle

Expressions should feel cinematic and mid-thought, not meme-like or exaggerated.

### 4. Cinematic Portrait

Include one larger half-body or bust portrait that shows the character's core aura.

Use:

- meaningful environment tied to character
- 50mm or 85mm lens feel
- shallow depth of field
- practical cinematic lighting
- strong emotional readability

### 5. Wardrobe And Material Breakdown

Show:

- main outfit
- inner layer
- trousers/skirt
- shoes
- accessories
- prop
- material close-ups
- stitching
- wrinkles
- wear marks
- stains/aging/usage marks

Clothing must reflect role, job, personality, living condition, and film genre.

### 6. Height Scale

Must include a clean height scale beside the character.

If user provides height, use it exactly.

If no height is provided, infer height from age, role, body type, and story function.

Height is especially important for multi-character AI video scenes.

### 7. Production Notes

Use concise, professional notes:

- facial identity anchors
- costume structure
- behavior habits
- key prop meaning
- color logic
- continuity notes

Notes should feel like film art department production notes, not long essays.

## Internal Analysis Checklist

Before writing the Image2 prompt, internally determine:

- identity: name, age, gender, height, body type, cultural/design language, job, role background
- face design: face shape, bone structure, facial proportions, eyes, nose, lips, jaw, skin, hair, unique marks
- psychology: 3-5 core traits, internal conflict, behavior habits, emotional baseline, emotion-change speed
- performance: posture, motion rhythm, hand habits, eye behavior, walking rhythm, idle body state
- wardrobe logic: why each clothing item, accessory, and prop belongs to this character
- visual style: user-specified style or default semi-realistic cinematic animated film design

## Uploaded Photo Rule

When the user provides a photo:

- use the uploaded image as the primary identity reference
- preserve facial identity, facial structure, eye shape, nose, mouth, jawline, age impression, skin tone, expression quality, and recognizability
- allow changes to wardrobe, occupation, scene, style, hair, and props only when requested
- do not change age, ethnicity, face shape, or core aura unless explicitly requested
- if multiple photos are provided, extract stable common identity features and ignore accidental lighting/expression/angle differences

Use strong identity language:

```text
STRICT IDENTITY PRESERVATION. The same person must be recognizable in every view and portrait. No facial drift across angles.
```

## Reusable Instruction Block

```text
创建一张电影制作级人物角色卡，供导演、选角团队、服装部门、动画制作团队和 AI 视频团队使用。画面必须像高预算电影项目提案级角色设计板，而不是普通 AI 写真、证件照、海报或通用模型表。

角色必须像真实演员在叙事瞬间被捕捉到：包含微表情、嘴角张力、眼神轻微偏移、眉毛变化、下颌紧张感、呼吸感、过渡情绪和自然不对称身体语言。

构图必须有艺术指导感：禁止普通等距网格、机械对称和复制粘贴式平均摆放。使用轻微不对称、主次关系、留白层次、视觉节奏和专业电影美术部门的 production notes。

必须包含：角色标题区、全身正面/3-4正面/侧面/背面/3-4背面、头部表情研究、大幅电影肖像、服装材质分解、身高比例尺、专业注释、色卡和连续性锁定。
```

## Default Style

If the user does not specify style, use:

```text
semi-realistic cinematic animated film character design, premium studio pitch board, stylized realism, soft geometry, cinematic lighting, high emotional readability
```

## Negative Requirements

Use these when relevant:

- no generic model sheet
- no evenly spaced grid
- no random clothing changes
- no face drift
- no inconsistent proportions
- no lifeless symmetrical posing
- no plastic fabric
- no cheap cosplay look
- no blurry details
- no distorted hands
- no extra limbs
- no duplicated faces with different identity
- no text overload
- no messy layout
- no low-budget concept art

## When To Use With Other Branches

Combine with `character-design-sheet.md` when performance, psychology, and director-facing role identity matter.

Combine with `ue5-metahuman-technical-sheet.md` when exact technical multi-view consistency, body landmarks, hands/feet, groom, armor, or asymmetry matter.
