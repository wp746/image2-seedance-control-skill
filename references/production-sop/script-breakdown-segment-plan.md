# Script Breakdown And Segment Plan SOP

Use this before asset prompts or storyboards whenever the user provides a script, outline, episode, scene list, reference remake request, or multi-beat idea.

## Core Rule

Do not write Image2 boards directly from raw script prose.

First convert the script into a production segment plan:

```text
script -> dramatic beats -> scene units -> Seedance segments -> asset list -> storyboard duties -> prompt duties
```

For finished scripts, do not treat the script as raw information to summarize. Treat it as a performed score. Read line by line and beat by beat before designing. Preserve the user's story rhythm, emotional turns, dialogue, and sound intentions. The segment plan exists to protect the script, not to simplify it into generic visuals.

## Script Reading Gate

Before any asset/storyboard/Seedance prompt, build an internal reading map:

- exact scene range and source line numbers
- beat-by-beat story purpose
- emotional start, pressure, turn, and exit
- POV or audience knowledge position
- verbatim dialogue/voiceover lock
- required silence, breath, pause, reaction, or withheld information
- recurring characters and their state at this beat
- recurring locations and geography constraints
- recurring props and state changes
- sound motifs, room tone, ambience, foley, music, VFX cues
- Image2 risk: text density, crowd cloning, board overcrowding, mixed labels, substrate/font drift
- Seedance risk: too many characters, too many actions, overlong dialogue, unclear reference priority, exact text rendering, scene/prop/style drift

## Script Viability + Runtime Gate

Before producing final prompts, decide whether the script can actually work at the requested duration. Do not assume the user-provided runtime is correct.

Check:

- Does every important line have enough time to be spoken at natural speed?
- Does every emotional turn have a reaction beat or silence after it?
- Does the story need establishing space before the first line?
- Are there enough visual transitions between locations?
- Are action beats being compressed into dialogue time?
- Does the ending land, or does it cut off because the runtime is too short?
- Are there missing motivations, missing prop handoffs, missing geography, or logical contradictions?

If the answer is no, revise the production plan: extend total runtime, split one scene into more Seedance segments, turn a dense paragraph into a slower one-shot or two-shot, add silent reaction beats, move readable text to post, or recommend script repair before prompt generation if the logic itself is broken.

Do not create a prompt package that will predictably become a rushed or incoherent video.

If the reading map shows a beat is too dense for one segment, split it or extend the segment within the model's reliable duration range. Do not compress the story or delete lines.

When a scene needs 20+ seconds to breathe, design it as linked segments instead of forcing it into one overloaded prompt. Each continuation segment must define:

- previous segment final-frame/video state to inherit
- first-frame body position, eyeline, prop position, light, sound tail, and emotional carryover
- exact dialogue continuation point if a line was split
- what the new segment adds emotionally or narratively
- clean end-state for the next continuation

## Dramatic Beat Table

| Field | Meaning |
|---|---|
| Beat ID | `B01`, `B02` |
| Script source | sentence / paragraph / scene range |
| Dramatic function | DIALOGUE / ACTION / SUSPENSE / TRANSITION / PRODUCT / ATMOSPHERE |
| Emotional start/end | e.g. calm -> dread |
| Story event | what the viewer must understand |
| Performance core | actor behavior that carries the beat |
| Visual core | what must be shown |
| Sound core | what must be heard or withheld |
| Required assets | CHAR / SCENE / PROP / STYLE |
| Segment strategy | one-take / 2-shot / 3-shot / multi-shot / split |

## Seedance Segment Plan

Every segment must have one clear job. A segment is not a paragraph container.

| Segment | Duration | Beat(s) | Function | Shot Count | Rhythm | Must Show | Must Write | Risk |
|---|---:|---|---|---:|---|---|---|---|
| EP01_SC01_SEG01 | 0:15 | B01 | SUSPENSE | 1-2 | slow inhale | space, path, camera | breath, sound, tension | low |

Rules:

- A slow emotional beat can be a 1-shot 15-second segment.
- If one beat needs too much story, split it into multiple segments.
- If one segment contains multiple dramatic functions, decide the dominant function and push the rest into another segment unless the transition is essential.
- Do not use fast cutting to hide unclear script breakdown.
- Preserve emotional breath. If a line, silence, look, or command needs time to land, create another segment instead of rushing it.
- Normal Chinese dramatic speech should usually be planned at 3-4 characters/second, tense whispering at 2-3 characters/second, and urgent commands only briefly faster; add pre-line breath and listener reaction before accepting the segment duration.
- Dialogue/voiceover is not optional metadata. Assign every original line or exact line fragment to one or more segments before writing prompts.
- Keep every segment's job narrow enough that Seedance can execute it without inventing new action, new faces, new props, or new geography.

## Asset List Gate

Before storyboards:

- every named recurring character has an asset code
- every recurring location has a scene code
- every plot-critical prop has a prop code
- crowd/extras are marked as `EXTRAS_GROUP_*`, not treated as a single cloned identity
- style references are marked as `STYLE_REF_*` or `STYLE_BIBLE`
- every asset's reference duty is clear: character identity, scene geography, prop shape/material/state, storyboard camera/blocking, or optional abstract style only
- avoid global mixed visual bibles as Seedance references; split people/scene/prop/map/text into proper asset boards and put global look into prompt text

## Storyboard / Prompt Duty Split

Storyboard must show:

- geography and blocking
- camera positions and motion paths
- shot order and timing
- start/end composition
- physical action and object handoff
- light direction and sound cue markers

Seedance prompt must write:

- micro-expression timing
- breath and speech rhythm
- camera texture and focus behavior
- light quality, grain, surface texture
- sound layers and silence
- continuity, forbidden drift, clean-frame line

If a requirement cannot be made clear in words, draw it in the storyboard. If it cannot be drawn clearly, write it in the Seedance prompt.

## Pre-Prompt Gate

Before writing final prompts, confirm:

- segment plan exists
- every segment has one dramatic job
- every segment starts at `0:00`; duration is chosen by performance rhythm and platform capability, not by a fixed 8-second habit
- every segment has a rhythm strategy
- every long scene has a continuation strategy when needed: previous final frame/video reference, start-state match, exact dialogue carryover, and next end-state
- every segment has complexity risk checked
- every storyboard has a matching Seedance prompt planned
- no raw script paragraph is being compressed into one overfull segment
- no dialogue/voiceover line is omitted, paraphrased, or left unassigned
- Image2-specific text risks have a plan: large short labels, English production board, blurred in-world text, TEXT_PROP_PLATE, or post-production
- Seedance-specific drift risks have a plan: character, scene, prop, style, spatial direction, clean frame, and segment handoff guards
