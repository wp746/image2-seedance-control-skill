# Visual Bible Reference Boundary SOP

Use this SOP whenever a project has a global visual bible, style bible, look board, mood board, film reference, or project-wide visual control image.

## Core Problem

Seedance treats uploaded images as visual references. If a "global visual bible" image contains characters, faces, scene geography, vehicles, props, maps, or readable text, Seedance may copy those elements into unrelated shots. This creates identity drift, scene confusion, prop contamination, and random text.

Therefore, a visual bible must be split by duty. A single rich board should not be used as a universal Seedance reference.

## Three-Layer Solution

### Layer 1. PROJECT_BOARD_SYSTEM

Controls board substrate, palette, typography, margins, arrows, labels, and diagram style.

Use as prompt text only.

Do not upload `PROJECT_BOARD_SYSTEM` boards to Seedance.

### Layer 2. STYLE_LOCK_TEXT

Controls the actual film look: palette, contrast, exposure, lens language, grain, light quality, haze/rain/smoke, camera mood, and forbidden style drift.

This is the primary global visual-control method for Seedance.

Required:

- Put a compact `STYLE_LOCK_TEXT` in Production Control.
- Repeat the relevant compact style lock inside every Seedance prompt.
- Adapt style lock by current scene: day/night, indoor/outdoor, rain/snow/dust, warm/cold light.

### Layer 3. STYLE_LOOK_SAFE

Optional image reference for style only.

A safe style image may contain:

- color swatches
- contrast strips
- exposure examples without recognizable story content
- lens/depth-of-field samples using abstract objects or cropped surfaces
- grain, haze, rain, smoke, dust, halation samples
- light direction diagrams
- material texture crops

A safe style image must not contain:

- recognizable faces or bodies
- named character silhouettes
- specific scene geography
- buildings that could become a location
- vehicles, weapons, hero props, uniforms, maps
- readable Chinese/English text
- camera floor plans or blocking diagrams
- story facts

If the style bible image contains people, places, vehicles, props, maps, or text, it is not safe as a global Seedance style reference.

## Classification Rule

Before referencing any visual bible image in Seedance, classify it:

| Image Type | Upload To Seedance? | Duty |
|---|---|---|
| `PROJECT_BOARD_SYSTEM` layout board | No | Prompt-only board formatting rule |
| `STYLE_LOCK_TEXT` | No image | Repeat text inside every Seedance prompt |
| `STYLE_LOOK_SAFE` abstract style card | Optional | Palette/lens/light/grain only |
| Scene asset board with real location views | Only for matching scene segments | Scene geography and light |
| Character asset board | Only when that character appears | Identity/body/wardrobe/performance |
| Prop board | Only when that prop appears | Prop shape/material/hand logic |
| Storyboard board | Only for current segment | Shot order/blocking/camera |
| Mixed global bible with characters/scenes/props/text | No global upload | Extract text style lock; split into separate assets |

## Seedance Reference Rule

Default Seedance reference stack should be:

```text
STYLE_LOCK_TEXT in prompt -> character board(s) actually appearing -> scene board for this exact scene -> prop board(s) actually used -> current storyboard -> previous final frame if continuing
```

Only add `STYLE_LOOK_SAFE` as an uploaded image if it is truly abstract and non-contaminating.

Never upload a scene bible, project bible, or visual bible globally if it shows people, vehicles, city streets, maps, weapons, or readable text.

## Prompt Reference Wording

When no style image is uploaded:

```text
STYLE_LOCK_TEXT controls the global look through words only: palette, contrast, lens, grain, light, weather, camera mood. Do not use any global style image as a story/content reference.
```

When a safe style image is uploaded:

```text
@[STYLE_LOOK_SAFE] = style only: palette, contrast, lens texture, grain, light quality, haze/rain/smoke. It must not control identity, wardrobe, scene geography, props, story facts, vehicles, signs, or text.
```

When a visual bible image is unsafe:

```text
Do not upload the mixed visual bible to Seedance. Extract its color/lens/light/grain into STYLE_LOCK_TEXT, then use separate character, scene, prop, and storyboard references.
```

## Image2 Prompt Injection For Style Cards

Chinese:

```text
这是 STYLE_LOOK_SAFE 安全风格卡，不是场景图、不是角色图、不是道具图、不是故事板。图中不得出现可识别人物、士兵、车辆、建筑地理、地图、武器、英雄道具、可读中文/英文。只允许色卡、光线方向、镜头质感、颗粒、雾/雨/烟/尘、材质裁切小样和抽象曝光对比。后续上传Seedance时它只控制色彩/光线/镜头/颗粒，不控制剧情内容。
```

English:

```text
This is a STYLE_LOOK_SAFE card, not a scene board, character board, prop board, or storyboard. Do not show recognizable people, soldiers, vehicles, specific geography, maps, weapons, hero props, or readable Chinese/English text. Only show color swatches, light direction, lens texture, grain, haze/rain/smoke/dust, material texture crops, and abstract exposure/contrast samples. If uploaded to Seedance later, it controls only palette, lighting, lens, and grain, never story content.
```

## Self Review

- Is the global style control primarily written as `STYLE_LOCK_TEXT`?
- Does every Seedance prompt repeat the relevant style lock?
- Is any uploaded style image free of people, scenes, props, vehicles, maps, and text?
- Are scene/location boards used only for matching scenes, not globally?
- Does every reference line state that style never controls identity, geography, props, story facts, vehicles, signs, or text?
