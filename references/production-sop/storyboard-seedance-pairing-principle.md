# Storyboard-Seedance Pairing Principle

This is the master design philosophy for how Image2 storyboards and Seedance 2.0 text prompts work together. Every storyboard+prompt pair must follow this contract.

## Core Philosophy

```
故事板 = 把文字表达不精准的东西画出来
Seedance Prompt = 把图画不出来的东西写出来
```

They are **complementary, not redundant**. Each does what the other cannot.

## Division of Responsibility

### Storyboard's Job (Visual — 重图轻文)

The storyboard image visualizes what text cannot precisely express. Text on the board is minimal — logic labels, annotations, behavioral rules. The board IS the visual expression.

**Must visualize:**

1. **俯视动线图 / Top-Down Movement Diagram**
   - Character starting positions
   - Movement paths with directional arrows
   - Speed/timing marks on paths
   - Key blocking moments (stops, turns, interactions)
   - Camera positions numbered (CAM 1, CAM 2...)
   - Camera direction arrows and lens labels

2. **机位设置 / Camera Setup**
   - Each camera position on the floor plan
   - Shot size and lens choice per position
   - Camera height (eye-level, low, high, overhead)
   - Movement type (locked-off, dolly, handheld, crane, steadicam)
   - Movement path if camera moves

3. **灯光氛围说明 / Lighting Atmosphere**
   - Light source direction and quality (hard/soft)
   - Color temperature and gel notes
   - Key-to-fill ratio indication
   - Practical light sources in scene
   - Atmospheric elements (haze, dust, rain, smoke)
   - Light change cues (dimmer, flicker, practical switch)

4. **情绪关键词 / Emotion Keywords**
   - Emotional state per shot (large visible labels)
   - Emotional progression across the sequence
   - Micro-expression triggers (eye shift, lip twitch, breath change)
   - Tension/release mapping

5. **声音/特效标注 / Sound & VFX Annotations**
   - Sound cue positions on timeline
   - Music entry/exit points
   - VFX trigger frames and behavior
   - Sound bridges between shots

6. **逻辑标签 / Logic Labels**
   - Shot numbers and local timecodes
   - Asset codes (CHAR_A, SCENE_01, PROP_PHONE)
   - Shot size abbreviations (CU, MS, WS, OTS)
   - Edit type marks (CUT, DISSOLVE, MATCH CUT)
   - Continuity locks (LOCK FACE, KEEP HAND, MAINTAIN EYELINE)

7. **行为遵守 / Behavioral Rules**
   - What characters must always do
   - What characters must never do
   - Physical constraints (hand position, posture, walking speed)
   - Interaction rules (who touches what, eye contact rules)

**Keep text minimal.** Short labels only. Bilingual: `S03 / 0:04-0:07 / CU / 愤怒`. No paragraphs. No descriptions that belong in the Seedance prompt.

Dialogue belongs to sound and performance. Storyboards may show `低声命令`, `犹豫回答`, `RADIO VOICE`, or `PA SPEECH`, but should not place full dialogue paragraphs inside frame thumbnails. If exact dialogue is needed, write it in the Seedance prompt as spoken audio timing and explicitly forbid subtitles. See `dialogue-audio-subtitle-boundary.md`.

### Seedance Prompt's Job (Textual — 2000字符上限)

The Seedance prompt fills in everything the storyboard image cannot express. Stay under the 2000-character hard limit; prioritize clarity over density and do not try to use all available characters unless the segment truly needs it.

**Must describe (in detail the board only hints at):**

1. **微表情 / Micro-Expressions**
   - Eye movement: shifts, blinks, pupil dilation, gaze direction changes
   - Mouth: lip part, corner twitch, swallow, jaw tension
   - Brow: furrow depth, asymmetry, release timing
   - Breath: chest rise, nostril flare, held breath, exhale quality
   - Skin: sweat, flush, goosebumps, vein visibility

2. **运镜质感 / Camera Texture**
   - Handheld character: breathing rhythm, micro-jitter, operator personality
   - Dolly/slider: acceleration curve, settling at end, speed ramps
   - Focus: rack speed, breathing, depth character (not just "shallow")
   - Lens: distortion, flare character, edge falloff, bokeh shape
   - Sensor/film: grain structure, highlight rolloff, shadow character

3. **光线纹理 / Lighting Texture**
   - Quality: hard shadow edge transition, soft wrap gradient
   - Movement: flicker rhythm, practical dimming speed, cloud passing
   - Color: shift across frame, mixed temperature motivation, time-of-day logic
   - Practicals: lamp glow, candle flicker, neon buzz, phone screen

4. **声音设计 / Sound Design**
   - Room tone: size, surface, distance feel
   - Foley: footsteps material and weight, cloth rustle, breath
   - Ambience: wind, traffic, crowd, nature — distance and density
   - Music: entry point, genre, instrumentation, emotional function
   - Silence: where it falls, what it means

5. **表演节奏 / Performance Rhythm**
   - Timing of reactions (not instant, not delayed — motivated)
   - Beat spacing between lines
   - Physical business between dialogue
   - When stillness speaks louder than movement

6. **材质质感 / Material Texture**
   - Skin: pore visibility, oil sheen, age texture, not AI plastic
   - Fabric: weave, weight, drape, light interaction
   - Surfaces: patina, wear, dust, reflection character
   - Hair: strand behavior, light catch, movement physics

7. **电影级运镜 / Cinematic Camera**
   - Motivated movement: camera moves because story demands it, not because it can
   - No unmotivated orbits, no drone shots for drama's sake
   - Handheld = character POV or documentary feel, not random shake
   - Locked-off = tension, observation, judgment
   - Slow push = emotional intensification, not just "cinematic"

8. **连续性 / Continuity**
   - Previous segment out-frame state
   - This segment in-frame must match
   - Character physical state (wet, tired, injured, clean)
   - Prop state (in hand, on table, broken, charged)
   - Emotional carryover from previous beat

## The Non-Duplication Rule

| Information | Storyboard shows it? | Seedance prompt writes it? |
|---|---|---|
| Shot order and timing | ✅ Visual labels | ✅ Text timeline |
| Character position and movement | ✅ Floor plan + arrows | ✅ Describe nuance of movement |
| Camera position | ✅ Floor plan + CAM labels | ✅ Describe camera texture |
| Lighting direction | ✅ Light source arrows | ✅ Describe light quality and texture |
| Emotion | ✅ Keywords | ✅ Detail micro-expressions |
| Sound | ✅ Cue markers | ✅ Describe sound design |
| VFX | ✅ Trigger frames | ✅ Describe VFX behavior |
| Dialogue intention | ✅ Short intent note outside thumbnails | ✅ Write spoken delivery only when needed; never render as subtitles |
| Micro-expressions | ❌ Cannot show | ✅ Must describe fully |
| Texture/grain/patina | ❌ Cannot show | ✅ Must describe fully |
| Performance timing | ❌ Cannot show | ✅ Must describe fully |

## Film-Level Quality Standard

This is not "AI video." This is film. Every frame must avoid the AI look:

**Forbidden AI signatures:**
- Plastic skin, no pores, no texture
- Unmotivated camera movement (floating, orbiting)
- Instant emotion changes with no transition
- Over-smooth motion, no physical weight
- Generic "cinematic" lighting with no source motivation
- Characters that look at camera for no reason
- Over-saturated, over-sharp, HDR-heavy color
- Perfect symmetry, no human imperfection
- Dialogue sync that looks dubbed
- Random slow-motion for no narrative reason

**Required film signatures:**
- Skin with visible texture, pores, imperfections
- Motivated camera: every move has a story reason
- Emotional transitions: beat → reaction → new state
- Physical weight: gravity, inertia, effort
- Source-motivated light: practicals, windows, time-of-day logic
- Natural asymmetry and human imperfection
- Color science with character: film stock reference, not Instagram filter
- Performance with subtext: what's unsaid matters

## Rhythm-Driven Shot Count

Shot count is NEVER a formula. It is always rhythm and emotion.

```
情绪需要空间 → 少切，长镜头
情绪需要冲击 → 快切，短镜头
情绪需要审视 → 固定机位
情绪需要代入 → 手持
情绪需要压迫 → 推近
情绪需要释放 → 拉远
情绪需要孤独 → 广角远离
情绪需要亲密 → 长焦贴近
```

- **One continuous take** can express a complete emotional arc better than 8 cuts.
- **Two shots** — one wide, one close — can carry a scene if the performances are rich.
- **No shot minimum.** A single locked-off wide shot of a character sitting still for 8 seconds can be more powerful than a 6-shot action sequence.

The storyboard exists to serve the emotion, not to fill panels. Choose the minimum number of shots that carry the emotional weight. Add shots only when the story demands a new perspective.

## 2000-Character Hard Limit

**Seedance 2.0 accepts a maximum of 2000 characters per prompt. This is a HARD limit, not a target.** If you exceed it, the prompt will be truncated — losing critical continuity, micro-expression, or forbidden-drift instructions.

Recommended ranges:

- transition / B-roll: 400-800 characters
- dialogue / suspense / emotional drama: 900-1500 characters
- action / product / multi-reference segments: 1200-1800 characters
- only approach 2000 when complexity is justified and the segment budget remains safe

Before delivering any Seedance prompt, count the characters. If >2000, compress using the techniques below. Do NOT split the prompt — one prompt per segment.

### Compression Techniques

These are battlefield-tested techniques from real 11,000-char → 1,790-char compression (actual test: Rain Neon perfume ad).

**Technique 1: Merge reference stack into one line**

Before (198 chars):
```
参考图职责：
@[CHAR_A Asset Board] = CHAR_A 角色身份锁：脸、体型、比例、发型（湿发）、风衣...
@[SCENE_01 Asset Board] = SCENE_01 场景空间锁：窄巷四角度空间、建筑结构...
@[PROP_PERFUME Asset Board] = PROP_PERFUME 道具身份锁：方形玻璃瓶、金属盖...
@[Current Storyboard] = 当前故事板视觉控制图，负责俯视动线、机位设置...
```
After (89 chars, saved 55%):
```
@资产: CHAR_A板(脸/体型/湿发/风衣/疏离气质) SCENE_01板(四角度空间/建筑/光源) PROP_PERFUME板(方瓶/金属盖/琥珀液/雨滴/持握) 当前故事板(动线/机位/镜头顺序/情绪弧线/声效)
```

**Technique 2: Use symbols instead of connecting words**

| Before (冗长) | After (紧凑) | Saved |
|---|---|---|
| 不是直接闭眼——先看，瞳孔聚焦在手腕湿润处，0.5s 后眼睑开始闭合。闭合速度 0.3s（不是突然闭眼），闭合持续 1.2s。 | 低头看腕→0.5s后闭眼(速度0.3s时长1.2s)→ | 62% |
| 眉弓微降 1.5mm——不是痛苦，是沉浸。鼻翼轻微扩张（吸入）。 | 眉弓降1.5mm→鼻翼微扩→ | 57% |
| 步频从 1.2 降至 0.8 再至 0。停下不是突然的刹车——像被什么从侧面抓住了注意力。 | 步频1.2→0.8→0，停步位置井盖附近。 | 55% |
| 雨声从 -6dB 压低至 -9dB，霓虹嗡鸣过滤高次谐波只留 60Hz 基频 -14dB，形成"进入私密空间"的听觉收缩。 | 雨声-6→-9dB 霓虹去谐波只留60Hz-14dB(私密空间收缩) | 50% |

**Technique 3: Imperative fragments instead of full sentences**

Before: `CHAR_A 从画面下方撑透明伞走入窄巷。不是走秀——是凌晨1点独自回家的步态。步频 1.2步/秒，身体微前倾但不是赶路。`

After: `CHAR_A撑透明伞从下方走入窄巷，步频1.2步/s微前倾。`

**Technique 4: Move camera/light specs inline with shot header**

Before:
```
S01 / 0:00-0:06 / WS / 35mm / CAM 1 手持跟拍
CAM 1 在右侧距人物 3m，高度 1.6m 视线水平，操机者有轻微呼吸——画面有 2-3 像素的周期性微动...
```

After:
```
S01/0:00-0:06 WS/35mm/CAM1手持跟拍 高度1.6m 右侧30°。CAM1呼吸微动2-3px，偶尔滞后0.3s修正。
```

**Technique 5: Merge continuity and forbidden into compact form**

Before (12 lines):
```
连续性锁：
- CHAR_A: 同一张脸、同一体型、湿发状态贯穿全程...
- 风衣: 同款黑色哑光防水风衣...
```
After (2 lines):
```
连续:同脸/体型/湿发/风衣/伞贯穿全程，微表情递进(疏离→被吸引→私密→软化)幅度≤2mm。
禁止:换脸/换装/干发/改霓虹比/改天气/加人/加慢动作/AI塑料皮/浮游运镜/改4镜结构/加音乐
```

### What to Keep (Never Compress Away)

These are non-negotiable. If you're out of characters, cut description of background details before cutting these:

- Micro-expression timing and amplitude (眼睑1mm, 闭眼1.2s, 眉弓降1.5mm)
- Camera texture spec (呼吸微动2-3px, 偶尔滞后0.3s)
- Light quality and ratio (硬光边缘, 补光暗1.5档, 色温差)
- Key sound events with timing (瓶盖咔嗒, 喷洒50ms, 雨声-6→-9dB)
- Emotional arc keywords (疏离→被吸引→私密→软化)
- Forbidden drift list
- Asset codes and hand positions

### What to Cut First (Lowest Priority)

When you need characters, cut in this order:

1. Explanatory phrases (不是因为...而是... → delete)
2. Redundant scene description (already in storyboard image)
3. Second-level background details (distant car sound specifics unless plot-critical)
4. Emotion adjectives that repeat the emotion keyword
5. "Not X, but Y" constructions → just say Y

### The Rule

```
Every Seedance prompt MUST be ≤ 2000 characters.
Count before delivering.
If >2000: compress, don't split.
If still >2000 after compression: the segment has too many shots. Reduce shot count.
```

A weak prompt (wastes characters, AI-looking):
```
S01 0-3s: Character walks into room, looks around, sits down. Camera follows. Sad mood. Cinematic lighting.
```

A strong prompt (dense, film-level, 2000-char fit):
```
S01/0:00-0:03.2 WS/35mm/CAM2手持胸高 呼吸微动2px。CHAR_A左手推门，指节触木纹，门有阻力不轻不重。迈门槛右脚先落，体重转移在地板旧木上出声。0:45停步——眼球从左到右跳转(非扫视)，依次定格:窗(0:52)/空椅(1:10)/桌上照片(1:35)。微表情1:35:下唇收紧2mm→释放。屏息0.8s→鼻呼。走向椅4步每步不同木板呻吟。2:50坐下——控制下降非塌，手放大腿手指微蜷入布。
光:下午4时窗光画面右,4300K,薄纱柔化,尘粒可见光束中。影侧落至近黑，无补光。台灯灭。
声:房间音小空间木面，窗外远处车流。脚步旧皮鞋橡木每步不同，第三步轻咯吱。坐下时布摩擦。呼吸鼻息克制，坐下后一次深呼。无声乐。

## Revision to Existing Patterns

When loading any storyboard pattern from `references/storyboard-prompts/`, always apply this pairing principle on top. The pattern files provide structural templates. This file provides the quality and complementarity philosophy that overlays every template.

For the complete filmmaking quality standard across all 10 departments, see `references/production-sop/film-industry-master-checklist.md`.
