# Script Breakdown And Segment Plan SOP

Use this before asset prompts or storyboards whenever the user provides a script, outline, episode, scene list, reference remake request, or multi-beat idea.

## Core Rule

Do not write Image2 boards directly from raw script prose.

First convert the script into a production segment plan:

```text
script -> dramatic beats -> scene units -> Seedance segments -> asset list -> storyboard duties -> prompt duties
```

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

## Asset List Gate

Before storyboards:

- every named recurring character has an asset code
- every recurring location has a scene code
- every plot-critical prop has a prop code
- crowd/extras are marked as `EXTRAS_GROUP_*`, not treated as a single cloned identity
- style references are marked as `STYLE_REF_*` or `STYLE_BIBLE`

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
- every segment starts at `0:00` and ends at or before `0:15`
- every segment has a rhythm strategy
- every segment has complexity risk checked
- every storyboard has a matching Seedance prompt planned
- no raw script paragraph is being compressed into one overfull segment

