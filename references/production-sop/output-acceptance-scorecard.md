# Output Acceptance Scorecard — 出片验收评分表

Use this after Seedance generates a video segment. The goal is to decide whether to pass, edit, repair, regenerate, or rebuild the source prompt/board.

Do not judge only by whether the clip "looks good". Judge by whether it fulfills the production contract.

## Verdict Bands

| Score | Verdict | Meaning |
|---|---|---|
| 90-100 | `PASS` | ready for edit or delivery |
| 75-89 | `CONDITIONAL` | usable with small edit, crop, timing, or minor repair |
| 60-74 | `REPAIR` | core idea works, but one or more defects need targeted repair |
| 0-59 | `FAIL` | regenerate or rebuild prompt/storyboard/assets |

Hard fail overrides score:

- wrong character identity
- wrong product or brand-critical prop
- wrong location for a continuity scene
- subtitles, shot labels, random visible text, UI overlays, watermarks, or garbled characters appear in a clean narrative frame
- realist live-action project turns into game, CG, anime, glossy concept art, or digital illustration texture
- user-provided style reference or STYLE_BIBLE is ignored, replaced by a generic default look, or applied so strongly that it changes story/identity/geography
- group scenes show repeated same-face extras, cloned soldiers, or the main character's face copied into the crowd
- spoken dialogue is rushed, lacks reaction time, or appears as unwanted subtitles/text
- segment complexity exceeds model capacity and the required story beat is unreadable
- impossible or broken main action
- slow dramatic beat is cut so fast that the intended emotion cannot be read
- segment cannot connect to previous/next segment
- unsafe, unwanted, or policy-breaking content

## 100-Point Scorecard

| Category | Points | What To Check |
|---|---:|---|
| Identity Lock | 12 | named character face, age, body, hair, wardrobe, performance baseline |
| Crowd/Extras Diversity | 5 | group faces are differentiated; no cloned soldiers/extras; varied age, build, posture, micro-reactions |
| Scene Continuity | 10 | layout, doors/windows, light direction, weather/time, fixed objects |
| Prop/Product Continuity | 8 | shape, color, material, scale, hand relationship, readable short text/logo |
| Story Execution | 15 | main beat, cause/effect, emotional turn, no missing required action |
| Motion And Physics | 10 | gravity, weight, speed, no melting, no impossible body behavior |
| Camera And Composition | 10 | correct shot size, motivated movement, no random orbit/floating, usable framing |
| Light And Style | 8 | source-motivated light, palette, film texture, user style reference match, no sudden style shift |
| Performance And Emotion | 10 | micro-expression, reaction chain, breath, body language, no instant emotion jump |
| Sound/Editability | 7 | sound cues, room tone, usable in/out frames, no broken handoff |
| Prompt Compliance | 5 | follows timecode, aspect ratio, negative notes, no extra characters/props, no rendered text contamination |

## Review Template

```markdown
## Output Acceptance Review
- Project:
- EP / Scene / Segment:
- Prompt version:
- Take:
- Reviewer:
- Verdict: PASS / CONDITIONAL / REPAIR / FAIL
- Total Score:

| Category | Score | Notes |
|---|---:|---|
| Identity Lock /12 | | |
| Crowd/Extras Diversity /5 | | |
| Scene Continuity /10 | | |
| Prop/Product Continuity /8 | | |
| Story Execution /15 | | |
| Motion And Physics /10 | | |
| Camera And Composition /10 | | |
| Light And Style /8 | | |
| Performance And Emotion /10 | | |
| Sound/Editability /7 | | |
| Prompt Compliance /5 | | |

## Hard Fail Check
- Wrong identity: YES/NO
- Wrong prop/product: YES/NO
- Wrong scene: YES/NO
- Text/label contamination: YES/NO
- Wrong visual medium/style: YES/NO
- User style reference ignored/misapplied: YES/NO
- Cloned crowd/extras: YES/NO
- Dialogue/subtitle failure: YES/NO
- Segment over-complexity: YES/NO
- Rhythm destroys story beat: YES/NO
- Broken main action: YES/NO
- Broken segment handoff: YES/NO
- Unsafe/unwanted content: YES/NO

## Decision
- Keep:
- Repair:
- Regenerate:
- Rebuild:
- Next prompt change:
```

## Repair Mapping

Use this table to choose the smallest next action:

| Score Pattern | Likely Cause | Next Action |
|---|---|---|
| Identity low, story high | references weak or far faces | stronger character reference, closer framing |
| Scene low, identity high | floor plan under-specified | add scene board or camera map |
| Prop low | prop board missing or hand relationship unclear | add prop board, close-up, hand lock |
| Motion low | too many actions or complex physics | split segment, one action per shot |
| Camera low | storyboard over-ambitious | simplify camera, lock CAM position |
| Emotion low | prompt lacks reaction chain | add breath, pause, micro-expression timing |
| Text contamination | board labels/subtitles leaked into video | add clean-frame line, remove dialogue text from storyboard thumbnails, regenerate |
| Game/CG look | asset board style was too concept-art oriented | rebuild asset board with realist war-film lock |
| User style mismatch | style was vague, missing, or treated as identity/story reference | create STYLE_BIBLE, add compact style lock to prompts, limit style reference duty |
| Cloned crowd | prompt over-locked one face or treated uniform group as one identity | add crowd diversity guard, reduce hero-face references in wide crowd shots, regenerate |
| Dialogue failure | lines were too long, rushed, or became subtitles | split line, add speech rate/pause/reaction, add no-subtitle boundary |
| Over-complex segment | too many jobs in one generation | return to segment complexity budget and split |
| Fast-cut drama | too many story beats in one 15s segment | rewrite as 1-3 shots or split into more segments |
| Editability low | no in/out state | rewrite handoff and final frame |

## Segment Acceptance Gate

A segment may move to edit only when:

- no hard fail exists
- score is 75 or higher
- the first frame can inherit previous state or the segment is a first segment
- the final frame can hand off to the next segment or serve as an intentional ending
- the user-facing story beat is understandable without reading the prompt
