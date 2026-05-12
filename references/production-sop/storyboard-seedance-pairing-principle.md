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

**Keep text minimal.** Short labels only. Bilingual: `S03 / 4-7s / CU / 愤怒`. No paragraphs. No descriptions that belong in the Seedance prompt.

### Seedance Prompt's Job (Textual — 2000字符上限)

The Seedance prompt fills in everything the storyboard image cannot express. Use the full 2000-character limit for rich, nuanced text description.

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
| Dialogue intention | ✅ Short intent note | ❌ Write actual dialogue in prompt |
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

## Using the Full 2000 Characters

Seedance 2.0 accepts up to 2000 characters per prompt. Use them.

A weak prompt (wastes characters):
```
S01 0-3s: Character walks into room, looks around, sits down. Camera follows. Sad mood.
```

A strong prompt (uses characters for nuance):
```
S01 / 0:00-3:20:
CAM 2, 35mm, handheld at chest height, subtle operator breath rhythm, slight drift during stillness.
CHAR_A pushes door with left hand, fingers visible on wood grain. Door resistance felt — not light, not heavy. Steps over threshold — right foot first, weight shift audible on old floorboards. Pause at 0:45 — eyes scan room left to right, not panning, discrete saccades landing on: window (0:52), empty chair (1:10), photograph on table (1:35). Micro-expression at 1:35: lower lip tightens 2mm, releases. Breath held 0.8s at photograph, then exhale through nose. Walks to chair — 4 steps, each footfall distinct on wood. Sits at 2:50 — not collapse, controlled descent, hands rest on thighs, fingers curl slightly into fabric.
Light: 4pm winter window light from frame right, 4300K, soft through sheer curtain, dust motes visible in beam. Shadow side falloff to near-black, no fill light. Practical desk lamp off.
Sound: room tone — small room, wood surfaces, distant traffic through closed window. Footsteps — worn leather soles on oak, slight creak at third step. Cloth rustle when sitting. Breath — nasal, controlled, one deeper exhale after sitting. No music.
```

## Revision to Existing Patterns

When loading any storyboard pattern from `references/storyboard-prompts/`, always apply this pairing principle on top. The pattern files provide structural templates. This file provides the quality and complementarity philosophy that overlays every template.
