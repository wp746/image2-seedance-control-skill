# Asset-Locked Lookbook Camera Storyboard Pattern

Use this pattern when the user provides existing character, product, vehicle, prop, scene, or style assets, and wants a Seedance-readable storyboard that strictly follows those assets.

This branch is distilled from a X reference by John (`john87445528`) showing a GPT Image 2 board built from uploaded assets: a female character reference, wardrobe/accessories, a purple vehicle, and a red-carpet/event location. The board combines asset references, location/camera planning, and a 5-frame storyboard in one premium production sheet.

Source: `https://x.com/john87445528/status/2048760792632205502`

## Best For

- 用户已经上传角色、场景、道具、车辆、产品资产
- 高端广告、汽车大片、时尚大片、红毯出场、产品发布、品牌短片
- 需要先展示资产引用，再做机位规划，再做分镜
- 需要 Seedance 严格继承上传资产，不重新设计人物、车辆、产品、道具或场景
- 8-15 秒单段镜头，尤其适合 5 帧出场、亮相、英雄镜头、离场结构

## Core Method

The board has three production sections:

1. `ASSET REFERENCE / 资产引用`
2. `LOCATION & CAMERA PLAN / 场景与机位规划`
3. `STORYBOARD / 分镜故事板`

This is different from a pure storyboard table. It deliberately keeps a small but clear asset reference area inside the board, so Seedance can see what the storyboard is locked to.

Important: this board does not replace formal asset design boards. If the user's assets are complex or long-term recurring assets, first create separate character/scene/prop asset boards. Then use this pattern as the asset-locked storyboard execution board.

## Input Asset Handling

Assign uploaded assets clear codes before writing the Image2 prompt:

- `CHAR_A`: main character
- `CHAR_B`: secondary character
- `PRODUCT_01`: hero product
- `VEHICLE_01`: vehicle
- `PROP_01`: hand prop or accessory
- `SCENE_01`: location
- `STYLE_REF_01`: look/style reference

The prompt must state:

```text
以用户上传资产图为最高优先级。所有人物、车辆、产品、配饰、场景和材质必须严格继承上传资产，不得重新设计，不得随机替换。
```

## Board Layout

Use a premium horizontal cinematic board, usually 16:9 or ultra-wide.

Recommended visual style:

- deep black / charcoal editorial background
- gold, purple, white, or project-matching accent lines
- clean high-end layout
- thin dividers
- large readable labels
- cinematic stills
- no dense tiny text

## Section 01: Character / Product / Vehicle Reference

Title example:

```text
01 角色与产品参考 / CHARACTER & PRODUCT REFERENCE
```

Show the user-provided assets as locked reference modules:

For character:

- front view
- side view
- back or 3/4 view
- face identity close-up if needed
- wardrobe shape and color

For product / vehicle / prop:

- full side view or main readable silhouette
- front or hero angle
- material / color / logo / distinctive feature
- accessory macro if relevant

For accessories:

- jewelry
- bag
- shoes
- watch
- weapon
- phone
- product packaging

Each reference module must have a compact asset code label:

```text
CHAR_A / uploaded reference
VEHICLE_01 / uploaded reference
PROP_EARRING / uploaded reference
```

Avoid random alternates. The board is not for redesign exploration.

## Section 02: Location & Camera Plan

Title example:

```text
02 场景与机位参考 / LOCATION & CAMERA PLAN
```

Split this section into two parts:

### Left: Location Reference

Show:

- one location atmosphere image
- time of day
- light direction
- background crowd or environment density if relevant
- set dressing
- color palette and surface texture

### Right: Top View Floor Plan

Use a readable top-down diagram.

Must include:

- space outline: stairs, plaza, corridor, road, room, stage, doorway, route
- character initial position
- character movement path with dotted arrows
- product/vehicle/prop anchor points
- 3-6 camera positions with labels
- camera direction arrows
- key frame area highlight
- simple legend

Camera labels should combine number and shooting method:

```text
CAM 1 / LS
CAM 2 / LOW
CAM 3 / 85mm
CAM 4 / WIDE
CAM 5 / TELE
```

## Section 03: Storyboard

Title example:

```text
03 分镜故事板 / STORYBOARD (5 FRAMES)
```

Use 5 frames by default. For direct Seedance execution, this is often enough for a premium 8-15 second sequence.

Each storyboard frame must include:

- frame number
- shot name
- shot size / lens
- image frame
- shot description
- camera label matching the floor plan
- continuity note

Recommended 5-frame premium entrance structure:

1. `WIDE SHOT / 建立与开启`: show location, product/vehicle/door/stage opening, atmosphere begins.
2. `LOW ANGLE / 出场动作`: show feet, fabric, object detail, product body, ground reflection.
3. `85mm CU / 身份特写`: show face, eyes, accessory sparkle, hand detail, product texture.
4. `HERO SHOT / 主体同框`: show character and product/vehicle/scene in one iconic composition.
5. `EXIT SHOT / 留白离场`: show door closing, tail light, object leaving, silhouette fading, final light trace.

For non-luxury projects, adapt the same logic:

- establish
- enter / approach
- detail / reaction
- hero / conflict / reveal
- exit / aftermath / hook

## Required Asset Lock Notes

Each storyboard frame should include one short lock note:

- `LOCK CHAR_A face + dress`
- `LOCK VEHICLE_01 color + shape`
- `LOCK SCENE_01 red carpet geometry`
- `LOCK PROP_01 hand position`

In Chinese boards:

```text
锁定：CHAR_A 脸与礼服；VEHICLE_01 车身颜色与轮廓；SCENE_01 红毯空间。
```

## Reusable Image2 Prompt Block

```text
请创建一张用于 Seedance 2.0 的资产锁定型故事板执行图。用户已经上传了资产图，本图必须严格继承用户资产，不是重新设计，不是海报，不是普通 moodboard。

项目：[PROJECT_NAME]
总时长：[DURATION]
画幅：[ASPECT_RATIO]
风格：[STYLE]
用户上传资产：
[ASSET_LIST_WITH_CODES]
段落目标：[SCENE_GOAL]

最高优先级规则：
以用户上传资产图为最高优先级。人物、车辆、产品、道具、配饰、场景、材质、颜色、比例、造型和视觉气质必须严格继承上传资产，不得重新设计，不得随机替换，不得脸漂移、服装漂移、产品漂移、车辆漂移、场景漂移或道具漂移。

整体版式：
生成一张 16:9 或超宽横版高级影视 production board，深黑色/炭黑背景，高端编辑排版，金色或项目主色细线分区，文字大而清楚，图像区域足够大，禁止小字密集。标题为：[BOARD_TITLE]。

第一区块：01 角色与产品参考 / CHARACTER & PRODUCT REFERENCE
把用户上传资产整理成锁定参考区。必须展示：
- CHAR_A：正面、侧面、背面或 3/4 视图，保持同一张脸、同一发型、同一服装、同一气质。
- PRODUCT_01 / VEHICLE_01 / PROP_01：完整侧面或主轮廓、正面或英雄角度、关键材质/颜色/标志性细节。
- ACCESSORIES / 配饰：如果有耳环、手包、鞋、手机、武器、包装等，做 1-2 个微距参考。
每个资产模块都标注资产编号，例如 CHAR_A / uploaded asset, VEHICLE_01 / uploaded asset。禁止生成随机替代版本。

第二区块：02 场景与机位参考 / LOCATION & CAMERA PLAN
左侧是 SCENE_01 场景环境参考图，展示时间、光线、背景、人群/空间密度、材质和氛围。
右侧是 TOP VIEW FLOOR PLAN / 空间俯视平面图，必须标出：
- 空间轮廓线：楼梯、广场、通道、道路、房间、门口或舞台
- 人物初始站位
- 人物移动路径，用虚线箭头表示
- 产品/车辆/道具锚点
- 3-6 个机位，标注 CAM 1 / LS, CAM 2 / LOW, CAM 3 / 85mm, CAM 4 / WIDE, CAM 5 / TELE
- 摄影机朝向箭头
- 核心构图区域高亮框
- 图例 LEGEND：人物起点、移动路径、机位、产品锚点、关键画面区域

第三区块：03 分镜故事板 / STORYBOARD (5 FRAMES)
生成 5 帧可直接执行的故事板，每一帧都要有编号、镜头名、景别/镜头、画面、镜头描述、机位、连续性锁定。
帧 1：建立与开启 / WIDE SHOT。展示地点、主体进入前的空间、产品/车辆/门/舞台开启或被看见。
帧 2：出场动作 / LOW ANGLE。低机位拍脚步、衣料、产品细节、地面倒影或关键动作起点。
帧 3：身份特写 / 85mm CU。展示脸、眼神、配饰闪光、手部细节或产品质感。
帧 4：主体同框 / HERO SHOT。人物与产品/车辆/场景形成标志性构图，背景虚化或高端光效强化主角。
帧 5：离场留白 / EXIT SHOT。主体离开、车门关闭、尾灯点亮、门缓缓合上、光轨或余韵留白。

每帧都必须写一条锁定说明：
锁定 CHAR_A 脸/服装/发型；锁定 PRODUCT_01 或 VEHICLE_01 的形状/颜色/材质；锁定 SCENE_01 空间结构/光线/背景。

最终效果要像高端广告或电影项目的执行级分镜板。Seedance 2.0 能从图中同时读到：资产长什么样、角色在哪里、机位在哪里、怎么运动、每一帧怎么拍、哪些东西绝对不能变。
```

## Seedance Input Sentence

After generating this board, use:

```text
请根据这张资产锁定型故事板生成连续视频。人物、车辆、产品、道具和场景以我上传的原始资产图与本故事板中的资产引用区为最高优先级，严格遵守 5 帧分镜、机位编号、移动路径、景别、动作、光影和连续性锁定，不要重新设计任何资产。
```

## When Not To Use

Avoid this pattern when:

- the user has no assets and only gives a vague idea; use `smart-shot-directing-sheet.md`.
- the project needs a pure row-based dialogue table; use `traditional-storyboard-table-board.md`.
- the project is an 8-scene luxury commercial without provided assets; use `luxury-ad-creative-direction-board.md`.
- the sequence is action choreography with body/VFX timing; use `previs-action-vfx-music-timeline.md`.
