# Named Reference Stack Action Prompt Pattern

Use this pattern when a Seedance 2.0 prompt needs several uploaded references and each reference should have a clear job.

This pattern is distilled from a workflow where a creator uses a custom GPT to turn an image or concept into a storyboard, then sends the storyboard and identity references into Seedance. The key lesson is: do not say "use all images as references" vaguely. Give every reference a name and a responsibility.

## Best For

- action shorts with multiple characters
- hero vs villain / monk vs demon / warrior vs monster scenes
- fantasy, martial arts, mythic, sci-fi, cyberpunk, superhero, horror action
- projects using one storyboard image plus separate character identity sheets
- cases where Seedance confuses which reference controls story, identity, costume, or antagonist design

## Core Method

Define a named reference stack at the top of the Seedance prompt:

```text
References:
@[CurrentStoryboardRef] = storyboard and shot-flow guide.
@[HeroRef] = identity lock for [HERO_NAME].
@[VillainRef] = identity lock for [VILLAIN_NAME].
@[LocationRef] = environment and spatial design lock.
@[WeaponRef] = weapon / prop design lock.
```

Then state the priority:

1. Storyboard reference controls shot order, framing, camera rhythm, and action flow.
2. Character references control face, body, costume, silhouette, weapons, colors, and VFX identity.
3. Location reference controls environment, lighting, floor, background, atmosphere, and geography.
4. Prompt text controls the final motion, dialogue, pace, and emotional emphasis.

## Reference Rules

Use exact reference labels throughout the prompt.

Good:

```text
Follow @[CurrentStoryboardRef] for the shot order.
Keep @[HeroRef] as the only identity source for the hero.
Keep @[VillainRef] as the only identity source for the villain.
```

Avoid:

```text
Use these images as inspiration.
Make it like the references.
```

## Reusable Seedance Prompt

```text
Seedance 2.0 Prompt:

[REFERENCES / 参考图职责]
@[CurrentStoryboardRef] = 故事板和镜头流参考，只负责镜头顺序、构图、景别、运镜、动作节奏和段落结尾状态。
@[HeroRef] = [主角名] 的身份锁，只负责脸、体型、服装、武器、颜色、轮廓、材质、伤痕/纹身/特殊标记和动作气质。
@[VillainRef] = [反派名] 的身份锁，只负责反派脸、体型、服装/盔甲、颜色、轮廓、材质、武器、怪物特征或能量形态。
@[LocationRef] = 场景锁，只负责建筑/地形/地面/背景层次/光线/天气/烟雾/灰尘/水面/火光/空间方向。

优先级：严格按 @[CurrentStoryboardRef] 的镜头顺序和动作流生成；角色身份必须分别锁定到 @[HeroRef] 和 @[VillainRef]；场景空间必须锁定到 @[LocationRef]；本提示词只补充运动、节奏、台词、声音和情绪。

[FORMAT]
生成一个 [时长] 秒、[画幅]、电影级 [类型] 动作视频。风格：[视觉风格，例如 dark mythic action / cinematic martial arts / cyberpunk fight / game trailer quality]。

[STORY PREMISE]
[一句话写清楚冲突：谁在什么地方面对谁，为什么必须战斗，当前情绪是什么。]

[CHARACTER LOCK]
[HeroRef / 主角]：[主角身份、服装、武器、动作方式、能量颜色、情绪状态]。主角必须与 @[HeroRef] 完全一致，不得换脸、换衣、换武器或改变体型。
[VillainRef / 反派]：[反派身份、服装/盔甲、武器/能力、动作方式、能量颜色、威胁感]。反派必须与 @[VillainRef] 完全一致，不得重新设计。

[LOCATION LOCK]
场景必须与 @[LocationRef] 完全一致：[地点名、时间、天气、灯光颜色、地面材质、背景结构、烟雾/水花/火花/灰尘/VFX 残留]。不得随机换地点或改变空间方向。

[SHOT FLOW]
严格按照 @[CurrentStoryboardRef] 的镜头顺序执行：
S01：[开场镜头，建立地点、人物站位、冲突方向]
S02：[主角动作或准备]
S03：[反派动作或威胁升级]
S04：[第一次碰撞/闪避/追击]
S05：[动作升级，环境产生物理反馈]
S06：[关键对抗，角色情绪变化]
S07：[短台词或战术变化]
S08：[最终冲击或反转]
S09：[结尾状态，保留可续接最后一帧]

[CAMERA AND MOTION]
动作要快但清楚。镜头要跟随故事板，不得乱跳机位。保持角色左右关系、运动方向、眼线、武器轨迹和 VFX 颜色可读。每次攻击都要有准备、接触、冲击反馈和余波。

[AUDIO / DIALOGUE]
台词必须短，贴合动作节奏：
[主角台词]：[一句]
[反派台词]：[一句]
音效：[武器、脚步、布料、金属、能量、撞击、环境声]

[CONTINUITY RULES]
严格保持参考图身份、服装、武器、场景、光线、色彩、VFX、空间关系和故事板顺序。每个镜头的出镜状态必须自然衔接下一镜头的入镜状态。

[FORBIDDEN]
禁止把所有参考图混成一个角色；禁止主角和反派脸互换；禁止改变服装、武器、颜色、VFX；禁止跳过故事板；禁止随机增加角色；禁止换场景；禁止画面文字、水印、字幕乱码、UI、分屏。
```

## Use With Existing Templates

Use this together with:

- `character-storyboard-first-pass-continuation.md` when the video is part of a longer 15s + 15s sequence.
- `cinematic-production-sheet-timeline.md` when the storyboard is a full cinematic production sheet.
- `seedance-repair-sop.md` if one reference dominates incorrectly or characters mix together.

## Why This Works

Seedance handles multiple references better when each image has a single duty. Named references reduce ambiguity:

- storyboard image = motion and shot flow
- hero image = hero identity
- villain image = villain identity
- location image = spatial and lighting continuity

This prevents common failures such as face mixing, costume drift, wrong antagonist design, scene replacement, and random action order.
