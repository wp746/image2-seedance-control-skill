# Style Look Bible Board Pattern

Use this when the user provides a style reference image/video/film look or asks to extract a visual style.

This board is a visual style contract. It is not a character board, scene board, or storyboard.

Important: a style/look board that contains people, faces, vehicles, buildings, scene geography, props, maps, or readable text is unsafe as a global Seedance reference. Use it to extract `STYLE_LOCK_TEXT`, or rebuild it as `STYLE_LOOK_SAFE`.

## Controls

- palette and color separation
- contrast and exposure bias
- lens family and depth-of-field tendency
- lighting quality, direction, ratio, color temperature
- texture: grain, halation, haze, bloom, dust, sharpness
- composition habits: negative space, symmetry, foreground occlusion, density
- camera mood and pacing tendency when based on video
- forbidden style drift

## Does Not Control

- character identity
- wardrobe structure
- scene geography
- prop shape
- plot facts
- subtitles or title cards
- readable signs, wall slogans, documents, maps, or prop text

## STYLE_LOOK_SAFE Requirement

If the board is intended to be uploaded to Seedance as a global style reference, it must be a safe style card:

- only color swatches, contrast strips, lens texture, grain, haze/rain/smoke/dust, light direction diagrams, and abstract material crops
- no recognizable people, soldiers, bodies, faces, vehicles, specific buildings, city geography, weapons, hero props, maps, or readable text
- no floor plans, camera blocking, scene labels, or story facts

If the project needs a beautiful visual bible with scene examples, keep it as an Image2/design reference only. Do not upload it globally to Seedance; repeat `STYLE_LOCK_TEXT` in each Seedance prompt instead.

## Reusable Image2 Prompt

```text
请根据用户提供的风格参考，创建一张 STYLE_LOOK_SAFE / 安全风格视觉圣经控制板，用于后续 Image2 资产板、故事板和 Seedance 2.0 视频提示词统一视觉风格。

这不是角色设定图、不是场景图、不是道具图、不是故事板。它只控制影像处理方式：色彩、光线、镜头、颗粒、构图、质感和节奏倾向。不得出现可识别人物、士兵、车辆、建筑地理、地图、武器、英雄道具、可读中文/英文。

画面必须包含：
1. PALETTE / 色彩：主色、辅色、点缀色、禁用色，使用色块和小样图表达。
2. CONTRAST / 曝光：高光滚降、阴影密度、黑位、是否欠曝或过曝。
3. LENS / 镜头：常用焦段、景深、畸变、焦外、边缘衰减。
4. LIGHT / 光线：主光方向、软硬、光比、色温、实际光源动机。
5. TEXTURE / 质感：胶片颗粒、雾气、尘埃、雨、噪点、锐度、晕光。
6. COMPOSITION / 构图：留白、前景遮挡、人物占比、画面密度、对称/不对称。
7. CAMERA MOOD / 摄影机气质：固定、手持、缓推、观察、压迫、疏离等，用抽象箭头和节奏条表达，不画具体人物调度。
8. REFERENCE DUTY / 参考职责：只控制色彩/光线/镜头/颗粒/质感，不控制人物、场景、道具、车辆、地图、文字或剧情。
9. FORBIDDEN DRIFT / 禁止漂移：不得改变人物身份、服装、场景地理、道具形状、车辆样式、文字内容或剧情事实。

所有文字使用短标签和大字号。不要长段文字，不要海报化，不要把角色/场景/道具设计混进风格板。若要做英文生产板，只允许英文标签和资产编号，不生成可读中文。
```
