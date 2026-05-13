# Prompt Self-Review Checklist

Use this before delivering any Image2 prompt file. Audit and fix against every rule.

## 1. Responsibility Separation

- Character boards lock identity, face, body, wardrobe, expressions, and status variants.
- Scene boards lock space, light, material, geography, and usable camera areas.
- Prop/UI boards lock object shape, usage, hand relationship, and short readable text.
- Storyboard boards lock shot order, timing, staging, camera, action, dialogue intention, and handoff.

Do not let one board accidentally perform another board's job unless the chosen reference pattern explicitly requires an integrated board.

## 2. No Accidental Identity Sources

Scene boards should not show clear main-character faces unless the board is intentionally asset-locked. Use empty locations, distant passersby, silhouettes, or placeholders for scale.

## 3. Storyboard as Execution Board

Check that the storyboard focuses on props, scene, camera map, placeholders, palette, sound, VFX, notes, and shot table. It should not contain detailed character turnarounds, facial identity studies, wardrobe breakdowns, or competing character designs when separate asset boards exist.

## 4. UI and Text Control

If exact text matters, keep it short, large, and isolated. Do not ask Image2 to recreate complex app interfaces with many small labels. Prefer a separate UI/prop board for phone screens, signs, documents, chat messages, contracts, brand slogans, and curse rules.

For narrative footage, the final Seedance frame must be clean. Storyboard labels, `S01/S02/S03`, timecodes, dialogue lines, camera notes, arrows, subtitles, captions, and production annotations are control-board information only. They must never be rendered into the video image.

Every narrative Seedance prompt must include a clean-frame negative line:

```text
纯净电影画面；不要字幕、不要标题、不要画面内文字、不要 S01/S02/S03 分镜编号、不要 UI、不要水印、不要随机中文/英文、不要乱码文字。
```

If the project uses Chinese board labels, verify that they are Simplified Chinese unless the user explicitly requested Traditional Chinese.

## 5. Specific but Not Over-Constrained

Lock non-negotiables: identity, wardrobe, scene geography, prop shape, UI text, story order, start/end state, and forbidden drift. Leave creative room for lighting texture, performance nuance, natural background detail, and cinematic composition.

## 6. Logical Consistency

Check that every asset code used in storyboards exists. Check that every Seedance prompt references the same asset names as the storyboard. Check that character state changes happen in the right order and are not introduced early.

## 7. Segment Timecode + Character Limit

For Seedance generation segments, verify every storyboard and matching Seedance prompt starts at `0:00` and ends at or before `0:15`. Do not use cumulative episode timestamps inside segment prompts.

**Seedance prompt MUST be ≤ 2000 characters.** This is a hard limit — if exceeded, Seedance 2.0 will truncate the prompt. Count characters before delivering. If >2000, compress using the techniques in `storyboard-seedance-pairing-principle.md` (merge reference stack, symbols over connecting words, imperative fragments, inline specs). If compression still fails, reduce shot count — the segment has too many shots to describe with quality.

## 8. Shot Count and Rhythm

Shot count is driven by emotion, not formula. One continuous take can carry a scene. Two shots — one wide, one close — can be enough. Check that every shot has an emotional reason to exist; remove shots added just to fill panels. Use rhythm logic: space needs fewer cuts, impact needs more cuts, stillness needs locked-off camera, immersion needs handheld.

For 15-second dramatic segments, fail the prompt if it tries to solve a slow emotional beat with fast coverage. Use this gate:

- waiting / fear / command hesitation / grief / moral pressure: 1-3 shots, long holds, visible breath
- dialogue / interrogation / order delivery: 2-4 shots, let the line land before cutting
- attack / impact / chaos: 4-7 shots only when the script calls for acceleration
- if more than 5 shots are needed to tell the beat clearly, split into multiple Seedance segments instead of cramming

Do not add shots to "fill 15 seconds." A one-shot 15-second segment is valid when the emotion is alive.

## 9. Storyboard/Seedance Mirror Check

For every storyboard shot row, verify the matching Seedance prompt has the same shot number, local timecode, main content, camera/movement, character action, dialogue, sound/music, emotion, VFX, and end-state logic. Remove anything in the Seedance prompt that is not supported by the storyboard.

## 10. Production Readability

Remove contradictory instructions, repeated labels, dense tiny paragraphs, and vague commands such as "make it cinematic" without execution detail. Each prompt should be clear enough that another agent can use it without asking what you meant.

## 11. Film Industry Master Checklist

Before final delivery, run through the `film-industry-master-checklist.md` — 10 departments, 40+ items. Mark each as satisfied or N/A with reason. At minimum, verify these high-risk items:

- Model capability boundary: can Seedance actually execute what we're asking?
- Color constitution declared: main/secondary/accent/neutral/forbidden colors
- Film stock color science declared
- Every camera movement has a story motivation (no AI orbiting/floating)
- Every light source has a physical origin (practical or clear environmental source)
- Four sound layers addressed (room tone/ambience/foley/dialogue intent)
- Every key emotional moment has a complete reaction chain (breath→micro-expression→body language→recovery)
- Segment rhythm has breathing (inhale→pause→exhale→suspend)
- Segment-to-segment handoff is at a breath boundary, not mid-action
- Final video prompt contains a clean-frame/no-text line
- Realist projects explicitly forbid game/CG/illustration texture
- Chinese project boards use Simplified Chinese unless otherwise requested
