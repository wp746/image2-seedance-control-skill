# Image2 Seedance Control Skill

> v1.1.0 | 2026-05-12

一个面向 AI 视频创作者的 Image2 控制图 + Seedance 2.0 工业化生产 skill。

它不是简单帮你写一条视频提示词，而是把模糊创意、剧本、AI 真人剧单集、漫剧单集、广告脚本、已有角色/场景/道具资产，整理成 Seedance 2.0 能看懂的 **Image2 视觉控制图提示词文件**。

核心思路是：

```text
先用 GPT Image 2 生成资产板和故事板，
再把这些图作为 Seedance 2.0 全能参考，
让视频模型按图执行角色、场景、镜头、动作、台词、音效和连续性。
```

它适合 AI 真人剧、仿真人剧、AI 漫剧、创意短片、广告片、TVC、汽车/香水/美妆/服装大片、文旅片、MV、动作/VFX 短片，以及需要按集稳定生产的长线 AIGC 视频项目。

## Quick Start

如果你现在就要把这个 skill 交给 OpenClaw、Hermes、Codex 或其他智能体工具，用下面这组信息就够了。

安装仓库地址：

`https://github.com/wp746/image2-seedance-control-skill.git`

技能入口地址：

`https://raw.githubusercontent.com/wp746/image2-seedance-control-skill/main/SKILL.md`

压缩包地址：

`https://github.com/wp746/image2-seedance-control-skill/archive/refs/heads/main.zip`

推荐先看：

- [SKILL.md](SKILL.md)
- [提示词武器库索引](references/prompt-library-index.md)
- [项目连续性圣经 SOP](references/production-sop/project-continuity-bible.md)
- [镜头接缝审核 SOP](references/production-sop/shot-seam-review.md)
- [Seedance 返修 SOP](references/production-sop/seedance-repair-sop.md)
- [提示词自检清单](references/production-sop/prompt-self-review-checklist.md)

## 它能解决什么问题

这个 skill 主要解决 Image2 + Seedance 2.0 视频生产里的 10 个关键问题：

1. 用户只有模糊想法，不知道怎么补齐时长、画幅、风格、冲突和结尾。
2. 用户有剧本，但不知道如何拆成资产板和 Seedance 可执行故事板。
3. 角色资产和故事板混在一张图里，导致角色信息挤占镜头空间。
4. 角色脸、年龄、发型、服装在视频里漂移。
5. 场景空间、门窗、道路、桌椅、车辆位置在镜头间乱跳。
6. 道具、产品、车辆、手机、饰品在不同镜头里变形或换色。
7. Seedance 只收到一句抽象提示词，不知道每秒该拍什么。
8. 多镜头之间没有入点、出点、方向、声音和情绪接力，剪起来割裂。
9. 几分钟或分集项目没有项目级连续性圣经，越做越失控。
10. 出片后脸漂、动作错、运镜乱、接不上时，不知道该局部返修还是重做。

## 核心能力

### 1. 模糊创意需求澄清

当用户只说一句想法，比如“金刚大战哥斯拉”或“撒谎就变丑的销售”，skill 不会马上写提示词，而是先补齐生产关键项：

- 时长
- 画幅
- 类型
- 风格
- 角色与冲突
- 结尾方向
- 是否已有资产

如果用户不确定，会主动给出适合短视频生产的推荐方向。

### 2. 资产设计提示词

资产和故事板严格分离。

资产提示词用于生成：

- 角色资产板
- 单角色母版参考表
- 真人剧角色卡
- 夫妻/情侣角色参考表
- 儿童/地域文化角色卡
- UE5 / MetaHuman 技术角色表
- 场景连续性资产板
- 道具/产品/车辆资产板
- 风格/look bible

这些资产图后续会和故事板一起上传到 Seedance 2.0，作为全能参考。

### 3. 已有资产严格绑定

当用户已经有角色、场景、道具、产品、车辆或风格参考图时，这个 skill 不会把它们当成普通灵感图重新设计。

它会先做：

```text
用户原始资产 -> 可见特征提取 -> 正规资产连续性板 -> 资产编号 -> 故事板资产锁定
```

每个故事板都会明确引用：

- `CHAR_A`
- `SCENE_01`
- `PROP_PHONE`
- `VEHICLE_01`
- `PRODUCT_01`

并要求 Seedance 严格继承用户上传资产，不得重新设计。

### 4. Seedance 可读故事板

故事板不是海报，也不是 moodboard，而是给 Seedance 读取的视觉控制表。

每张故事板会写清：

- 镜头编号
- 秒级时间
- 景别
- 画面内容
- 角色动作
- 台词对白
- 拍摄手法
- 镜头参数
- 音效音乐
- 剪辑点
- 资产引用
- 连续性备注

15 秒以内的片段默认控制在 5-6 镜，复杂时最多 8 镜，避免故事板塞太满导致模型执行跑偏。

### 5. 多类型故事板武器库

内置多种故事板模式：

- 基础 Seedance 故事板控制图
- 传统表格式分镜控制图
- 资产锁定型 lookbook + 机位平面图 + 5 帧故事板
- 25-40 秒两段式电影分镜
- 动作/VFX/音乐时间轴预演板
- 16 格舞蹈/动作编排板
- 高端广告创意指导板
- 竖屏香水/美妆氛围广告板
- 体育高光动作板
- Smart Shot 电影导演总控板

### 6. 项目连续性圣经

针对几分钟、几十分钟、分集、系列化项目，skill 会建立项目级连续性控制：

- 角色关系
- 角色状态变化
- 场景空间
- 时间线
- 道具状态
- 风格/光线
- 声音/VFX
- 情绪递进
- 禁止漂移项

这样长项目不会每一段都像重新开了一部片。

### 7. 镜头接缝审核

每个镜头都必须定义：

```text
IN STATE -> ACTION -> OUT STATE -> NEXT SHOT HANDOFF
```

也就是：

- 上一镜最后一帧是什么
- 下一镜第一帧怎么接
- 人物站位是否一致
- 屏幕方向是否一致
- 道具在哪只手
- 情绪是否自然递进
- 光线和声音是否能接上

### 8. Seedance 返修 SOP

出片后如果出现问题，不会盲目重做整段，而是先诊断：

- 角色漂移
- 场景漂移
- 道具漂移
- 动作失败
- 运镜失败
- 情绪失败
- 光线/风格失败
- 镜头接缝失败

然后决定是提示词收紧、单段重生、故事板重写，还是资产板重建。

## 标准工作流

默认生产链路：

```text
Input Intake
-> 需求澄清 / 剧本分析
-> 项目连续性圣经
-> 资产提取与资产板提示词
-> 场景空间 / 道具 / 风格锁定
-> 分段故事板提示词
-> 镜头接缝检查
-> Seedance 2.0 全能参考生成
-> 出片后返修 SOP
```

关键原则：

- 没有资产，不直接做复杂视频。
- 资产和故事板分开生成。
- 已有资产必须作为最高优先级。
- 每个 Seedance 片段通常控制在 4-15 秒。
- 15 秒段落优先 5-6 镜，最多 8 镜。
- 长片按集、按场、按段拆分。
- 每段都要有上一段接点和下一段交接。

## 适用场景

适合这些需求：

- “我只有一个模糊想法，帮我做成 Image2 控制图提示词。”
- “我有 AI 真人剧剧本，先做第一集。”
- “我有角色、场景、道具资产图，帮我按资产生成故事板。”
- “我想做 9:16 竖屏短剧，拿图去 Seedance 生成视频。”
- “我想做汽车、香水、美妆、服装、产品广告大片。”
- “我想做一个 1-3 分钟创意短片。”
- “我想做按集生产的 AI 真人剧/漫剧。”
- “我生成的视频脸漂了，帮我写 Seedance 返修 prompt。”
- “帮我审核镜头接缝，保证剪起来不割裂。”

## 适用人群

适合这些人和团队：

- AI 视频创作者
- AI 真人剧创作者
- AI 短剧 / 漫剧团队
- AIGC 广告创作者
- 品牌短片导演
- 文旅片创作者
- MV / 舞蹈 / 动作短片创作者
- 使用 GPT Image 2 / Seedance 2.0 / 即梦 / 可灵等工具的创作者
- 想把 AI 视频从“碰运气出片”变成“可复用生产流程”的团队

## 仓库结构

仓库根目录就是 skill 根目录，已经可直接分发：

- `SKILL.md` — 技能入口文件
- `agents/openai.yaml` — Codex / OpenAI agent UI 元数据
- `references/prompt-library-index.md` — 提示词武器库索引
- `references/asset-prompts/` — 资产设计提示词分支
- `references/storyboard-prompts/` — 故事板提示词分支
- `references/seedance-prompts/` — Seedance 视频提示词分支
- `references/production-sop/` — 工业化生产 SOP 分支

### 资产提示词分支

- `character-design-sheet.md`
- `cinematic-character-card-generator.md`
- `master-character-reference-sheet.md`
- `couple-character-reference-sheet.md`
- `cultural-child-character-card.md`
- `simple-seedance-character-reference-sheet.md`
- `ue5-metahuman-technical-sheet.md`
- `animated-cinematic-character-pitch-board.md`

### 故事板提示词分支

- `storyboard-control-board.md`
- `traditional-storyboard-table-board.md`
- `asset-locked-lookbook-camera-storyboard.md`
- `smart-shot-directing-sheet.md`
- `cinematic-production-plan-sheet.md`
- `one-line-smartshot-storyboard.md`
- `two-part-cinematic-production-board.md`
- `integrated-15s-commercial-production-board.md`
- `previs-action-vfx-music-timeline.md`
- `luxury-ad-creative-direction-board.md`
- `infographic-8-shot-poster.md`
- `sixteen-panel-dance-choreography-board.md`
- `vertical-fragrance-mood-ad.md`
- `sports-highlight-sequence-board.md`

### Seedance 提示词分支

- `romantic-couple-introduction.md`
- `product-ad-timeline.md`
- `cinematic-production-sheet-timeline.md`
- `character-storyboard-first-pass-continuation.md`
- `named-reference-stack-action-prompt.md`

### 工业化 SOP 分支

- `project-continuity-bible.md`
- `shot-seam-review.md`
- `seedance-repair-sop.md`
- `prompt-self-review-checklist.md`

## 安装地址

如果 OpenClaw、Hermes、Codex 或其他智能体工具支持直接从 GitHub 仓库安装 skill，优先给它这个地址：

```text
https://github.com/wp746/image2-seedance-control-skill.git
```

也可以给它仓库页面地址：

```text
https://github.com/wp746/image2-seedance-control-skill
```

如果对方支持用原始入口文件识别 skill，可以给：

```text
https://raw.githubusercontent.com/wp746/image2-seedance-control-skill/main/SKILL.md
```

如果对方更适合下载压缩包安装，可以用：

```text
https://github.com/wp746/image2-seedance-control-skill/archive/refs/heads/main.zip
```

## OpenClaw / Hermes 使用建议

如果它们支持“从 Git 仓库安装 skill”，一般直接填仓库地址即可：

```text
https://github.com/wp746/image2-seedance-control-skill.git
```

如果它们支持“从 skill 入口文件识别”，就填：

```text
https://raw.githubusercontent.com/wp746/image2-seedance-control-skill/main/SKILL.md
```

如果它们支持“先导入仓库，再读取根目录 skill”，这个仓库本身已经是 skill 根目录，不需要再额外指定子路径。

## 怎么使用

### 1. 只有一个模糊想法

```text
请调用 image2-seedance-control-skill。

我想做一个 47 秒 16:9 好莱坞灾难片：
原创怪兽大战，结尾两败俱伤留悬念。
请先帮我补齐导演方案，
再输出 Image2 资产板提示词和故事板提示词。
```

### 2. 有 AI 真人剧剧本

```text
请调用 image2-seedance-control-skill。

这是我的 AI 真人剧第一集剧本。
请按 9:16 竖屏短剧规格，
先做项目连续性控制、角色/场景/道具资产提示词，
再按 4-15 秒分段输出 Seedance 可读故事板提示词。
```

### 3. 已经有角色、场景、道具资产

```text
请调用 image2-seedance-control-skill。

我已经上传了角色、场景和道具资产图。
请先把这些资产整理成正规的连续性资产板，
再严格按照这些资产生成故事板。
故事板只调度镜头、动作、台词、音效和节奏，不要重新设计资产。
```

### 4. 做高端广告 / 产品片

```text
请调用 image2-seedance-control-skill。

我要做一个 15 秒汽车广告。
我会提供车辆图、人物图和场景图。
请生成资产锁定型 lookbook + 机位平面图 + 5 帧故事板，
用于上传到 Seedance 2.0 生成视频。
```

### 5. 做 Seedance 返修

```text
请调用 image2-seedance-control-skill。

这是 Seedance 生成出来的视频问题：
第 2 段人物脸漂了，第三个镜头运镜乱，和上一段接不上。
请按 Seedance 返修 SOP 诊断问题，
输出局部返修提示词。
```

## 最终输出格式

这个 skill 默认输出一个 Markdown 文件，通常包含：

- Project Settings
- Director Recommendation
- Usage
- Production Control
- Asset Design Prompts
- Storyboard Prompts
- Shot Seam Checklist
- Seedance 最简输入句

默认文件名：

```text
image2_seedance_control_prompts.md
```

输出语言默认中文，方便创作者理解和复用；必要的镜头标签会保留英文，例如：

- `CLOSE-UP`
- `WIDE SHOT`
- `TRACKING`
- `OVER-THE-SHOULDER`
- `DO NOT CHANGE FACE`

## 和其他 skill 的关系

`aigc-asset-board-skill` 专注资产板设计。

`aigc-video-one-stop-skill` 是从资产到 Seedance 视频提示词的一站式流程。

`image2-seedance-control-skill` 专注 **先用 Image2 生成可视化控制图，再把图交给 Seedance 2.0 生成视频**。它更强调：

- 资产板与故事板分离
- 图像控制 Seedance
- 秒级故事板
- 镜头接缝
- 多段/分集连续性
- 出片后返修 SOP

推荐组合：

```text
aigc-asset-board-skill -> 稳定资产
image2-seedance-control-skill -> Image2 控制图 + Seedance 执行
aigc-video-one-stop-skill -> 更完整的一站式项目打包
```

## 当前状态

v1.1.0 | 2026-05-12

已沉淀多类真实案例方法，覆盖角色、场景、道具资产板、多种故事板模式、连续性圣经、接缝审核、返修 SOP 和提示词自检清单。

SKILL.md 已精简为调度器，完整模板详见 [提示词武器库索引](references/prompt-library-index.md)。

当前仓库已可作为 CodeBuddy / OpenClaw / Hermes / Codex 等智能体工具的独立 skill 安装使用。
