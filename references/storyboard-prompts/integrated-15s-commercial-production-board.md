# Integrated 15s Commercial Production Board Pattern

Use this pattern when the user needs a compact 15-second commercial, animated short, regional product promo, food/drink ad, mascot ad, tourism-specialty ad, or kids/family branded short where one highly readable Image2 board can carry both light asset locks and a complete 5-shot timeline.

This pattern is distilled from one-page boards that combine:

- character / mascot / product asset references
- prop and environment design
- camera map
- palette and sound notes
- a 5-shot storyboard table with timecode, frame thumbnail, lens, movement, action, dialogue, sound, and emotion

## Best For

- 15-second commercials
- food, beverage, fruit, restaurant, snack, dessert, skincare, tourism-specialty, local product, seasonal product
- mascot-led ads and family/kids-friendly animation
- anime-style or stylized 3D brand shorts
- simple product reveal ads with one hero product and one protagonist
- fast social video, TVC, online video, platform ads

## Do Not Use When

- the script is longer than 20 seconds
- there are more than 2 recurring characters
- the character identity needs strict face continuity across many clips
- the scene geography is complex
- the user already has many separate asset images
- the project is AI真人剧, 漫剧单集, long-form drama, or multi-scene episode

In those cases, keep using the normal split workflow: asset boards first, then storyboard boards.

## Core Lesson

For short ads, the board should not be a beautiful poster. It should be a production sheet that Seedance can read.

The strongest layout is:

```text
LEFT 45-50%: asset and production controls
RIGHT 50-55%: 5-shot timeline table
BOTTOM STRIP: tone, target audience, format, duration, negative notes, version
```

The right side must have a strict 5-shot, 3-second-per-shot rhythm:

```text
S01 0:00-0:03 = hook / establish / sensory trigger
S02 0:03-0:06 = product or problem reveal
S03 0:06-0:09 = interaction / tasting / repair / emotional turn
S04 0:09-0:12 = hero reveal / delight / proof / scale
S05 0:12-0:15 = logo / slogan / final memory frame
```

## Visual Modules

Include these modules when relevant:

- `PROJECT TITLE / 项目标题`
- `15-SECOND COMMERCIAL / 15秒广告分镜脚本`
- `CHARACTER DESIGN REFERENCE / 角色设计参考`
- `PRODUCT / PROP DESIGN / 产品或道具设计`
- `ENVIRONMENT & SET DESIGN / 场景设计`
- `CAMERA MAP / 机位图`
- `COLOR PALETTE / 色彩方案`
- `SOUND DESIGN / 声音设定`
- `TONE & STYLE / 风格语气`
- `TARGET AUDIENCE / 目标受众`
- `NEGATIVE NOTES / 禁止事项`
- `SHOT TABLE / 分镜表`

## Shot Table Columns

Use clear large table headers:

```text
Shot # | Timecode | Frame Thumbnail | Camera/Lens | Shot Size | Movement | Action / Description | Dialogue / Subtitle | Sound / Music | Emotional Beat
```

For Chinese users, use bilingual headers:

```text
镜头# / Shot
时间 / Time
画面 / Frame
镜头 / Camera
动作 / Action
台词 / Dialogue
声音 / Sound
情绪 / Emotion
```

## Reusable Image2 Prompt

```text
请为下面这个 15 秒商业短片 / 动画广告 / 产品宣传片，生成一张横版 16:9 的一页式生产分镜控制图。

项目名称：[PROJECT_NAME]
产品/主题：[PRODUCT_OR_THEME]
目标受众：[TARGET_AUDIENCE]
风格：[STYLE，例如：清新自然真人广告 / 可爱儿童动画 / 日系手绘动画 / 赛博朋克动漫 / 高级商业摄影 / 文旅治愈短片]
核心卖点：[SELLING_POINT]
情绪路径：[EMOTION_ARC，例如：好奇 -> 惊喜 -> 喜爱 -> 满足 -> 记忆点]
画幅：[16:9 / 9:16]
总时长：15 秒

画面必须是 production board / storyboard sheet，不是海报。版式要求：

左侧 45%-50% 放资产与生产控制模块：

1. PROJECT TITLE / 项目标题
   大标题必须清楚显示项目名、15秒广告、画幅、风格标签。

2. CHARACTER DESIGN REFERENCE / 角色设计参考
   如果有角色或吉祥物，展示正面、侧面、背面或表情变化；必须锁定发型、服装、体型、颜色、标志性配件、表情基调。
   如果没有人物，就把这一栏改为 PRODUCT HERO / 产品主视觉，展示产品正面、侧面、剖面、包装、材质、比例。

3. PRODUCT / PROP DESIGN / 产品或道具设计
   展示产品/道具的关键细节：形状、材质、颜色、标签、包装、切面、质感、水珠、蒸汽、果肉、泡泡、光泽、磨损或手持比例。

4. ENVIRONMENT & SET DESIGN / 场景设计
   展示主场景宽景、局部场景、背景层次、光线方向、天气或季节、可互动空间。

5. CAMERA MAP / 机位图
   用俯视图或简化路线图标出 S01-S05 的机位位置、角色/产品运动方向、开始点和结束点。

6. COLOR PALETTE / 色彩方案
   展示 4-6 个色块，标注颜色名称和色值；颜色必须服务产品和情绪，不要单一色系。

7. SOUND DESIGN / 声音设定
   用小图标和短标签标出 2-4 个声音元素：环境声、产品声、音乐类型、品牌音效。

8. NEGATIVE NOTES / 禁止事项
   用简短大字写清：不要模糊、不要杂乱、不要换角色、不要改产品、不要多余人物、不要水印、不要乱码字幕。

右侧 50%-55% 放 5 镜头分镜表，每个镜头约 3 秒。表格必须清晰、整齐、可读，包含：

列名：Shot # / Timecode / Frame Thumbnail / Camera-Lens / Shot Size / Movement / Action-Description / Dialogue-Subtitle / Sound-Music / Emotional Beat

S01 0:00-0:03：
功能：开场钩子或环境建立。
画面：[建立产品世界、场景或人物注意力]
镜头：[镜头焦段、景别、运镜]
动作：[清楚的单一动作]
台词/字幕：[一句很短的台词或空]
声音：[环境声或开场音乐]
情绪：[好奇、清新、警报、期待等]

S02 0:03-0:06：
功能：产品/问题/欲望出现。
画面：[产品或冲突被看见]
镜头：[特写、推近、揭示]
动作：[角色靠近、发现、指向、打开、观察]
台词/字幕：[一句短句]
声音：[揭示音、泡泡、铃声、蒸汽、风、音乐节拍]
情绪：[惊喜、紧张、喜悦、警觉等]

S03 0:06-0:09：
功能：核心互动。
画面：[角色使用、品尝、修复、拥抱、奔跑、剥开、倒入、碰撞、变化]
镜头：[中景、跟拍、动态镜头]
动作：[必须能直接视频化]
台词/字幕：[一句短句]
声音：[产品细节声或动作声]
情绪：[投入、愉悦、专注、搞笑等]

S04 0:09-0:12：
功能：高潮 / 产品证明 / 情绪释放。
画面：[大杯出现、果肉爆汁、云朵恢复、门店亮灯、烟花绽放、角色满足]
镜头：[低角度、英雄镜头、摇臂、环绕或拉远]
动作：[视觉上最有记忆点的动作]
台词/字幕：[一句短句]
声音：[音乐上扬、品牌声、欢呼、泡泡、清脆音]
情绪：[满足、震撼、治愈、快乐]

S05 0:12-0:15：
功能：品牌收束与记忆点。
画面：[产品+Logo+Slogan，清楚干净，有最终定格]
镜头：[静态或轻微环绕，不要复杂]
动作：[产品稳定展示，角色微笑或场景完成]
台词/字幕：[品牌口号]
声音：[logo chime / 音乐收束]
情绪：[信任、记忆点、购买欲、温暖收尾]

底部横条必须包含：
Tone & Style / 风格语气：[一句话]
Target Audience / 目标受众：[一句话]
Platform / 平台：[TVC / Online Video / Social Media]
Runtime / 时长：15 seconds
Version / 版本：01

视觉要求：
整张图必须干净、像专业广告分镜表；所有文字大而短，不要小段密密麻麻；frame thumbnail 要真实表达每个镜头；角色、产品、场景、颜色、声音、情绪必须在 S01-S05 中连续一致；最后一格必须适合直接作为 Seedance 结尾定格和下一段续接参考。
```

## Seedance Handoff Prompt

Use this short instruction after the board is generated:

```text
严格参考上传的一页式广告生产分镜图生成 15 秒视频。左侧资产区负责锁定角色、产品、场景、色彩、声音和机位图；右侧分镜表负责锁定 S01-S05 的时间、画面、动作、镜头、台词、音效和情绪。请按 0:00-0:15 顺序连续生成，不得跳过、合并或重新设计镜头。保持同一角色、同一产品、同一场景、同一色彩风格、同一声音方向和同一情绪递进。最后 2 秒要清楚展示产品/Logo/Slogan，画面干净、有广告收束感。
```

## Why This Pattern Works

- The left side gives Seedance stable visual anchors.
- The right side gives Seedance precise temporal execution.
- The camera map prevents spatial confusion.
- The sound and emotion columns make ads feel directed instead of random.
- The final logo frame gives the clip a clean commercial endpoint.

