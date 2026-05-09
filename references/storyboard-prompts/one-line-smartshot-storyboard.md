# One-Line Smartshot Storyboard Pattern

Use this pattern when the user has only one short idea and wants to quickly create a detailed storyboard-style image, then use that storyboard to generate a video prompt.

This pattern is inspired by the Smartshot-style workflow: a single short prompt becomes a highly detailed storyboard image, and the video prompt is then built from that storyboard.

## Best For

- one-sentence cinematic ideas
- concept testing
- quick OpenArt Smartshot-style workflows
- mythic action, samurai, monk, monster, demon, fantasy, sci-fi, disaster, horror, sports, ad, travel, or product scenes
- users who want speed before a full industrial package
- turning a rough prompt into a readable 6-9 panel storyboard

## Core Method

Start with one short logline:

```text
A one-armed samurai monk confronts a towering [enemy] in [location] under [mood/light/weather].
```

Then expand it into a storyboard-style image with:

- title and genre
- character identity blocks
- environment block
- 6-9 numbered panels
- shot size and camera movement
- action progression
- emotion progression
- color and lighting notes
- final frame / continuation hook
- compact video prompt block

## Difference From Production Plan Sheet

Use `cinematic-production-plan-sheet.md` when you need floor plans, camera positions, and pre-production control.

Use this pattern when you need faster idea-to-storyboard conversion and a ready video prompt from one short sentence.

## Storyboard Layout

Recommended layout:

- 16:9 horizontal board or 4:5 vertical board depending on platform
- large title strip at top
- left side: compact character and environment locks
- center/right: 6-9 storyboard panels
- bottom strip: video prompt summary, camera style, palette, sound notes, forbidden drift

The storyboard should feel like a clear production storyboard, not a poster. Panels must be numbered and visually connected with arrows or timing labels.

## One-Line Expansion Rules

When expanding a short prompt, infer only what is needed:

- who is protagonist
- who or what is antagonist
- why the conflict starts
- where the scene happens
- how the action escalates
- what visual motif or VFX color controls the sequence
- what final frame makes the video feel complete or continued

Avoid overbuilding lore. The goal is a strong short scene, not a full screenplay.

## Reusable Image2 Prompt

```text
请把下面一句短创意扩展成一张高度详细、可直接指导视频生成的 storyboard-style image / 故事板风格控制图。

短创意：[ONE-LINE IDEA]

画幅：[16:9 / 9:16 / 4:5]
视频目标：[15 秒 / 30 秒 / 首段 15 秒]
类型：[电影级动作 / 武侠 / 黑暗奇幻 / 科幻 / 灾难 / 广告 / 文旅 / 运动 / 恐怖]

要求这张图不是海报，而是 Smartshot 风格的高细节故事板控制图。请包含：

1. TITLE / 标题：
[项目名 + 类型片标签]

2. CHARACTER LOCKS / 角色锁定：
主角：[身份、年龄感、体型、服装、武器/道具、动作气质、颜色/VFX、禁止变化项]
对手/威胁：[身份、体型、材质、能力、颜色/VFX、动作方式、威胁感、禁止变化项]

3. ENVIRONMENT LOCK / 场景锁定：
[地点、时间、天气、灯光、地面材质、背景层次、可互动道具、烟雾/水/火/灰尘/风/碎片等物理元素]

4. STORYBOARD PANELS / 分镜面板，共 [6-9] 格：
每一格必须有编号、时间、景别、运镜、画面内容、动作、情绪、VFX/物理反馈和出镜状态。
S01 / [时间] / [景别+运镜]：[建立地点、主角状态、冲突方向]
S02 / [时间] / [景别+运镜]：[威胁出现或压力升级]
S03 / [时间] / [景别+运镜]：[主角准备动作，武器/能力启动]
S04 / [时间] / [景别+运镜]：[第一次交锋]
S05 / [时间] / [景别+运镜]：[反击或环境变化]
S06 / [时间] / [景别+运镜]：[情绪或战术转折]
S07 / [时间] / [景别+运镜]：[高潮动作]
S08 / [时间] / [景别+运镜]：[冲击后果]
S09 / [时间] / [景别+运镜]：[最终画面或续集钩子]

5. CAMERA STYLE / 摄影风格：
[镜头语言、镜头速度、手持/推轨/摇臂/低角度/航拍/慢动作、镜头轴线和空间方向]

6. COLOR / LIGHT / VFX：
[主色、反差色、VFX 颜色、光源、反射、体积光、烟雾、水花、火花、灰尘]

7. READY VIDEO PROMPT / 可直接生成视频的摘要提示词：
用一小段文字总结：严格按故事板 S01-S09 顺序生成 [时长] 秒视频，保持角色、场景、武器、光线、VFX、动作方向和情绪递进一致。

8. FORBIDDEN DRIFT / 禁止漂移：
不得换脸、换装、换武器、换场景、改变左右关系、跳过分镜、合并分镜、随机加角色、文字水印、字幕乱码、UI、分屏。

视觉要求：每个面板画面清楚，人物和动作可读，文字短而大，箭头或时间标签清晰，最后一格必须适合作为 Seedance 下一段续接的最后一帧参考。
```

## Ready Seedance Handoff

After the Image2 storyboard is generated, use this compact Seedance instruction:

```text
严格参考上传的故事板图生成视频。故事板是最高优先级，按 S01-S09 的顺序、构图、动作、情绪、运镜和结尾状态执行。保持同一角色、同一场景、同一武器、同一光线、同一 VFX 颜色和同一空间方向。动作要快但清楚，每个镜头自然衔接，不得跳过、合并或重新设计故事板。
```

## When Not To Use

Avoid this pattern when:

- user already has a long script
- there are many recurring characters and locations
- strict floor plan and camera positions are required
- the project is an episode or industrial long-form production

For those, use the full pipeline: asset boards -> production bible -> storyboard segments -> Seedance prompts.
